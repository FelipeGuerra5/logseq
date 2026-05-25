- [Link](https://www.cursoemvideo.com/curso/curso-pratico-de-redes-de-computadores-e-internet-20-horas/aulas/modulo-01-3/modulos/aula-06-como-testar-a-rota-da-conexao-com-a-internet/)
  id:: 699c83df-02ed-461c-a607-d2426d280579
- #Cybersecurity
- # Aulas
  id:: 699c8455-0fdb-46ef-bcd2-9d1e863743ca
	- ## Aula 6
	  collapsed:: true
		- **You can use ping to test the computer network status**
		  collapsed:: true
			- ```powershell
			  PS C:\Users\fbald> ping 127.0.0.1
			  
			  Pinging 127.0.0.1 with 32 bytes of data:
			  Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
			  Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
			  Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
			  Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
			  
			  Ping statistics for 127.0.0.1:
			      Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
			  Approximate round trip times in milli-seconds:
			      Minimum = 0ms, Maximum = 0ms, Average = 0ms
			  ```
		- **You can use it to test connectivity with other networks**
		  collapsed:: true
			- ```powershell 
			  C:\Users\fbald>ping google.com
			  
			  Pinging google.com [142.250.219.238] with 32 bytes of data:
			  Reply from 142.250.219.238: bytes=32 time=5ms TTL=117
			  Reply from 142.250.219.238: bytes=32 time=6ms TTL=117
			  Reply from 142.250.219.238: bytes=32 time=6ms TTL=117
			  Reply from 142.250.219.238: bytes=32 time=6ms TTL=117
			  
			  Ping statistics for 142.250.219.238:
			      Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
			  Approximate round trip times in milli-seconds:
			      Minimum = 5ms, Maximum = 6ms, Average = 5ms
			      
			  
			  ```
		- **You can use `trackert` to see the whole route**
			- ```powershell 
			  C:\Users\fbald>tracert google.com
			  
			  Tracing route to google.com [172.217.30.142]
			  over a maximum of 30 hops: 
			  
			    1    <1 ms    <1 ms    <1 ms  192.168.15.1
			    2     8 ms     5 ms     3 ms  152-255-239-47.user.vivozap.com.br [152.255.239.47]
			    3     2 ms     2 ms    30 ms  201-1-224-253.dsl.telesp.net.br [201.1.224.253]
			    4     4 ms     3 ms     9 ms  152-255-212-5.user.vivozap.com.br [152.255.212.5]
			    5     *        *        *     Request timed out.
			    6     3 ms     3 ms     4 ms  74.125.52.64
			    7    13 ms     4 ms    43 ms  142.251.228.185
			    8    19 ms     3 ms     2 ms  142.250.238.249
			    9     7 ms     7 ms     7 ms  pngrub-ah-in-f14.1e100.net [172.217.30.142]
			  
			  Trace complete.
			  
			  ```
		- You con use `ipconfig` to visualize the ethernet configuration, the gateway IP and the local machine IP adress.
		  collapsed:: true
			- ```powershell
			  PS C:\Users\fbald> ipconfig
			  
			  Windows IP Configuration
			  
			  
			  Ethernet adapter Ethernet:
			  
			     Connection-specific DNS Suffix  . :
			     Link-local IPv6 Address . . . . . : fe80::af93:bd0e:427a:e656%18
			     IPv4 Address. . . . . . . . . . . : 192.168.15.144
			     Subnet Mask . . . . . . . . . . . : 255.255.255.0
			     Default Gateway . . . . . . . . . : 192.168.15.1
			  
			  Wireless LAN adapter Local Area Connection* 1:
			  
			     Media State . . . . . . . . . . . : Media disconnected
			     Connection-specific DNS Suffix  . :
			  
			  Wireless LAN adapter Local Area Connection* 2:
			  
			     Media State . . . . . . . . . . . : Media disconnected
			     Connection-specific DNS Suffix  . :
			  
			  Wireless LAN adapter WiFi:
			  
			     Media State . . . . . . . . . . . : Media disconnected
			     Connection-specific DNS Suffix  . :
			  
			  Ethernet adapter Bluetooth Network Connection:
			  
			     Media State . . . . . . . . . . . : Media disconnected
			     Connection-specific DNS Suffix  . :
			  ```
				- If there is a IP `169.254.0.0` to `169.254.255.255` APIPA - Automatic Private IP Addressing it would mean the the DHCP server is down or not reachable and the local machine is able to communicate only between computers on the same local network also with APIPA active.
				  background-color:: yellow
		- **CDN**
		  collapsed:: true
			- Content Delivery Network
			- It makes sure the content can be accessed without the need to actually reach the main google server at USA.
			-
		-
	- ## Aula 7
	  collapsed:: true
		- **Commands**
			- `ipconfig /all` -> all networks configuration
			- `ipconfig /release`  `ipconfig /renew`-> Release the information about the network and will receive again
			- `ipconfig /flushdns` -> to flush the DNS information
			- `netsh int ip reset` -> Redefine all network configurations.
			- ```powershell
			  # Get -> to retrieve, 
			  # CIM -> Commom Information Model
			  # Instance -> Concrete Object of a Class
			  Get-CimInstance 
			  	-Class Win32_NetworkAdapterConfiguration 
			      -Filter "IPEnable=$true and DHCPEnable=$true" 
			  	| Format-Table -Property DHCP*
			  ```
	- ## Aula 8
		- ### **Communication Ports**
			- Interval -> 0 to 65535
			- **Portas Baixas**
			  collapsed:: true
				- Well Known Ports -> 0 - 1023
			- __Portas altas:__
			  collapsed:: true
				- Registered: 1024 - 49151
				- Dynamic/Private: 49152 - 65535
			- **Command `netstat -a`**
			  collapsed:: true
				- ```powershell
				  PS C:\Users\fbald> netstat -a
				  
				  Active Connections
				  
				    Proto  Local Address          Foreign Address        State
				    TCP    0.0.0.0:135            Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:445            Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:1883           Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:2968           Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:5040           Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:5432           Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:7070           Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:23443          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:28252          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49664          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49665          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49666          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49667          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49668          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:49680          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:57621          Metil-Propano:0        LISTENING
				    TCP    0.0.0.0:64949          Metil-Propano:0        LISTENING
				    TCP    127.0.0.1:5939         Metil-Propano:0        LISTENING
				    TCP    127.0.0.1:7768         Metil-Propano:0        LISTENING
				    TCP    127.0.0.1:27017        Metil-Propano:0        LISTENING
				    TCP    127.0.0.1:50911        Metil-Propano:0        LISTENING
				    TCP    127.0.0.1:50912        Metil-Propano:0        LISTENING
				    TCP    192.168.15.144:139     Metil-Propano:0        LISTENING
				    TCP    192.168.15.144:28252   DESKTOP-742TMTN:58865  ESTABLISHED
				    TCP    192.168.15.144:49431   172.172.255.218:https  ESTABLISHED
				    TCP    192.168.15.144:50780   vip-149-96-209-84:https  ESTABLISHED
				    TCP    192.168.15.144:51864   104.46.162.225:https   ESTABLISHED
				    TCP    192.168.15.144:51933   104.46.162.225:https   ESTABLISHED
				    TCP    192.168.15.144:52321   172.64.148.235:https   ESTABLISHED
				    TCP    192.168.15.144:52377   9:https                ESTABLISHED
				    TCP    192.168.15.144:55379   cj-in-f188:https       ESTABLISHED
				    TCP    192.168.15.144:55687   vip-149-96-209-84:https  ESTABLISHED
				    TCP    192.168.15.144:56548   0:https                CLOSE_WAIT
				    TCP    192.168.15.144:57736   38:https               ESTABLISHED
				    TCP    192.168.15.144:59182   unn-46-151-194-96:https  ESTABLISHED
				    TCP    192.168.15.144:60429   24:https               ESTABLISHED
				    TCP    192.168.15.144:60556   38:https               ESTABLISHED
				    TCP    192.168.15.144:60647   vip-149-96-209-84:https  ESTABLISHED
				    TCP    192.168.15.144:62065   104.46.162.225:https   ESTABLISHED
				    TCP    192.168.15.144:62066   201-0-222-80:http      ESTABLISHED
				    TCP    192.168.15.144:62412   vip-149-96-209-84:https  ESTABLISHED
				    TCP    192.168.15.144:62714   ce-in-f188:https       ESTABLISHED
				    TCP    192.168.15.144:62908   vip-149-96-209-84:https  ESTABLISHED
				    TCP    192.168.15.144:64522   104.46.162.225:https   ESTABLISHED
				    TCP    192.168.15.144:65196   62:http                ESTABLISHED
				    TCP    [::]:135               Metil-Propano:0        LISTENING
				    TCP    [::]:445               Metil-Propano:0        LISTENING
				    TCP    [::]:1883              Metil-Propano:0        LISTENING
				    TCP    [::]:5432              Metil-Propano:0        LISTENING
				    TCP    [::]:7070              Metil-Propano:0        LISTENING
				    TCP    [::]:49664             Metil-Propano:0        LISTENING
				    TCP    [::]:49665             Metil-Propano:0        LISTENING
				    TCP    [::]:49666             Metil-Propano:0        LISTENING
				    TCP    [::]:49667             Metil-Propano:0        LISTENING
				    TCP    [::]:49668             Metil-Propano:0        LISTENING
				    TCP    [::]:49680             Metil-Propano:0        LISTENING
				    TCP    [::1]:42050            Metil-Propano:0        LISTENING
				    TCP    [::1]:49672            Metil-Propano:0        LISTENING
				    UDP    0.0.0.0:123            *:*
				    UDP    0.0.0.0:1900           *:*
				    UDP    0.0.0.0:3702           *:*
				    UDP    0.0.0.0:3702           *:*
				    UDP    0.0.0.0:5050           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5353           *:*
				    UDP    0.0.0.0:5355           *:*
				    UDP    0.0.0.0:49184          172.217.28.164:443
				    UDP    0.0.0.0:49748          *:*
				    UDP    0.0.0.0:50001          *:*
				    UDP    0.0.0.0:56480          *:*
				    UDP    0.0.0.0:56736          *:*
				    UDP    0.0.0.0:56830          172.217.28.142:443
				    UDP    0.0.0.0:57621          *:*
				    UDP    0.0.0.0:60303          *:*
				    UDP    0.0.0.0:64759          *:*
				    UDP    127.0.0.1:1900         *:*
				    UDP    127.0.0.1:56413        127.0.0.1:56413
				    UDP    127.0.0.1:59024        *:*
				    UDP    192.168.15.144:137     *:*
				    UDP    192.168.15.144:138     *:*
				    UDP    192.168.15.144:1900    *:*
				    UDP    192.168.15.144:2177    *:*
				    UDP    192.168.15.144:2968    *:*
				    UDP    192.168.15.144:5353    *:*
				    UDP    192.168.15.144:28252   *:*
				    UDP    192.168.15.144:59023   *:*
				    UDP    [::]:123               *:*
				    UDP    [::]:3702              *:*
				    UDP    [::]:3702              *:*
				    UDP    [::]:5353              *:*
				    UDP    [::]:5353              *:*
				    UDP    [::]:5353              *:*
				    UDP    [::]:5353              *:*
				    UDP    [::]:5353              *:*
				    UDP    [::]:5355              *:*
				    UDP    [::]:49748             *:*
				    UDP    [::]:56737             *:*
				    UDP    [::]:60304             *:*
				    UDP    [::]:64759             *:*
				    UDP    [::1]:1900             *:*
				    UDP    [::1]:5353             *:*
				    UDP    [::1]:59022            *:*
				    UDP    [fe80::af93:bd0e:427a:e656%18]:1900  *:*
				    UDP    [fe80::af93:bd0e:427a:e656%18]:2177  *:*
				    UDP    [fe80::af93:bd0e:427a:e656%18]:59021  *:*
				  ```
			- Command `netstat -ano``
			  collapsed:: true
				- ```powershell
				  PS C:\Users\fbald> netstat -ano
				  
				  Active Connections
				  
				    Proto  Local Address          Foreign Address        State           PID
				    TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       1612
				    TCP    0.0.0.0:445            0.0.0.0:0              LISTENING       4
				    TCP    0.0.0.0:1883           0.0.0.0:0              LISTENING       5404
				    TCP    0.0.0.0:2968           0.0.0.0:0              LISTENING       18172
				    TCP    0.0.0.0:5040           0.0.0.0:0              LISTENING       5476
				    TCP    0.0.0.0:5432           0.0.0.0:0              LISTENING       6244
				    TCP    0.0.0.0:7070           0.0.0.0:0              LISTENING       4920
				    TCP    0.0.0.0:23443          0.0.0.0:0              LISTENING       11344
				    TCP    0.0.0.0:28252          0.0.0.0:0              LISTENING       5660
				    TCP    0.0.0.0:49664          0.0.0.0:0              LISTENING       1276
				    TCP    0.0.0.0:49665          0.0.0.0:0              LISTENING       1100
				    TCP    0.0.0.0:49666          0.0.0.0:0              LISTENING       2120
				    TCP    0.0.0.0:49667          0.0.0.0:0              LISTENING       3504
				    TCP    0.0.0.0:49668          0.0.0.0:0              LISTENING       4536
				    TCP    0.0.0.0:49680          0.0.0.0:0              LISTENING       1244
				    TCP    0.0.0.0:57621          0.0.0.0:0              LISTENING       10748
				    TCP    0.0.0.0:64949          0.0.0.0:0              LISTENING       10748
				    TCP    127.0.0.1:5939         0.0.0.0:0              LISTENING       5740
				    TCP    127.0.0.1:7768         0.0.0.0:0              LISTENING       10748
				    TCP    127.0.0.1:27017        0.0.0.0:0              LISTENING       5368
				    TCP    127.0.0.1:50911        0.0.0.0:0              LISTENING       5672
				    TCP    127.0.0.1:50912        0.0.0.0:0              LISTENING       5680
				    TCP    192.168.15.144:139     0.0.0.0:0              LISTENING       4
				    TCP    192.168.15.144:28252   192.168.15.113:58865   ESTABLISHED     5660
				    TCP    192.168.15.144:49431   172.172.255.218:443    ESTABLISHED     5916
				    TCP    192.168.15.144:50780   149.96.209.84:443      ESTABLISHED     14228
				    TCP    192.168.15.144:52321   172.64.148.235:443     ESTABLISHED     14228
				    TCP    192.168.15.144:52377   35.186.224.9:443       ESTABLISHED     14640
				    TCP    192.168.15.144:55379   142.251.0.188:443      ESTABLISHED     14228
				    TCP    192.168.15.144:55687   149.96.209.84:443      ESTABLISHED     14228
				    TCP    192.168.15.144:57736   35.186.224.38:443      ESTABLISHED     14640
				    TCP    192.168.15.144:59182   46.151.194.96:443      ESTABLISHED     4920
				    TCP    192.168.15.144:60429   35.186.224.24:443      ESTABLISHED     14640
				    TCP    192.168.15.144:60556   35.186.224.38:443      ESTABLISHED     10748
				    TCP    192.168.15.144:62412   149.96.209.84:443      ESTABLISHED     14228
				    TCP    192.168.15.144:62714   64.233.190.188:443     ESTABLISHED     14640
				    TCP    192.168.15.144:62908   149.96.209.84:443      ESTABLISHED     14228
				    TCP    192.168.15.144:65196   34.158.255.62:80       ESTABLISHED     10748
				    TCP    [::]:135               [::]:0                 LISTENING       1612
				    TCP    [::]:445               [::]:0                 LISTENING       4
				    TCP    [::]:1883              [::]:0                 LISTENING       5404
				    TCP    [::]:5432              [::]:0                 LISTENING       6244
				    TCP    [::]:7070              [::]:0                 LISTENING       4920
				    TCP    [::]:49664             [::]:0                 LISTENING       1276
				    TCP    [::]:49665             [::]:0                 LISTENING       1100
				    TCP    [::]:49666             [::]:0                 LISTENING       2120
				    TCP    [::]:49667             [::]:0                 LISTENING       3504
				    TCP    [::]:49668             [::]:0                 LISTENING       4536
				    TCP    [::]:49680             [::]:0                 LISTENING       1244
				    TCP    [::1]:42050            [::]:0                 LISTENING       2708
				    TCP    [::1]:49672            [::]:0                 LISTENING       5316
				    UDP    0.0.0.0:123            *:*                                    8012
				    UDP    0.0.0.0:1900           *:*                                    10748
				    UDP    0.0.0.0:3702           *:*                                    3108
				    UDP    0.0.0.0:3702           *:*                                    3108
				    UDP    0.0.0.0:5050           *:*                                    5476
				    UDP    0.0.0.0:5353           *:*                                    14004
				    UDP    0.0.0.0:5353           *:*                                    14004
				    UDP    0.0.0.0:5353           *:*                                    10748
				    UDP    0.0.0.0:5353           *:*                                    10748
				    UDP    0.0.0.0:5353           *:*                                    10748
				    UDP    0.0.0.0:5353           *:*                                    14228
				    UDP    0.0.0.0:5353           *:*                                    1696
				    UDP    0.0.0.0:5353           *:*                                    14228
				    UDP    0.0.0.0:5355           *:*                                    1696
				    UDP    0.0.0.0:49748          *:*                                    1696
				    UDP    0.0.0.0:50001          *:*                                    4920
				    UDP    0.0.0.0:50930          8.8.4.4:443                            14228
				    UDP    0.0.0.0:51297          8.8.4.4:443                            14640
				    UDP    0.0.0.0:54888          172.217.162.174:443                    14228
				    UDP    0.0.0.0:55304          172.64.155.209:443                     14228
				    UDP    0.0.0.0:56480          *:*                                    10748
				    UDP    0.0.0.0:56736          *:*                                    5740
				    UDP    0.0.0.0:57250          201.0.218.105:443                      14228
				    UDP    0.0.0.0:57621          *:*                                    10748
				    UDP    0.0.0.0:60913          172.217.28.68:443                      14228
				    UDP    0.0.0.0:63351          *:*                                    3108
				    UDP    0.0.0.0:63685          35.186.224.24:443                      14640
				    UDP    0.0.0.0:64759          *:*                                    1696
				    UDP    127.0.0.1:1900         *:*                                    5176
				    UDP    127.0.0.1:56413        127.0.0.1:56413                        5308
				    UDP    127.0.0.1:59024        *:*                                    5176
				    UDP    192.168.15.144:137     *:*                                    4
				    UDP    192.168.15.144:138     *:*                                    4
				    UDP    192.168.15.144:1900    *:*                                    5176
				    UDP    192.168.15.144:2177    *:*                                    20672
				    UDP    192.168.15.144:2968    *:*                                    18172
				    UDP    192.168.15.144:5353    *:*                                    5740
				    UDP    192.168.15.144:28252   *:*                                    5660
				    UDP    192.168.15.144:59023   *:*                                    5176
				    UDP    [::]:123               *:*                                    8012
				    UDP    [::]:3702              *:*                                    3108
				    UDP    [::]:3702              *:*                                    3108
				    UDP    [::]:5353              *:*                                    10748
				    UDP    [::]:5353              *:*                                    14228
				    UDP    [::]:5353              *:*                                    10748
				    UDP    [::]:5353              *:*                                    14004
				    UDP    [::]:5353              *:*                                    1696
				    UDP    [::]:5355              *:*                                    1696
				    UDP    [::]:49748             *:*                                    1696
				    UDP    [::]:56737             *:*                                    5740
				    UDP    [::]:63352             *:*                                    3108
				    UDP    [::]:64759             *:*                                    1696
				    UDP    [::1]:1900             *:*                                    5176
				    UDP    [::1]:5353             *:*                                    5740
				    UDP    [::1]:59022            *:*                                    5176
				    UDP    [fe80::af93:bd0e:427a:e656%18]:1900  *:*                                    5176
				    UDP    [fe80::af93:bd0e:427a:e656%18]:2177  *:*                                    20672
				    UDP    [fe80::af93:bd0e:427a:e656%18]:59021  *:*                                    5176
				  ```
			- **Command `Get-Process -Id <id>` -> will return the process Name and port**
			- **Command to recursively return all the process on `netstat -ano` on a table:**
			  collapsed:: true
				- ```powershell
				  PS C:\Users\fbald> netstat -ano |
				  >> Select-String "LISTENING" |
				  >> ForEach-Object {
				  >> ($_ -split "\s+")[-1]
				  >> } |
				  >> Sort-Object -Unique |
				  >> ForEach-Object {
				  >> Get-Process -Id $_
				  >> }
				  
				  Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
				  -------  ------    -----      -----     ------     --  -- -----------
				     2203      88   198608     164448     262.75  10748   1 Spotify
				      163      11     1556       2748              1100   0 wininit
				      497      28    12140      50876       4.84  11344   1 Ditto
				     1042      19     7744      12008              1244   0 services
				     1799      32    13536      26580              1276   0 lsass
				     1606      23    13576      20924              1612   0 svchost
				      324      24     4244       9416      17.36  18172   1 EEventManager
				      357      17     6848      12324              2120   0 svchost
				      555      28    44156       7452       4.50   2708   1 OneDrive.Sync.Service
				      487      14    16200      14780              3504   0 svchost
				     5869       0       56       1712                 4   0 System
				      801      37    18312      33672              4536   0 spoolsv
				      443      32    36876      14264      28.11   4920   0 AnyDesk
				      145      10     1428       3056              5316   0 jhi_service
				      330      25   367260      27280              5368   0 mongod
				       96       9     1508       3332              5404   0 mosquitto
				      471      26     6384      19260              5476   0 svchost
				      483      32    74488      54500              5660   0 spacedeskService
				      192      13     2304       4044              5672   0 ss_conn_service
				      223      14     2560       4192              5680   0 ss_conn_service2
				      417      91    17648      27864              5740   0 TeamViewer_Service
				      409      13     3136       8220              6244   0 postgres
				  ```
			- ### Well know most used Ports
			  collapsed:: true
				- | Port    | Process | Meaning                             |What it does                                                        |
				  | ------- | ------- | ----------------------------------- |------------------------------------------------------------------- |
				  | 20/21   | ftp     | File Transfer Protocol              |Transfers files between client and server (unencrypted).            |
				  | 22      | ssh     | Secure Shell                        |Secure remote command-line access and encrypted tunneling.          |
				  | 23      | telnet  | Teletype Network Protocol           |Remote terminal access (unencrypted).                               |
				  | 25/587  | smtp    | Simple Mail Transfer Protocol       |Sends email between mail servers and from client to server.         |
				  | 53      | dns     | Domain Name System                  |Resolves domain names to IP addresses.                              |
				  | 67      | dhcp    | Dynamic Host Configuration Protocol |Automatically assigns IP configuration to clients.                  |
				  | 69      | tftp    | Trivial File Transfer Protocol      |Simple file transfer, no authentication, often for network devices. |
				  | 79      | finger  | Finger User Information Protocol    |Retrieves user information from a remote system.                    |
				  | 80      | http    | Hypertext Transfer Protocol         |Transfers web pages (unencrypted).                                  |
				  | 110     | pop     | Post Office Protocol (POP3)         |Retrieves email by downloading it to the client.                    |
				  | 123     | ntp     | Network Time Protocol               |Synchronizes system time with time servers.                         |
				  | 143     | imap    | Internet Message Access Protocol    |Accesses and manages email directly on the server.                  |
				  | 161/162 | snmp    | Simple Network Management Protocol  |Monitors and manages network devices.                               |
				  |443     | https   | Hypertext Transfer Protocol Secure  |Encrypted web communication (HTTP over TLS).                        |
	- ## Aula 9
	  collapsed:: true
		- ### Well know most used Ports
			- | Port    | Process | Meaning                             |What it does                                                        |
			  | ------- | ------- | ----------------------------------- |------------------------------------------------------------------- |
			  | 20/21   | ftp     | File Transfer Protocol              |Transfers files between client and server (unencrypted).            |
			  | 22      | ssh     | Secure Shell                        |Secure remote command-line access and encrypted tunneling.          |
			  | 23      | telnet  | Teletype Network Protocol           |Remote terminal access (unencrypted).                               |
			  | 25/587  | smtp    | Simple Mail Transfer Protocol       |Sends email between mail servers and from client to server.         |
			  | 53      | dns     | Domain Name System                  |Resolves domain names to IP addresses.                              |
			  | 67      | dhcp    | Dynamic Host Configuration Protocol |Automatically assigns IP configuration to clients.                  |
			  | 69      | tftp    | Trivial File Transfer Protocol      |Simple file transfer, no authentication, often for network devices between themselves . |
			  | 79      | finger  | Finger User Information Protocol    |Retrieves user information from a remote system.                    |
			  | 80      | http    | Hypertext Transfer Protocol         |Transfers web pages (unencrypted).                                  |
			  | 110     | pop     | Post Office Protocol (POP3)         |Retrieves email by downloading it to the client, erasing it on the server.                    |
			  | 123     | ntp     | Network Time Protocol               |Synchronizes system time with time servers.                         |
			  | 143     | imap    | Internet Message Access Protocol    |Accesses and manages email directly on the server - without erasing it.                  |
			  | 161/162 | snmp    | Simple Network Management Protocol  |Monitors and manages network devices.                               |
			  |443     | https   | Hypertext Transfer Protocol Secure  |Encrypted web communication (HTTP over TLS).  SSL encryption                      |
			- FTP -> 20 21 File transfer.
			-