- #Trimais
- # Powershell commands to Sensus Information
	- Commands and Precision
		- | Campo | 1/0 | Fonte mais adequada | Observações |
		  | ---- | ---- | ---- |
		  | Index | 1 | Script | Contador interno da exportação. |
		  | Nome do proprietário (usuário logado) | 1 | WMI/CIM | `Win32_ComputerSystem.UserName` |
		  | Usuário principal do computador (AD) | 1* | Active Directory | Possível se sua empresa preencher atributos como `ManagedBy`, descrição, ou outra convenção. O AD não possui um campo padrão "usuário principal". |
		  | Hostname | 1 | WMI/CIM | `Win32_ComputerSystem.Name` |
		  | N/S Máquina | 1 | BIOS | `Win32_BIOS.SerialNumber` |
		  | Marca_Máquina | 1 | WMI/CIM | `Win32_ComputerSystem.Manufacturer` |
		  | Modelo Máquina | 1 | WMI/CIM | `Win32_ComputerSystem.Model` |
		  | Local | 1* | Active Directory | Pode vir de atributos como `Location`, `CanonicalName`, OU do objeto AD caso sua empresa utilize estes campos. |
		  | Andar | 1* | Active Directory | Somente se existir convenção corporativa para armazenar essa informação. |
		  | Teclado | 1 | PnP | `Get-PnpDevice` |
		  | Fio? (Teclado) | 0,5 | PnP | Detectável para Bluetooth; difícil distinguir USB x RF x Docking de forma confiável. |
		  | Mouse | 1 | PnP | `Get-PnpDevice` |
		  | Fio? (Mouse) | 0,5 | PnP | Mesma limitação do teclado. |
		  | Monitores | 1 | WMI | `WmiMonitorID` |
		  | Tamanho monitor | 1* | EDID | Calculável quando fabricante informa dimensões físicas. |
		  | Número do monitor | 1 | WMI | Enumerável por instância. |
		  | N/S Monitor | 1* | EDID | Nem todos os fabricantes preenchem corretamente. |
		  | Modelo_Monitor | 1 | EDID | Geralmente confiável. |
	- User_Name ->
		- ```powershell 
		  (Get-CimInstance Win32_ComputerSystem).UserName
		  ```
	- Computer_Name ->
		- ```shell 
		  (Get-CimInstance Win32_ComputerSystem).Name
		  ```
	- Computer_Serial_Number ->
		- ```shell 
		  (Get-CimInstance Win32_BIOS).SerialNumber
		  ```
	- Computer_Brand ->
		- ```shell 
		  (Get-CimInstance Win32_ComputerSystem).Manufacturer
		  ```
	- Computer_Model ->
		- ```shell 
		  (Get-CimInstance Win32_ComputerSystem).Model
		  ```
	- Window_version ->
		- ```bash 
		  (Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion').DisplayVersion
		  ```
	- SO ->
		- ```bash
		  (Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion').CurrentBuild
		  ```
	- Secondary_Screen ->
		- Input
			- ```bash 
			  $MonitorSizes = Get-CimInstance -Namespace root\wmi -ClassName WmiMonitorBasicDisplayParams
			  
			  Get-CimInstance -Namespace root\wmi -ClassName WmiMonitorID | Where-Object {
			      $_.InstanceName -notmatch '^DISPLAY\\(BOE|AUO|LGD|CMN|IVO|SEC)'
			  } | ForEach-Object {
			  
			      $Monitor = $_
			  
			      $Model = ($Monitor.UserFriendlyName | ForEach-Object { [char]$_ }) -join ''
			      $Serial = ($Monitor.SerialNumberID | ForEach-Object { [char]$_ }) -join ''
			  
			      $SizeData = $MonitorSizes | Where-Object {
			          $_.InstanceName -eq $Monitor.InstanceName
			      } | Select-Object -First 1
			  
			      $Inches = $null
			  
			      if ($SizeData) {
			  
			          $WidthCM  = [double]$SizeData.MaxHorizontalImageSize
			          $HeightCM = [double]$SizeData.MaxVerticalImageSize
			  
			          if ($WidthCM -gt 0 -and $HeightCM -gt 0) {
			  
			              $DiagonalCM = [math]::Sqrt(
			                  ($WidthCM * $WidthCM) +
			                  ($HeightCM * $HeightCM)
			              )
			  
			              $Inches = [int][math]::Round($DiagonalCM / 2.54)
			          }
			      }
			  
			      [PSCustomObject]@{
			          Monitor      = $Model.Trim([char]0)
			          SerialNumber = $Serial.Trim([char]0)
			          Inches       = $Inches
			          InstanceName = $Monitor.InstanceName
			      }
			  }
			  ```
		- Output
			- ```bash
			  Monitor SerialNumber Inches InstanceName
			  ------- ------------ ------ ------------
			  HP V19b BRL0075JK8       19 DISPLAY\HPN3539\4&19606edd&0&UID200195_0
			  ```
	- Mouse_Producer
		- ```bash
		  Get-PnpDevice -Class Mouse | Where-Object {
		  >>     $_.Status -eq 'OK' -and
		  >>     $_.InstanceId -match '^HID\\VID_'
		  >> } | ForEach-Object {
		  >>
		  >>     $VID = ([regex]::Match($_.InstanceId,'VID_([0-9A-F]{4})')).Groups[1].Value
		  >>
		  >>     $Vendor = switch ($VID) {
		  >>         '046D' { 'Logitech' }
		  >>         '045E' { 'Microsoft' }
		  >>         '0461' { 'Primax' }
		  >>         '04CA' { 'Lite-On' }
		  >>         '1A81' { 'Holtek' }
		  >>         default { 'Unknown' }
		  >>     }
		  >>
		  >>     [PSCustomObject]@{
		  >>         Vendor       = $Vendor
		  >>         FriendlyName = $_.FriendlyName
		  >>         InstanceId   = $_.InstanceId
		  >>     }
		  >>
		  >> } | Sort-Object Vendor -Unique
		  ```
	- ## Full Command
		- ```bash
		  $MonitorSizes = Get-CimInstance -Namespace root\wmi -ClassName WmiMonitorBasicDisplayParams
		  
		  $SecondaryScreens = Get-CimInstance -Namespace root\wmi -ClassName WmiMonitorID | Where-Object {
		      $_.InstanceName -notmatch '^DISPLAY\\(BOE|AUO|LGD|CMN|IVO|SEC)'
		  } | ForEach-Object {
		  
		      $Monitor = $_
		  
		      $Model = ($Monitor.UserFriendlyName | ForEach-Object { [char]$_ }) -join ''
		      $Serial = ($Monitor.SerialNumberID | ForEach-Object { [char]$_ }) -join ''
		  
		      $SizeData = $MonitorSizes | Where-Object {
		          $_.InstanceName -eq $Monitor.InstanceName
		      } | Select-Object -First 1
		  
		      $Inches = $null
		  
		      if ($SizeData) {
		  
		          $WidthCM  = [double]$SizeData.MaxHorizontalImageSize
		          $HeightCM = [double]$SizeData.MaxVerticalImageSize
		  
		          if ($WidthCM -gt 0 -and $HeightCM -gt 0) {
		  
		              $DiagonalCM = [math]::Sqrt(
		                  ($WidthCM * $WidthCM) +
		                  ($HeightCM * $HeightCM)
		              )
		  
		              $Inches = [int][math]::Round($DiagonalCM / 2.54)
		          }
		      }
		  
		      [PSCustomObject]@{
		          Monitor      = $Model.Trim([char]0)
		          SerialNumber = $Serial.Trim([char]0)
		          Inches       = $Inches
		          InstanceName = $Monitor.InstanceName
		      }
		  }
		  
		  $MouseProducer = Get-PnpDevice -Class Mouse | Where-Object {
		      $_.Status -eq 'OK' -and
		      $_.InstanceId -match '^HID\\VID_'
		  } | ForEach-Object {
		  
		      $VID = ([regex]::Match($_.InstanceId,'VID_([0-9A-F]{4})')).Groups[1].Value
		  
		      $Vendor = switch ($VID) {
		          '046D' { 'Logitech' }
		          '045E' { 'Microsoft' }
		          '0461' { 'Primax' }
		          '04CA' { 'Lite-On' }
		          '1A81' { 'Holtek' }
		          default { 'Unknown' }
		      }
		  
		      [PSCustomObject]@{
		          Vendor       = $Vendor
		          FriendlyName = $_.FriendlyName
		          InstanceId   = $_.InstanceId
		      }
		  
		  } | Sort-Object Vendor -Unique
		  
		  $CurrentBuild = [int](
		      Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion'
		  ).CurrentBuild
		  
		  $SO = if ($CurrentBuild -ge 22000) { "Windows 11" } else { "Windows 10" }
		  
		  $Inventory = [PSCustomObject]@{
		  
		      User_Name = (
		          Get-CimInstance Win32_ComputerSystem
		      ).UserName
		  
		      Computer_Name = (
		          Get-CimInstance Win32_ComputerSystem
		      ).Name
		  
		      Computer_Serial_Number = (
		          Get-CimInstance Win32_BIOS
		      ).SerialNumber
		  
		      Computer_Brand = (
		          Get-CimInstance Win32_ComputerSystem
		      ).Manufacturer
		  
		      Computer_Model = (
		          Get-CimInstance Win32_ComputerSystem
		      ).Model
		  
		      Window_Version = (
		          Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion'
		      ).DisplayVersion
		  
		      SO = $SO
		  
		      Secondary_Screen = @($SecondaryScreens)
		  
		      Mouse_Producer = @($MouseProducer)
		  }
		  
		  $Inventory | ConvertTo-Json -Depth 5
		  ```