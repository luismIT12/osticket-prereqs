<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# Deployment and Configuration of osTicket Help Desk System in Microsoft Azure

## Project Summary

This project involved deploying the open-source osTicket Help Desk Ticketing System within a Microsoft Azure virtual machine environment. The objective was to configure the required server prerequisites and successfully install the application to simulate a functional enterprise helpdesk platform


### Languages Used
- PowerShell

### Environments Used
- Microsoft Azure
- Windows 10

### Technologies / Applications / Services Used
- osTicket
- Microsoft Azure Virtual Machines
- Internet Information Services (IIS)
- PHP
- MySQL

---


## Demonstration


### Step 1 — Create an Azure Account (If One Has Not Been Created)
Navigate to the Azure portal:https://portal.azure.com

Click Start Free or Sign In and log in using a Microsoft account (Outlook/Hotmail works).

Complete:

Identity verification

Phone verification

Credit/debit card verification

Azure provides up to $200 in free credits for new accounts.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/3b104bcc-0b22-458c-8c05-237e893adfdf" />


Once completed, you will land on the Azure Portal dashboard.


<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/bb9159f3-b917-49f1-9bdc-1a5f43cd0822" />


### Step 2: Azure Virtual Machine Setup
In the Azure search bar, type Virtual Machines.


  <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/f8b3402b-4cd9-4ebc-b738-969198b4863d" />


  
Configure the following:

Subscription: Select your subscription

Resource Group: Create a new one (Example: Osticket-RG)

Virtual Machine Name: Example: OsticketVM

Region: Select your preferred region

Image: Windows 10 Enterprise (or Windows Server if required)

Zone: Zone 1

Size: At least 2 vCPUs recommended

Administrator Username & Password: Create secure credentials

Under Networking:

Virtual Network: Allow Azure to create one

Subnet: Default

Click Review + Create, then Create.


 
  <img width="520" height="546" alt="image" src="https://github.com/user-attachments/assets/42362bf8-7ad7-401d-ae93-3107bb9166e6" />


  <img width="515" height="500" alt="image" src="https://github.com/user-attachments/assets/e7d53b38-70c4-49fd-b66c-afcdadae3244" />



### Step 3 — Install osTicket Prerequisites
- Log into the VM using RDP.
  
  <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/9f31f597-91e5-430b-a833-52931573cf19" />

- Once logged in open up a web browser in the VM download this ( https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) installtion package

  <img width="600" height="412" alt="image" src="https://github.com/user-attachments/assets/703f0e3f-8acc-4276-83ee-48fd105a4f00" />

- Once the download is complete, click on the download folder, right click it and "extact all "

  <img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/3ef275e8-72e9-4d8a-b76a-7257265230f1" />

- Next were going to Install / Enable IIS in Windows WITH CGI
    - Click start, search for control panel, click on programs, click on turn on/off windows features
 
<img width="600" height="443" alt="image" src="https://github.com/user-attachments/assets/fe3fb500-2256-49fd-904a-7012e99b5ea2" />

- Next we select " Internet Infomation services --> world wide web --> application developer services --> check box CGI

<img width="500" height="433" alt="image" src="https://github.com/user-attachments/assets/ce61bd7b-0e21-4658-a23c-c633153e16b2" />


- Click ok then it should start installing CGI

  <img width="600" height="450" alt="image" src="https://github.com/user-attachments/assets/d1310950-28e0-46b6-955f-1085cb739b91" />


- Next open From the “osTicket-Installation-Files” folder and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi), Just keep click next till fully installed

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/55443a01-0bd6-4c66-af0e-50d25d2614df" />
  

- Similarily From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi) click install , then finish to complete installtion

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/49e25c51-d01d-44bd-8f18-1250456119d5" />

- Next we open up file exploxer , then go to our windows(C) drive, Right click inside and Create the directory and name it (PHP)
  
  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/0c584f72-9ac3-4216-b4a9-7ffbe7316057" />

- Next From the “osTicket-Installation-Files” folder, we extract PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the our Created PHP folder

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/30e46bf8-00c0-4227-957f-e434b487e729" />

- Next From the “osTicket-Installation-Files” folder, double click VC_redist.x86.exe., then click install

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/e62baf42-f325-4c4c-aa2d-b0ad50a337e0" />


- Next From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Keep clicking next then we select
Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Create a User name & password Username you won't forget (EX: Username: root , Passowrd: root)


<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/1e6518c2-0a31-41a7-a9d8-80b70621f5cc" />


<img width="600" height="385" alt="image" src="https://github.com/user-attachments/assets/2a77cee7-8e6f-4649-b090-45dad048adb3" />



### Step 4: osTicket Installation
- The final Steps of launching Osticket
  - We're going to search IIS and open as adminstaor

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/b0cb07d5-657e-41ae-8031-e3acbab7a5d2" />

- Next Register PHP from within IIS (PHP Manager)  Click On PHP manager --> select Register New PHP Version --> click on 3 dots ... then find our PHP folder -> find php.cgi and click open, then click ok

<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/81d0e155-a65d-4ccb-9f34-253e7bbdce18" />

- Next restart  IIS, top right

  <img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/899d92f6-aa7c-4ce5-b807-6e921128bd27" />

- Next we Install osTicket v1.15.8 From the “osTicket-Installation-Files” folder, right click and select extract from  “osTicket-v1.15.8.zip” and next we copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/4dd4462f-733c-4c18-88df-1c8aa3e39492" />


<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/1e8846d5-be17-4401-b24a-20f8cfd00ac3" />


<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/4a379b16-ca78-409e-b756-7d4c12af8238" />

- Next we are going to restart IIS server once more, top right


<img width="600" height="380" alt="image" src="https://github.com/user-attachments/assets/d8763cdb-2136-46ff-a9ce-3f922ef086bd" />

- Next on the left from IIS Go to sites -> Default -> osTicket then  On the right, click “Browse *:80” then our OSticket webpage should launch

  <img width="650" height="400" alt="image" src="https://github.com/user-attachments/assets/ca3f8f62-8741-4e5b-9d95-e9cd82285b48" />


- Next Go back to IIS, to enable some exenstions got to --> sites -> Default -> osTicketDouble-click PHP Manager --> Click “Enable or disable an extension”
-->Enable: php_imap.dll
-->Enable: php_intl.dll
-->Enable: php_opcache.dll
 the  Refresh the osTicket site in your browser, observe the changes

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/d0ff7f18-20c5-4e76-9f45-66cc2ac7e56b" />


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/1ff72bdc-efa1-4ce3-a46d-a431d178acd5" />


- Next Rename: ost-config.php From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php --> To: C:\inetpub\wwwroot\osTicket\include\ost-config.php


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/ed29f29d-b0bc-4ceb-9e04-a4e5d2a0c74a" />

- Next Assign Permissions: ost-config.php, right click then select properties ---> security --> advance
Disable inheritance -> Remove All ---> Add --> princpal  -> type in Everyone ->  All


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/68aac063-4a72-4105-aa49-cbb60533ab79" />


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/b8e78b10-7da7-4423-8e69-eaee66f1acec" />


- Next we  Continue Setting up osTicket in the browser (click Continue) --> finish setting up default infomation on Admin user
  

  <img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/690d3749-3e01-4c5e-a167-2411497bf419" />


- From the “osTicket-Installation-Files” folder, install HeidiSQL. Open Heidi SQL --> bottom left corner --> Click new --> user : root/ Password: root
Connect to the session
Create a new database Name it  “osTicket”

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/6693636f-13d7-479c-84fd-88647a26df4b" />


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/e58a64d7-1e30-4128-8941-436880e82f78" />


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/4c5425ba-3e86-4269-8fbb-b4e2a71b26bf" />


- Next we Continue Setting up osTicket in the browser --> MySQL Database: osTicket --> MySQL Username: root --> MySQL Password: root
  Next Click “Install Now!”

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/be95120d-2ea1-4535-bf3b-24c0b19cbc0c" />


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/9fdf2d14-a2f9-4d26-9721-4a8dba454932" />



- We finally installed it, next we can click on  http://localhost/osTicket/scp/login.php, should take us to link to login for admin

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/978fd255-f96f-42a9-a058-267d49f72200" />


- Once you put your username and password, you should be able to log in

  <img width="600" height="480" alt="image" src="https://github.com/user-attachments/assets/85beb8dd-9d07-4a02-87cf-8f682c139f37" />




---


<br />
