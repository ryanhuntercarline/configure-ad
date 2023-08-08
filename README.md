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

- Create 2 VMs in Microsoft Azure
    - 1 Domain Controller
    - 1 Client Computer
- Change Domain Controller's Private IP to Static 
- Install Active Directory in Domian Controller 
- Create Organizaitonal Units in Active Directory
    - Properties within OUs
- Connecting Client 1 VM to Domain Controller
- Setup Remote Desktop for non-administrative users on Client 1

<h2>Deployment and Configuration Steps</h2>

<p>
<h2>Virtual Machine Creation</h2>


  ![DC-1](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/9cebca24-eca0-4dac-9baf-fdfd212c4fd0) ![Screenshot 2023-08-07 163325](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/c985f9d3-eed5-4b2d-9366-2d0ced4c71b6)


</p>
<p>

In Microsoft Azure, set up two virtual machines: the first as a Domain Controller to host Active Directory, and the second as a client computer for future Domain Controller connection testing
</p>
<br />
<h2>Static IP Adress</h2>

<p>

  ![staticIP](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/64b4acd9-4f31-41dc-a3a7-3e48ebb93fcd)

</p>
<p>
Still in Azure, modify the Domain Controller's private IP address from dynamic to static for consistent network configuration
</p>
<br />


<p>
<h2>Install Active Directory Domain Services on DC-1 Virtual Machine</h2>

![ADDomainServices](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/b3e31dde-0548-4759-9169-c72ea5f22d17)

</p>
<p>
-Open Server Manager from the Start menu

-Navigate to "Add roles and features"

-Confirm the correct IP address

-Choose "Active Directory Domain Services" and proceed with the installation
</p>
<br />

<h2>Promote Server/Name Domain</h2>

![promote server](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/3ef594e1-8241-4418-b1c0-7afe2121e10e)![namedomain](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/68e12b32-8840-4abc-88d3-c12a4f6ded89)

</p>
<p>
While still in Server Manager:

-Promote this server to a domain controller

-Select "Add a new forest"

-Enter the Domain Name and set a password

-Complete the Active Directory installation process
</p>

<h2>Organizational Units</h2>

![Screenshot 2023-08-07 170650](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/8d0207cb-a211-4620-822b-b3a1667d89b8)

</p>
<p>

-After successfully installing Active Directory, you will be logged out of DC-1 

-To reconnect, use Remote Desktop with DC-1's public IP address 

-Once logged back in, open "Active Directory Users & Computers" using the search bar

-Right-click under mydomain.com and proceed to create two new organizational units: "_EMPLOYEES" and "_ADMINS" as shown above
</p>

<h2>Properties of Users within Organizational Units</h2>

![Screenshot 2023-08-07 172330](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/8821622b-f7d4-4d2d-b8f6-03b47d6b022f)![Screenshot 2023-08-07 172423](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/31671082-b166-4101-b420-3cab66383d99)![Screenshot 2023-08-07 172451](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/207e654a-891c-4195-91b2-648f72a117b6)![Screenshot 2023-08-07 172617](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/be1fa41d-781c-478c-a382-e0e35836f9d7)

Within Active Directory, you have the capacity to establish user accounts and tailor user attributes, such as modifying group memberships, as demonstrated above

</p>
<p>
    

<h2>Client 1 Connection to Domain</h2>

![Screenshot 2023-08-07 162115](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/822a45ab-e821-40c2-99fc-0dc4deddfc03)![Screenshot 2023-08-07 192157](https://github.com/ryanhuntercarline/configure-ad/assets/141659465/62bede51-238d-4777-af53-94139d8b379f)

In the Azure environment:

-Retrieve DC-1's Private IP Address.

-Access Client 1's VM.

-Update Client 1's DNS server settings with the IP Address obtained from DC-1, as illustrated above.

-This connection is essential for Client-1 to establish access to the domain established in DC-1.
