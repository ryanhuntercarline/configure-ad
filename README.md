<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Creat 2 VMs in Microsoft Azure
    - 1 Domain Controller
    - 1 Client Computer
- Change Domain Controller's Private IP to Static 
- Install Active Directory in Domian Controller 
- Create Organizaitonal Units in Active Directory
- Connect Client 1 to Domain Controller
- Setup Remote Desktop for non-administrative users on Client 1

<h2>Deployment and Configuration Steps</h2>

<p>

  ![DC-1](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/9cebca24-eca0-4dac-9baf-fdfd212c4fd0) ![Screenshot 2023-08-07 163325](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/c985f9d3-eed5-4b2d-9366-2d0ced4c71b6)


</p>
<p>

In Microsoft Azure, set up two virtual machines: the first as a Domain Controller to host Active Directory, and the second as a client computer for future Domain Controller connection testing
</p>
<br />

<p>

  ![staticIP](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/64b4acd9-4f31-41dc-a3a7-3e48ebb93fcd)

</p>
<p>
Still in Azure, modify the Domain Controller's private IP address from dynamic to static for consistent network configuration.
</p>
<br />


<p>


![ADDomainServices](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/b3e31dde-0548-4759-9169-c72ea5f22d17)

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
