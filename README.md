<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket Help Desk Ticketing System Deployment in Microsoft Azure

## Project Summary

This project is a hands-on walkthrough based on IT Support curriculum. It demonstrates how to deploy the osTicket help desk ticketing system inside a Microsoft Azure virtual machine. The lab simulates a real-world IT support environment where users submit tickets and help desk agents manage and resolve those tickets.

This project was completed to demonstrate practical help desk, cloud infrastructure, and troubleshooting skills commonly required for entry-level IT support roles.

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


### Step 1 — Create an Azure Account (if one hasn't been made yet)
Go to the Microsoft cloud platform at: https://portal.azure.com Click Start free or Sign in, Log in with a Microsoft account , (Outlook/Hotmail works)

Complete the following : Identity verification ,Phone verification ,Credit/debit card (for validation — 200$ is avalible as a free tier is offered)

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/3b104bcc-0b22-458c-8c05-237e893adfdf" />


Once finished, you’ll land in the Azure Portal Dashboard like the image below :


<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/bb9159f3-b917-49f1-9bdc-1a5f43cd0822" />


### Step 2: Azure Virtual Machine Setup
-- Next we create our Virtual machine for the Osticket, we search on top for virtual machine :

  <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/f8b3402b-4cd9-4ebc-b738-969198b4863d" />

- Once it's been selected, we click create on top left
   - Subscription : you select your own base on account
  - Resource group : click create a new one name it (EX : Osticket)
  - virtual name : create one base on your choice (ex: OsticketVM)
  - Region : select your region
  - image: select windows 2021 enterpise 
  - zone : Zone 1
  - size : at least 2 vcpu!
  - Create a user name & password for VM
  - click Next till we get to network section
  -   Virtual network : one is going to get created
  -   subnet : defualt 
  - we click create !
 
  <img width="520" height="546" alt="image" src="https://github.com/user-attachments/assets/42362bf8-7ad7-401d-ae93-3107bb9166e6" />


  <img width="515" height="500" alt="image" src="https://github.com/user-attachments/assets/e7d53b38-70c4-49fd-b66c-afcdadae3244" />



### Step 3: osTicket Prerequisites Installation
- Log in to the VM we created (Osticket)
  
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
  

- Next From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

  
  



 <img width="500" height="399" alt="image" src="https://github.com/user-attachments/assets/9a94b4f1-eb5d-4c33-8cb0-7c5357008211" />

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0272e3ba-799f-4f96-93ee-2b62b39afb98" />


- Installed MySQL database server

 <img width="483" height="391" alt="image" src="https://github.com/user-attachments/assets/d6eef78d-65fd-4b73-afed-587e05cccb71" />


### Step 4: osTicket Installation
- Downloaded and installed osTicket

 <img width="500" height="510" alt="image" src="https://github.com/user-attachments/assets/01154c11-cadb-4126-86ed-b29d71aaa453" />

- Completed the web-based installation process

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/a6dd7fb9-d922-4c55-a03d-2912cb2277dd" />

- Connected osTicket to the MySQL database

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6f74267a-8923-41c3-9025-a38f2ba49c8b" />


### Step 5: Help Desk Ticket Workflow
- Created departments and help desk agents
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f43487c5-36aa-4f70-b393-3b4b68aad68e" />

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/edf11106-5407-476a-9903-379803b49ecb" />


- Submitted a test support ticket

  <img width="500" height="502" alt="image" src="https://github.com/user-attachments/assets/960475d6-7638-4d7a-b108-6fef6b9f9437" />

- Assigned and resolved the ticket using the osTicket admin panel

  <img width="500" height="318" alt="image" src="https://github.com/user-attachments/assets/454fabcc-5b2e-45c2-97e5-a6695b07f309" />


---


<br />
