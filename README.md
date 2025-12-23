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
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
1) Create two Azure virtual machines: one domain controller that uses Windows Server 2022 (dc-1) and one client machine that uses Windows 10 (client-1).
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-10-31 10-49-56" src="https://github.com/user-attachments/assets/f0e50998-32c8-4de1-bf5c-ee3ad0fc73e1" />

</p>
<br />

<p>
2) Set the domain controller’s private IP address to static in the Azure network interface settings.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-10-25 15-50-24" src="https://github.com/user-attachments/assets/da2efb2a-7cbc-4a0f-a417-53f7e3077e80" />

</p>
<br />

<p>
3) Open Windows Defender Firewall with Advanced Security on the domain controller. For the tabs named: Domain Profile, Private Profile & Public Profile, select the firewall state and make sure to put it on off.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-10-31 16-39-03" src="https://github.com/user-attachments/assets/36b7179e-e27e-4031-9aa1-1822983e0e7f" />

</p>
<br />

<p>
4) Install and configure Active Directory Domain Services on the domain controller.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-11-22 13-18-20" src="https://github.com/user-attachments/assets/ab276f75-8b73-4ee3-b911-04fe8602bc7b" />


</p>
<br />

<p>
5) Disconnect & Connect to the domain controller using Remote Desktop, Making sure this time you add the domain name in this case mydomain.com to the login of the remote desktop.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-00-19" src="https://github.com/user-attachments/assets/f4467833-c3cf-4e28-9b1a-e842228b02b9" />


</p>
<br />

<p>
6) Create organizational units in Active Directory Users and Computers. For organizational purposes and to follow along with this walkthrough, name them _ADMINS, _CLIENTS & _EMPLOYEES.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-03-28" src="https://github.com/user-attachments/assets/7e214bc0-a13f-43cb-b06e-b23c0f71b567" />


</p>
<br />

<p>
7) Create a new domain user account inside the _ADMINS organizational unit.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-07-56" src="https://github.com/user-attachments/assets/3cdd333c-e382-4e10-9bf1-4457c2eaee23" />


</p>
<br />

<p>
8) Set the password and account options for the new domain user. Ideally, for the purposes of the walkthrough, select the option password never expires. (Keep in mind, in a real-life scenario, this might not be the best thing to do)
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-09-38" src="https://github.com/user-attachments/assets/8ea0fef8-91af-4dc8-9dfa-2e4a3cfe10f0" />


</p>
<br />

<p>
9) Add the new user account (Jane Doe) to the Domain Admins group. By clicking right-click in the user name and selecting properties, go to the tab (Member of), click add, and inside the white box type Domain Admins and press check names.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-11-52" src="https://github.com/user-attachments/assets/e95cd5a8-6865-4c21-a40a-ea43be1a9714" />


</p>
<br />

<p>
10) Now in the client-1 machine, go to settings, in the about section, click into system properties and in the computer name tab press the button change. In there select Domain and write down the name of the domain (In this case mydomain.com) and press ok. If everything done correctly you should have a text welcoming to the domain and then asking you to restart the machine.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-21-32" src="https://github.com/user-attachments/assets/deb3e114-1d64-4cfb-bb49-b93df35b9449" />


</p>
<br />

<p>
11) Back to DC-1, in Active Directory Users and Computers, inside the computers folder, drag and move client-1 to the _CLIENTS OU. Press okay on the warning sign. 
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-24-54" src="https://github.com/user-attachments/assets/c77439f7-c206-4a58-917e-d23ef3a5e157" />


</p>
<br />

<p>
12) Now Connect to the client-1 machine using the domain administrator account and using the domain name as well.
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-28-34" src="https://github.com/user-attachments/assets/59f4c8aa-b231-4821-92cc-0e5f63163cbc" />


</p>
<br />

<p>
13) Grant domain users permission to access the client machine via Remote Desktop.(NEEDS TO BE MRE PRECISE).
</p>
<p>
<img width="1920" height="1080" alt="Screenshot from 2025-12-04 11-32-33" src="https://github.com/user-attachments/assets/c40bb5f9-afd6-41ef-a325-ab06323be26b" />


</p>
<br />

<h2>Conclusion</h2>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
