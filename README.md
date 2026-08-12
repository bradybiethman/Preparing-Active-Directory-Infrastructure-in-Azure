# Preparing-Active-Directory-Infrastructure-in-Azure
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing Active Directory Infrastructure in the Cloud (Azure)</h1>
This tutorial outlines the creation of domain controller and client virtual machines and setting up DNS Settings in Microsoft Azure.<br />

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
- Step 4: Run Commands via Windows Powershell to verify proper data transfer
- Step 5: Shut down Virtual Machines.

<h2>Deployment and Configuration Steps</h2>

<p>
<img <img width="2559" height="1439" alt="image" src="https://github.com/user-attachments/assets/00ef7652-34e6-494c-b0b0-fafd8849c9d7" />
</p>
<p>
Step 1: We will navigate to the Microsoft Azure website and get signed in to our account.
</p>
<br />

<p>
<img <img width="2559" height="1439" alt="image" src="https://github.com/user-attachments/assets/ab9879a5-be48-416f-9901-494617a4ba16" />
</p>
<p>
Step 2: Navigate to the Resource groups tab on the left side of the screen
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
<img <img width="1372" height="1213" alt="image" src="https://github.com/user-attachments/assets/1ea87c69-e6ed-44b1-acb3-724293d6dc5d" />
</p>
<p>
Click Create at the bottom once information is validated.
</p>
<br />

<p>
<img <img width="1146" height="749" alt="image" src="https://github.com/user-attachments/assets/f8dae39c-8dbf-4508-9776-38d5a40440f1" />
</p>
<p>
Step 3: Select Active-Directory Resource group and name the Virtual machine client-1
</p>
<br />

<p>
<img <img width="918" height="695" alt="image" src="https://github.com/user-attachments/assets/34adc3de-2fc1-4322-be25-0d1e313b435e" />
</p>
<p>
Select Windows 10 Enterprise, version 22H2 - x64 Gen2 for the Image and Standard_D2lds_v7 - 2 vcpus, 4 GiB memory ($101.47) for Size.
</p>
<br />

<p>
<img <img width="818" height="657" alt="image" src="https://github.com/user-attachments/assets/24e735d9-c058-4792-bd5a-5c56fa3bcaa2" />
</p>
<p>
Create username and password and check off box under Licensing before clicking Review + create at the bottom.
</p>
<br />

<p>
<img <img width="1156" height="1215" alt="image" src="https://github.com/user-attachments/assets/26cdae8b-1e66-403d-b2cc-aacaf4d96b19" />
</p>
<p>
Ensure validation and click Create at the bottom.
</p>
<br />

<p>
<img <img width="1837" height="590" alt="image" src="https://github.com/user-attachments/assets/3dd21cf2-6ec2-4753-bb22-789a7e8fe4e5" />
</p>
<p>
Navigate back to Virtual machines and click on dc-1.
</p>
<br />

<p>
<img <img width="1329" height="477" alt="image" src="https://github.com/user-attachments/assets/95583e24-ebf1-4f3a-bfa9-b16cfaa1c5f1" />
</p>
<p>
Under Networking select Network settings and click on dc-1638_z1 (primary) / ipconfig1 (primary) to access the Ip Settings for dc-1.
</p>
<br />

<p>
<img <img width="2336" height="1228" alt="image" src="https://github.com/user-attachments/assets/54c0842f-c234-4a72-b526-2d7b5afa2919" />
</p>
<p>
Click on ipconfig1 and on the Edit IP Configuration menu select Static bubble under Allocation and then click Save on the bottom right to ensure the IP Address does not change.
</p>
<br />

<p>
<img <img width="2330" height="564" alt="image" src="https://github.com/user-attachments/assets/27dea81f-27fa-445f-bfb6-702072a6fbec" />
</p>
<p>
Navigate back to Virtual machines and copy the Public IP address for dc-1 to use for logging in via Remote Desktop.
</p>
<br />

<p>
<img <img width="388" height="950" alt="image" src="https://github.com/user-attachments/assets/b9156ea0-ee45-4ac2-8098-def933120297" />
</p>
<p>
Click on start menu on the bottom left of the screen and navigate to Remote Desktop to log in to the Virtual Machine.
</p>
<br />

<p>
<img <img width="404" height="240" alt="image" src="https://github.com/user-attachments/assets/46247c0b-5273-4f7d-b970-dba12fa43b26" />
</p>
<p>
Click on Show Options to expand Remote desktop.
</p>
<br />

<p>
<img <img width="405" height="482" alt="image" src="https://github.com/user-attachments/assets/f848cf51-edd9-4cb0-9135-bb08cfbada32" />
</p>
<p>
Enter credentials to log in to dc-1 remotely.
</p>
<br />

<p>
<img <img width="2559" height="1440" alt="image" src="https://github.com/user-attachments/assets/237180a8-cdd3-4ec9-b4c6-18c5fad4d51d" />
</p>
<p>
Once logged in Server Manager will automatically launch.
</p>
<br />

<p>
<img <img width="634" height="339" alt="image" src="https://github.com/user-attachments/assets/a8431a44-8b7a-49e3-9dd8-9137e5d3f7e2" />
</p>
<p>
Right click the start menu, Select Run, and type in wf.msc. Then click OK to open Windows Firewall.
</p>
<br />

<p>
<img <img width="1043" height="782" alt="image" src="https://github.com/user-attachments/assets/ee9acfba-797b-46ee-8039-47e4580523e4" />
</p>
<p>
Select Windows Defender Firewall Properties under the Overview box.
</p>
<br />

<p>
<img <img width="398" height="454" alt="image" src="https://github.com/user-attachments/assets/e313d4a0-e445-4400-91ee-024c7a584daf" />
</p>
<p>
On Domain Profile under Firewall state turn from On to Off. Click Apply on bottom right.
</p>

<p>
<img <img width="397" height="451" alt="image" src="https://github.com/user-attachments/assets/99612ecb-ae3f-4e1e-8387-eb8834432d7c" />
</p>
<p>
Click over to Private Profile and under Firewall State turn from ON to Off. Click Apply on bottom right.
</p>
<br />

<p>
<img <img width="400" height="453" alt="image" src="https://github.com/user-attachments/assets/23ecf3aa-d0c7-4935-8c3e-b1487b569b88" />
</p>
<p>
Click over to Public Profile and under Firewall State turn from ON to Off. Click Apply on bottom right.
</p>
<br />

<p>
<img <img width="2334" height="570" alt="image" src="https://github.com/user-attachments/assets/894f1937-eaaa-4c83-939e-8abfd78b53f3" />
</p>
<p>
Minimize dc-1 remote desktop using the bar at the top of the page and navigate back to Azure.
</p>
<br />

<p>
<img <img width="1751" height="746" alt="image" src="https://github.com/user-attachments/assets/bbe45c01-2b9f-4c94-8df2-62696e511443" />
</p>
<p>
Click on dc-1 and copy the Private IP address under Networking.
</p>
<br />

<p>
<img <img width="1753" height="1037" alt="image" src="https://github.com/user-attachments/assets/9267788b-fc47-4eb7-9348-de15f6d573b0" />
</p>
<p>
Click on client-1 and navigate to network settings and click on client-122_z1 (primary) / ipconfig1 (primary) to open its IP Settings.
</p>
<br />

<p>
<img <img width="1420" height="677" alt="image" src="https://github.com/user-attachments/assets/ee7d5150-cbd1-4ac0-93ec-cd6a85bd134c" />
</p>
<p>
Select DNS servers from menu on left.
</p>
<br />

<p>
<img <img width="1166" height="1228" alt="image" src="https://github.com/user-attachments/assets/dcb57705-ce5b-490b-b5f6-7f8dfc9bd080" />
</p>
<p>
Select Custom the bubble and paste in dc-1's private IP Address under Custom DNS Servers. Select Apply at the bottom to save settings.
</p>
<br />

<p>
<img <img width="2557" height="789" alt="image" src="https://github.com/user-attachments/assets/fbb4f244-38f4-4dec-b8b8-1fe59d985075" />
</p>
<p>
Navigate back to virtual machines on the left side menu.
</p>
<br />

<p>
<img <img width="2058" height="303" alt="image" src="https://github.com/user-attachments/assets/3c9d053d-a6ce-473d-8441-66465751401e" />
</p>
<p>
Select the check box next to client-1 and press restart on the bar on top. (This ensures client-1 is using the proper DNS Settings)
</p>
<br />

<p>
<img <img width="2332" height="729" alt="image" src="https://github.com/user-attachments/assets/9f6fc417-e282-4387-9696-b14692d22855" />
</p>
<p>
Click on client-1 and copy the Public IP address under Networking.
</p>
<br />

<p>
<img <img width="891" height="928" alt="image" src="https://github.com/user-attachments/assets/40f1ae53-03fc-4673-a9ae-90322526d4f1" />
</p>
<p>
Open back up Remote Desktop login from the start menu on the bottom left.
</p>
<br />

<p>
<img <img width="405" height="241" alt="image" src="https://github.com/user-attachments/assets/8d6c441a-f326-4376-8d82-ae95424b8e6b" />
</p>
<p>
Click on Show Options to expand the dialog box.
</p>
<br />

<p>
<img <img width="401" height="482" alt="image" src="https://github.com/user-attachments/assets/1b4fd972-2c48-482d-ac38-aff66d909738" />
</p>
<p>
Enter client-1 IP address and login credentials to log into the virtual machine.
</p>
<br />

<p>
<img <img width="866" height="809" alt="image" src="https://github.com/user-attachments/assets/5666ef07-5185-40a5-bcdb-9588e4a8b4f6" />
</p>
<p>
Step 4: Once logged in search Powershell on the start menu on the bottom left and open Windows Powershell.
</p>
<br />

<p>
<img <img width="858" height="733" alt="image" src="https://github.com/user-attachments/assets/0dc1c9df-2c1c-401c-91cc-b3e7aa727fd1" />
</p>
<p>
In Powershell type the command ping followed by dc-1's private IP address (10.0.0.4 in this case).
</p>
<br />

<p>
<img <img width="856" height="728" alt="image" src="https://github.com/user-attachments/assets/ea1521eb-e784-41de-bcb5-23e0c729b35b" />
</p>
<p>
Observe results of Ping command to ensure it succeeded.
</p>
<br />

<p>
<img <img width="858" height="733" alt="image" src="https://github.com/user-attachments/assets/a9fc1dfe-5fc3-4969-bfe6-c67451a4de5f" />
</p>
<p>
In Powershell run command ipconfig /all and ensure that DNS Servers shows dc-1's private IP address.
</p>
<br />

<p>
<img <img width="2558" height="820" alt="image" src="https://github.com/user-attachments/assets/a601c854-1382-4cf4-aa51-e3fd4cb62707" />
</p>
<p>
Step 5: Close out of both Remote Desktop connections and navigate back to Azure virtual machines page.
</p>
<br />

<p>
<img <img width="2334" height="602" alt="image" src="https://github.com/user-attachments/assets/24f49679-7f84-4389-8ce8-b31c14a24d99" />
</p>
<p>
Select check box for both virtual machines and click on Stop on the top bar to end operation of the virtual machines.
</p>
<br />
