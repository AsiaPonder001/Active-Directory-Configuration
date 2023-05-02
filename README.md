<p align="center">
<img src="https://i.Imgur.com/tBg2A87.png" alt="Microsoft Active Directory Logo"/>
</p>

<h2>Active Directory Deployed in the Cloud (Microsoft Azure)</h2>
  
<p>In the last tutorial I installed Active directory within Azure Virtual Machines. This tutorial I will go through configuration of Active Directory.</p>

- Create an Admin User account, Organizational Unit, and New Employee to the Domain Admins Security Group. 
- Join the Client to the DC
- Set up Remote Desktop for users/non-administrative users.
- Create a Bunch of Users

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
  
 <h2> Create an Admin User account and Organizational Units </h2>
 <p>Open Active Directory Users and Computers > Right click on mydomain.com > Click New > Click Organizational unit create one for both: </p>
 
- _EMPLOYEES(*NOTE: to make sure to put underscore and all words are capital for powershell script)
- _ADMINS

<img src="https://i.imgur.com/b5p8ppc.png">
<img src="https://i.imgur.com/LSUMMZg.png">

Right Click on mydomain.com > Click to Refresh

 <h2>Create an Admin User Account</h2>
 <a>Right click on _ADMINS > Click New > Click User</a>
 
 <img src="https://i.imgur.com/ndS71kC.png">
 
 <b> Fill in Information and Create a Password</b>
 
 Uncheck: user must check password at next logon
 
 Check: Password never expires 
 
 <img src="https://i.imgur.com/Eq1OV2X.png">
 <img src="https://i.imgur.com/f0tESfY.png">
 
<h2>Assign New "User" Admin to Admins Security Group </h2>
 
<b>Right click on new user name > Click on Properties</b>

<img src="https://i.imgur.com/17miYVt.png">
  
<b>Click Member of > Click ADD </b>
 
 <img src="https://i.imgur.com/gekIQmD.png">
 
 <b>Type: Domain > Click Check Names</b>
 
 <img src="https://i.imgur.com/Ce2hG3b.png">
 
<b> Click Domain Admins > Click Ok > Click Apply > Click Ok </b>

<img src="https://i.imgur.com/8Aqu3Bt.png">
  
<a>Log off of the DC and back into with new credentials</a>

<img src="https://i.imgur.com/EjoJrke.png">
  
<h2> Join Client to the Domain Controller</h2>
<a> In the DC go to System > Click Rename this Pc advanced > Click Change > Click Domain > Type: mydomain.com > Click Ok </a>
Dc should restart after and you will have successfully joined the Client to DC.
  
<h2>Set up Remote Desktop for users/non-administrative users</h2>
<a> Open system Properties > Click Remote Desktop > Click Select Users that can access this pc > Click ADD > Type: Domain Users > Click Check Names > Click Ok </a>
(Now all Domain Users can access the Client)
  
<h2>Create a Bunch of Users</h2>
To create the users we will use a script, <a href="https://github.com/AsiaPonder001/BunchofUsers/blob/main/README.md?plain=1)"> CLICK HERE</a>
<img src= "https://i.imgur.com/h7fem0x.png"/>
<a>Click RAW to copy the script</a>
<a> On Dc > Open POWERSHELL as an Admin > Click Create a New File > Paste the script > Click Run the Script </a>

<h2> Sign in the Client as one of the new users from the bunch we just created</h2>
Pick a name and sign in.
