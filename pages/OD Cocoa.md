- [[Calculus for fiscal on OD Cocoa BR]]
- [[TC's Errors - OD Cocoa BR]]
- [[Transction Net Price no SAP]]
- [[Calculations 2]]
- [[Creating WB]]
- [[OD App Labels Corrections]]
- [[OD Cocoa Help Desk]]
-
-
-
- ## UAT
- Demonstration users: #usersod #Login #edc
	- Br_Cocoa_Commercial/Olam123+
	  Br_Cocoa_Fiscal/Olam123+
	  Br_Cocoa_Finance/Olam123+
	  BR_Cocoa_Agronomy/Olam123+
	- Admin_Brazil/Olam123+
- Mobile:
	- Version: https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-android/distribution_groups/sit
	- user: OD ID -> THTH0327
	- ![image.png](../assets/image_1671542237188_0.png)
	-
- ## First meeting **18NOV22**
- ### Good practices from the #digital team
- 1. The promoter for each of the branches that can be on site and who can support us to understand the farmer.
  
  2. Increase awareness on the App
  	Talk to Marcela from marketing team
  	Banners
  	Videos
  	For coffe there is a webpage so only a link can be passed
  
  3. Train the commercial and susteihability teams
  	For they will go and help the farmers
  	I'm responsible to train the first layer of user (business team)
  
  4. Mapping of the LBA (Local Business Administrator)on the production team
  5. Web  page to see and donwload app - Similar https://www.ofi.com/sorteio.html
  6.
-
-
- ### Second meeting
- Getting the farmers mobile phone numbers for the roll out
-
- ### Bank Accont Number into SAP #sap #mdm #bankaccount
	- The SAP can handle both hyphen and character in the bank account number input
	- The Sr Master Data Mannager tha provide the info was:
		- Senthil Kumar Somasundaram
		- senthil.sundaram@olamnet.com
-
- ### **08DEZ22**
	- Setting price up
	- Price configuration settings -> Choose commodity -> Differential Safra settings
	- Premium
		- Geo/FL Price Adjustments
	-
- Make a list of people that need access to the page and what kind of access
-
-
-
- ### **13DEC22 Agronomy**
	- Origin setings -> news & info settings
		- The farmer get the news feed
	- Weather information
	- Agronomy -> info
	- The news in the feed can no t be deleted, only filtered to what will be shown
-
- ## Crop plan
	- #cropplan
	- Who has to receive this document after translation? Joseval Santos,
	-
- ## **19DEC22** Sync with SAP
	- User to use in the next presentation?
		- **User:** Ali will send separately
		- **Password:** ->
	-
	- Some users were created however not yet working for testing and presentation
	- Transaction List
		- Transaction
		- Pending approval
		- Bid Back Transactions
	- On the App
		- Transaction
	- Check transaction on the OD
		- Accept transaction
-
	- If the3 farmer can not access the price you can accept it for  him
		- Enable Add negotiated value -> insert price -> Accept on behalf of farmer
-
	- Manually set the price
		- Price Configuration -> Reference price config -> enable manual price
- ## 21DEZ22 Vendor Creation Problems Resolution
	- Commercial **Create** -> Fiscal **Approve** -> Financial **Approve** -> Created on **SAP**
	-
- ## 27DEC22 - Users for UAT and testing #odcocoa #usersod #Login #EDC
	-
	- Please find below UAT Mobile App links for testing features
	  specific to User Management.
	-
	- Farmer Android App Link: [https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-android/distribution_groups/internal_uat](https://clicktime.symantec.com/15tpJ9AAFKkAhn9jqzwSg?h=SYU4JyF0bdozEONXkKwP1U3N2U75K8Q9yHHDYpezOQM=&u=https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-android/distribution_groups/internal_uat)
	  id:: c25ebacc-e4ad-4001-baa7-b8e7fea50ea6
	- Version 1.0 (63)
	-
	- Farmer IOS
	  App Link: [https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-ios/distribution_groups/internal_uat](https://clicktime.symantec.com/15tpDJxsni4aHqKpJSYJ4?h=dIJN8sar03au_Kh0D19ZGL_x-EkLL9iovtW31egdR8g=&u=https://ind01.safelinks.protection.outlook.com/?url%3Dhttps%253A%252F%252Finstall.appcenter.ms%252Forgs%252Fdo-uat%252Fapps%252Ffarmer-rn-ios%252Fdistribution_groups%252Finternal_uat%26data%3D05%257C01%257CDeepika.Kallubhavi%2540lntinfotech.com%257C3d3851fda1ef4322008908dae4e0e196%257C02aa9fc118bc4798a020e01c854dd434%257C1%257C0%257C638073951786707859%257CUnknown%257CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%253D%257C3000%257C%257C%257C%26sdata%3DimCd2BtgZmWJMt7isTMB25Fmg2R0Be3KcQzZXqtyxUA%253D%26reserved%3D0)
	- Version 1.0
	  (63)
	- Browser: https://uat-ofi.olamdirect.com/
	-
	-
	- Known issue: User will sometimes get an error when updating
	  profile data on Farmer App My Profile screen. We will provide a fix for this
	  issue in the subsequent build.
-
- ## Improvements Interface or Errors 28
	- DEZ22
	- Birthday date do not accept date before 2004
	- On user registration:
		- On State
			- If an state with more then 2 letters is inserted it shows and error message generic, should be more simple and strait forward, or block more then 2 character or insert a place holder
		- Mark the required fields not filled with red or make them easier to find
		- Some users are receiving error message with 2 letters inserted, some are receiving with full state inserted and some are receiving with both cases.
		- Input titles are not following device language.
		- ? On Bank -> If some new bank or agency is made or merged how it can be changed with minimal user input, automatically.
		- Input fields do not strip the input fields, if an space bar is inserted after the input.
		- Some documents have two sides in Brazil, could we ask for the two sides of the document?
		-
	-
	- Código de fornecedor olam trans on Politics of access. "trans" could be inserted as full word, transaction.
	- On automatic e-mail verification, the link to talk to us the e-mail address is wrong. should not have  "~" or "ç" as we use only English characters.
	-
	-
-
- ## OD Cocoa - Digital Strategy 28DEC22
	- Marcellla Bessa
	-
- ## User with problem.
-
## Improvements Interface or Errors 29DEZ22
	- Conta bancária, tem algum modo mais facil de identificar e encontrar o nome do alem de o nome ser muito longo para ser lido.
	- Número de endereço do preenchimento automatico.
	-
- ## Doc TC
	- Should be trranslated to portuguese and then send byu e-mail to the business team.
-
-
- ## Meeting 12JAN2023
	- ### Horário de reunião: 07h30 as 08h30. 15h00 as 16h00 para seg - terça - quarta
	- OK - Profile picture should not be an mandatory field
	- OK - A Bank not registered on SAP?
	- OK - Farm details should have **complement** (additional info) for address not required but available.
	- OK - The program of sustainability toggle should do exactly as in the e-mail field
	- OK - For address details still not fetching all the ZIP Code.
	- OK - **Farm Details should not be required but possible by choice of Pessoa Juridica**
	- ***
	- How does the panel for exchange rate works?
	- It is not possible to access user profile if the market board is up.
	- **Operator name** is the responsible for the company or from Olam?
	- What is the max size for the pictures?
	- The type of delivery can be changed latter?
	- How long can be a bank account number?
	-
- ## Meeting January 16th
	- A user was registered on the last meeting however it does not show on the search with the correct criteria.
	- To insert the CPF and CNPJ into the search area for farmers list should be possible to insert only numbers, also the label does not
	- User has been registered however he does not show on the farmers list, with the pending approval criteria, and pessoa juridica enable.
	- Zip Code still not fully working. under Address Details.
	- The possibility under bank details could be more straight foward.
	- Could the bank account number receive zeros on the left automatically
	- The phone number accuse as it is already existis and it is not posssible to insert it, however the farmer leave it to be registered on friday and it is not in the SAP
	-
	- Problems found:
	-
	- Problem 01 #odcocoa
		- Error while user registration on UAT version:
		  •
		- Link: https://uat-ofi.olamdirect.com/#/roster-view
			-
		- User: Felipe Baldim Guerra
		- e-mail: felipe.guerra@ofi.com
		- Problem:
			- When registering Pessoa Jurídica
			- After all information was filled and the send button enabled, I clicked on the send button, an alert message raised without label
			- After closing it and sending the information again one alert raised of e-mail already registered, however the e-mail is surely not in the OD Data Base
		- My suspicion:
			- Every time we click on the send button the information is pre staged and if an alert pops up it does not prevent the pre staging and every time blocks the information even though is new information
			-
	- Problem 02
		- On user registration upon trying to insert the birth date with the keyboard it is not possible only by searching on the calendar. [Pessoa Física]
		- while trying to test the Pessoa Física registration the page raised a warning as if the images I used on the Pessoa Juridica already existed, however it is not in any user registered.
-
- ## Meeting January 17th
	- Yesterday Hercio and Vitor Couldnt register a new
	- User that couldn't access their account:
		- Karoline
		- Eduardo - partiialy
		- Alisson
		- Thaylan
		- Silvalan
	- Registration Label: "Copia digitalizada de caderneta bancária" -> Comprovante Bancário
	- On farmers lists the third input does not sent automatically to the fourth field
	- The information of the search on the list of farmers is not holding the information upon clicking the return to previous page button
	- 26 TC done today
	-
- ## Meeting  January 18th
	- New version for the app:
		- **Farmer Android App (UAT)**
		  [https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-android/distribution_groups/internal_uat](https://install.appcenter.ms/orgs/do-uat/apps/farmer-rn-android/distribution_groups/internal_uat)
		- Version 1.0 (66)
		- Upon registration:
			- Housing address has no field for number.
			- The field thought to be **UF** is actually **Inscrição Estadual**
	-
- ## Meeting January 19th
	- user did not got available to approvvall after filling all the necessary information
	- After
-
-
- ## Meeting January 20th
	- [Intermittent or solved] On the app while trying to take the picture for the  document the app closes.
	- While on farmers list searching with CPF/CNPJ needs to insert the dots ans dashes would be good to it to be inserted automatically
	-
- ## Meeting January 23th
	- ## Morning
	-
		- User registration by the team of business
		- **Label problems fixed!**
		- Users that **registered** today:
			- Antonio Alvez Pimenta
				- Karoline Gonçalves
				- Alisson Silva
				- Eduardo
				- Thayllan
			- Users pending Registration
				- Vitor Trinca
				- 73981473394
	- ### Meeting February 16th, 2023
		- We need to receive the contract of the email less users in the branch e-mail
	- ## Aftenoon
		- **Notification when the farmer sends a proposal a price.**
		- On the hamburger menu the link bellow LogOut Says "Jurídica", Should be Terms and conditions.
		- News feed alert error when
		-
- ## Meeting January 24th
	- ## Morning
		- **Notification when the farmer sends a proposal a price.**
		- When blocked and unblocked radio option text and alert message text needs revision.
		- Required, to change premium the user should only reach an admin status not fiscal and finance
		- ODBCC-46_12 - The farmer does not receive any information after changing premium and it being rejected
			- 1. commercial team changed the premmim
		- Cadastro basico não aprovado.
		- Envolver eduardo.
		- email - role name -
		-
		-
- ## Meting January 26th
	- ## Morning
		- We should have a commercial admin that is responsible to approve or not some changes in the page.
		- As we did the TC ODBCC-55_10 a questioning has raised:
			- No there is no superior to approve the change in loyalty or sustainability program.
			- would be possible to make a commercial admin to approve this kind of change without it pass right thought?
			- What is the possibility to insert a new kind of user that overseas only some of the changes in the farmer profile and has to approve it?
				- E.g.: After changing the loyalty program is not actually needed to take approval of fiscal as it not their real life attribute, however it is responsibility of the commercial admin, such as Vitor Trinca.
				- It this possible?
				- How long would take? (just to have an idea of possible time frame)
				-
	- ## Afternoon
		- Error:
			- After editing an profile previously rejected by The Fiscal user he did not appear to be approved in the list for fiscal. The profile stain rejected by admin.
		- After starting sign up with form the Farmer App. any
-
- ## Meeting January 26
	- ## Morning
		- Until the user is created (commercial admin) only vitor should have access to change in premium,
		- Do the mapping of each type of change and who would be responsible to oversea it.
			- Send vitor
			- send Gagan
				-
	- ## Afternoon
		- For Bahia needs to be in @
		- In portal and in the App
		-
		-
		- Bid back from the portal side it is not possible.
		-
		- under padrão in quality params "Grãos secos crus" Amendoas Secas.
		-
		- When making selll from the farmer app cannot insert the dot for the price.
		-
		- What each buyer can see,
		-
- ## Meeting January 30th, 2023
	- Does
	- Alert pops up CPF inserted is invalid panelinha.
	- On user register the alert only say about alphanumeric not full size.
	- On transaction  creation the CPF/CNPJ is not auto filling the dots and dash
	- In transaction list the quantity should be available. in the list of transaction
	- name on the column of the transaction list should have unit of measurements
- ## Meeting January 31, 2023
	- Eduasrdo's pprofile stil does not work
- ## user created
	- **BR-BAOF-ISIS-0099**
		- Lorem ipsum 10
	- **BR-PAOM-QGQG-0027**
		- Lorem Ipsum 11
	- **BR-BAOF-ISIS-0100**
		- Lorem Ipsum 12 (juridica)
- After full user registration by the Admin portal we where unable to sell any type of cocoa.
- Neither dots or coma fill in the bid back functionality from ther farmer App
- Bid back functionality does not work in the Admin Portal
-
	-
- ## Meeting February 01, 2023
	- On The farmer app we click in the bell -> notification
	- After we click notification and click on go back it goes to the negotiation page instead of going back to notifications.
	- ## Request about branch name [YES]
		- Both the name in the portal and in the app will be the same, what should it be like?
	- ## Send e-mail
-
- # PTBF
	- ZWB600 - For creating the weight bridge transaction
	- ZMM220 - To insert the transaction information
	- ME23n
	- migo
	-
- ## Meeting
	- Thayllan Fisica convencional -> Retirar
	- Hercio Juridica Sem fumaça -> Posto
	- Felipe Juridica Convencional -> Posto
	-
	- ## Crop Year VS Commercial Year??
	- DONE The analysis on the cocoa is being made in the calendar year, should be set by crop or calendar year on the OD.
	-
	-
	- ## Meeting February 14, 2023.
		- Upon inserting the price for the premium, the price is not saved.
			- Premios  e Comissões -> Premio Agricultor
		- Crop Year Differential under price configuration settings should be per state as the ICMS settings
		- Bolsa de nova york nao está atualizando.
		- Espirito Santo -> Bahia
			- Pessoa física cacau Tipo 1
		- Pará na Bahia.
		-
		-
-
- ## Meting FEB 15th, 2023
	- Freight configuration does not work,
		- is not possible to insert a new configuration.
	- update information from the app
		- If the user update information from the app and is approved in all instances ->
		- The
	- pará -> pará
		- altamira e medicialandia.
	- pará -> bahia
		- Itabuna
		- Ipiau
		- Gandu
		- **Ilheus**
	- Criar pessoa fisica
		- fazendas no Pará
		- Ilheus para entrega
	- [[Calculus for fiscal on OD Cocoa BR]]
-
- ### Agronomy Meeting Feb 16th, 2023
	- Where the information came from for weather information?
	-
	-
	- Under **Surveys** Region should be by:
		- A specific list of
		- Daniel Braga Can provide a list with all regions em:
			- | Grupo de produtores | Município | Estado |
		- País
		- Estado
		- Cidade
		- Grupo de produtores (Região) in accord with teh OFIS_Baseline sheet from the file:
			- ![File]()
		- Sustainability Program
	-
	- **Crop care**
		- How it works
		- How many people I will need to give maintenance to it.
		-
		-
- ### Meeting Agronomy
	- DONE Yasmin access is not working send it to ALi
	-
	-