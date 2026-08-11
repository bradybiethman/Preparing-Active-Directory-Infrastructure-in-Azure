# Preparing-Active-Directory-Infrastructure-in-Azure
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing Active Directory Infrastructure in the Cloud (Azure)</h1>
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

- Step 1: Sign in to Microsoft Azure
- Step 2: Setup Domain Controller Virtual Machine in Azure
- Step 3: Setup Client-1 Virtual Machine

<h2>Deployment and Configuration Steps</h2>

<p>
<img <img width="2559" height="1439" alt="image" src="https://github.com/user-attachments/assets/00ef7652-34e6-494c-b0b0-fafd8849c9d7" />
</p>
<p>
First we will navigate to the Microsoft Azure website and get signed in to our account.
</p>
<br />

<p>
<img <img width="2559" height="1439" alt="image" src="https://github.com/user-attachments/assets/ab9879a5-be48-416f-9901-494617a4ba16" />
</p>
<p>
Navigate to the Resource groups tab on the left side of the screen
</p>
<br />

<p>
<img <img width="1713" height="1230" alt="image" src="https://github.com/user-attachments/assets/6cd2330a-92e9-4aab-808e-c64a90f3f575" />
</p>
<p>
Click Create on the top left.
</p>
<br />

<p>
<img <img width="1015" height="1227" alt="image" src="https://github.com/user-attachments/assets/3602c27b-f7c2-4fd0-8b0f-8aaf2e087161" />
</p>
<p>
Name our resource group Active-Directory and ensure that it is listed under the proper Subscription and in the proper Region (in this case (US) East 2) before clicking on Review + create at the bottom.
</p>
<br />

<p>
<img <img width="776" height="1228" alt="image" src="https://github.com/user-attachments/assets/cd732a13-a899-4e2d-881a-dbee0ec448f4" />
</p>
<p>
Review the information for accuracy before clicking Create at the bottom.
</p>
<br />

<p>
<img <img width="2335" height="480" alt="image" src="https://github.com/user-attachments/assets/644d2d15-6dae-4265-a4bd-c29289ef76f8" />
</p>
<p>
Ensure that the Resource Group has been created in Azure. (This may require you to press refresh to make sure it works.)
</p>
<br />

<p>
<img <img width="2335" height="480" alt="image" src="https://github.com/user-attachments/assets/644d2d15-6dae-4265-a4bd-c29289ef76f8" />
</p>
<p>
Ensure that the Resource Group has been created in Azure. (This may require you to press refresh to make sure it works.) We then navigate to Virtual networks along the left side panel.
</p>
<br />

<p>
<img <img width="1694" height="848" alt="image" src="https://github.com/user-attachments/assets/3355bfc5-3b69-4be7-870f-eb15e1d2c577" />
</p>
<p>
Click Create to begin making the virtual network.
</p>
<br />

<p>
<img <img width="793" height="1227" alt="image" src="https://github.com/user-attachments/assets/0c9589e4-aaad-44d5-8c2e-05717131d2f8" />
</p>
<p>
Name our virtual network Active-Directory-VNet and review all info for accuracy before clicking on Review + Create at the bottom.
</p>
<br />

<p>
<img <img width="617" height="1226" alt="image" src="https://github.com/user-attachments/assets/bb2e68ca-faac-4a1b-9a28-59a0f6d9d960" />
</p>
<p>
Ensure Validation and then click Create at the bottom.
</p>
<br />

<p>
<img <img width="1821" height="815" alt="image" src="https://github.com/user-attachments/assets/e3400270-e393-44ed-9306-234585a7e725" />
</p>
<p>
Navigate to Virtual Machines along the left side panel.
</p>
<br />

<p>
<img <img width="1772" height="900" alt="image" src="https://github.com/user-attachments/assets/a229893f-364b-4d12-82fb-694f05ae5b3c" />
</p>
<p>
Click Create to make our Virtual Machine.
</p>
<br />

<p>
<img <img width="789" height="633" alt="image" src="https://github.com/user-attachments/assets/3216bf5c-7423-4f21-b977-13a62efaa616" />
</p>
<p>
Select the Resource group that we have created prior (Active-Directory) and name the Virtual Machine dc-1.
</p>
<br />

<p>
<img <img width="789" height="633" alt="image" src="https://github.com/user-attachments/assets/3216bf5c-7423-4f21-b977-13a62efaa616" />
</p>
<p>
Select the Resource group that we have created prior (Active-Directory) and name the Virtual Machine dc-1. Ensure that it is in the same Region as the virtual network.
</p>
<br />

<p>
<img <img width="855" height="686" alt="image" src="https://github.com/user-attachments/assets/26d00d76-3406-4517-a2f8-6e1b30a34cb8" />
</p>
<p>
Select Windows Server 2022 Datacenter: Azure Edition Hotpatch - x64 Gen2 for the Image and Standard_D2lds_v7 - 2 vcpus, 4 GiB memory ($168.63) for the Size.
</p>
<br />

<p>
<img <img width="815" height="503" alt="image" src="https://github.com/user-attachments/assets/fdd269c8-c812-488b-a00c-571517d54b25" />
</p>
<p>
Create our Username and Password that will be used to log into the virtual machine and then click Review + Create at the bottom.
</p>
<br />

<p>
<img <img width="762" height="1152" alt="image" src="https://github.com/user-attachments/assets/1cfe38ce-2646-435b-ad50-0f14529d9160" />
</p>
<p>
Click Create at the bottom once information is validated.
</p>
<br />
