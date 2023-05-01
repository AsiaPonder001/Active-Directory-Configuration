<p align="center">
<img src="https://i.imgur.com/iKPzneQ.png" alt="Microsoft Active Directory Logo"/>
</p>

<h3>Active Directory Deployed in the Cloud (Microsoft Azure)<h3/>
  
<h5>In the last tutorial I installed Active directory within Azure Virtual Machines. This tutorial I will go through configuration of Active Directory.<h5/>

- Create an Admin User account, Organizational Unit, and New Employee to the Domain Admins Security Group. 
- Join Client-1 to the DC
- Set up Remote Desktop for users/non-administrative users.
- Create a Bunch of Users
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
  
 <h2> Create an Admin User account and Organizational Units </h2>
 <p>Open Active Directory Users and Computers > Right click on mydomain.com > Click New > Click Organizational unit creat one for both: </p>
 
- _EMPLOYEES(*NOTE: to make sure to put underscore and all words are capital for powershell script)
- _ADMINS

 <h2>Create an Admin User Account</h2>
 <a>Right click on _ADMINS > Click New > Click User</a>
 
<h2>Assign New "User" Admin to Admins Group </h2>
 <p>Right click on new uesr name > Click ADD > Type: Domain > Click Check Names > Click Domain Admins > Click Ok > Click Apply > Click ok</p>
  
<a>Log off of the DC and back into with new credentials</a>
  
<h2> Join Client to the Domain Controller</h2>
