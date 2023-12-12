<p align="center">
<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/e151a8cd-026d-4c10-9332-1aa90afc69d6 width="50%" height="auto" alt="Microsoft Active Directory Logo Part 2"/>
</p>

<h1>PART 2: On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial is a continuation of the active directory part two. <a href=https://github.com/Archie735/Active-Directory-AZURE-Part-1/tree/main> Click here to see part 1 </a> 


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows 11 Pro(22H2)
- Windows Server

<h2 align="right">1. Creating admin and users in active directory</h2>

- In the Spring desktop search bar, search and open active directory users and computers
- Right-click to create two new organizational units:
      _EMPLOYEES
      _ADMIN

- To create a new user in the new organizational units, click the folders and right-click "user"
- Complete first name, last name, user login name, and password. For now, uncheck "user must change password". Click Finish

    _ADMIN users
  
        1. Lilly Seed; lilly_admin; Whitelilium1
        2. Willow Tree; willow_admin; Weeping2
        3. Adam Son; adam_admin; Genesis 3
  
<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/f382d95a-ed88-434f-b8fc-84ae69e1f4c3 alt="Organizational units and new users">

- In the _ADMIN folder, right-click the users and click on properties
- Add
- In enter object names type "domain" then click check names
- Click domain admin
- Ok
- Apply
- Ok

<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/a70c4ac0-7b32-481f-b5af-05b88dc7e5f9 alt="Admin user properties">


- Log in to one of the admin accounts
  - Copy Spring's public IP address and paste it on remote desktop
  - Log into Lilly's account
   
          Username: myholiday.com\lilly_admin
          Password: Whitelilium1
    
<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/8d54113c-090a-4626-914a-3a4aed9907b4 alt="Lilly's admin">

<h2 align="right">2. Join Autumn on the DNS server</h2>

- Retrieve the private IP address of Spring on Azure
- Go to the Autumn virtual machine and click network settings
- Network interface
- DNS servers
- Paste the Private IP address of Summer
- Save

<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/db2d57af-9f6f-43fa-8649-5e1006308454 alt="Autumn Network Settings">

<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/bdcb2629-bb36-4972-af89-ef2cf8b7b117 alt="Autumn DNS server">

- Go back to the Autumn overview and click on restart
  (At this point the open Autumn remote desktop will restart and log out)

- Login to remote desktop of Autumn using its public IP address
- Click on "settings"
- Search "rename your PC"
- Domain or workgroup
- Click domain and enter myholiday.com
- ok

        Username: myholiday.com\lilly_admin
        Password: Whitelilium1

  - Click ok then Restart now
  
<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/992dba5e-8602-475f-ae6d-7efbd6454d58 alt="renme Autumn DNS">

- Now any of the admin accounts can log in to the Autumn virtual machine because it is a member of the domain myholiday.com
- Open remote desktop and log in using any of the admin users

<img src=https://github.com/Archie735/Active-Directory-AZURE-Part-2/assets/150314129/373d3345-15b7-4f67-aeec-bf269943941f width="50%" height="auto" alt="Willow Tree Admin login">



