<p align="center">
<img src="https://i.imgur.com/VGKt0wo.png" height=20%" width="20%" alt="Duo Logo"/>
</p>

<h1>Setting Up MFA and Protecting RDP Using Duo (Server 2019)</h1>

<h2>Description</h2>

In this lab, we'll elevate our Azure Server 2019 security by integrating Multi-Factor Authentication (MFA) using Duo Security when using RDP.

In an era where cyber threats are evolving, safeguarding your digital assets is paramount.

This project aims to fortify your Azure server environment by introducing an additional layer of authentication, ensuring only authorized users gain access.

<br>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- Remote Desktop
- Cisco Duo Security RDP: https://duo.com/docs/rdp#first-steps
<br>



<h2>Step 1: Create Azure Server 2019 VM</h2>
<br>

Generate a virtual machine and choose the "Windows Server 2019 Datacenter" image.

<img src="https://i.imgur.com/EyiJzcO.png" height="70%" width="70%" alt="9"/><br />
<br>


Create a user profile with the role "Helpdesk," establish a password, and ensure that Remote Desktop Protocol (RDP) on port 3389 is selected.

<img src="https://i.imgur.com/yZZk3Yt.png" height="70%" width="70%" alt="9"/><br />
<br>
<br>

<h2>Step 2: Sign Up for Duo Security and Create User</h2>
<br>

Register for a free trial on Duo Security (https://signup.duo.com/).

<img src="https://i.imgur.com/Uxo9lj9.png" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Navigate to the "User" section on the left-hand side, then choose "Add User." Complete the necessary fields, and an email confirmation will be sent for login access.

<img src="https://i.imgur.com/3xhyySF.png" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/zoIQ7GK.png" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Launch the mobile application on your smartphone and scan the QR code. The application will guide you through the steps.

<img src="https://i.imgur.com/dJAbJ0j.png" height="30%" width="30%" alt="9"/><br />
<br>
<br>


<h2>Step 3: Install Duo Security on Server 2019 VM</h2>
<br>

Access the Server 2019 VM and log in to the Duo Admin interface (https://admin.duosecurity.com/login?next=%2F).

<img src="https://i.imgur.com/rEKkrxW.png" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Navigate to the left side and select "Applications," then choose "Protect an Application." Search for RDP and click on "Protect" to proceed.

<img src="https://i.imgur.com/IBUmJIZ.png" height="30%" width="30%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/hjzdCIB.png" height="70%" width="70%" alt="9"/><br />
<br>
<br>


On the next page, download the "Duo Authentication for Windows Login Installer" package and open the downloaded file when finished. Copy and paste the API Hostname, Integration Key, and Secret Key into the installer.

<img src="https://i.imgur.com/ai8tLPh.png" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/HQYTeRN.png" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/LYHRkdS.png" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/i4Xniv9.png" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://i.imgur.com/Vytqa96.png" height="50%" width="50%" alt="9"/><br />
<br>
<br>


<h2>Step 4: Log In as User</h2>
<br>

After the installer completes, log in to the Server 2019 VM.

<img src="https://i.imgur.com/q9fbXB0.png" height="70%" width="70%" alt="9"/><br />

Congratulations! The Server VM will now require Multi-Factor Authentication (MFA) each time a user logs in using Remote Desktop Protocol (RDP).
<br>
<br>


<h2>Conclusion</h2>

Our Duo Security-driven Multi-Factor Authentication (MFA) enhances Azure server security by seamlessly adding an extra layer of authentication. With streamlined configuration, real-time monitoring, and customizable policies, it ensures robust protection for your digital assets. Embrace this enhanced security for confident navigation in the dynamic realm of cybersecurity.
