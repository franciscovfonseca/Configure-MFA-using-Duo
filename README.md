<p align="center">
<img src="https://i.imgur.com/VGKt0wo.png" height=20%" width="20%" alt="Duo Logo"/>
</p>

<h1>Setting Up MFA and Protecting RDP Using Duo (Server 2019)</h1>

<h2>Description</h2>

In this lab, we'll elevate our *Azure Server 2019* security by **Integrating Multi-Factor Authentication (MFA) using Duo Security when using RDP**.

In an era where cyber threats are evolving, safeguarding your digital assets is paramount.

This project aims to **Fortify your Azure Server Environment** by introducing an **Additional Layer of Authentication**, ensuring only authorized users gain access.

<br>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- Remote Desktop
- Cisco Duo Security RDP: https://duo.com/docs/rdp#first-steps
<br>



<h2>Step 1: Create Azure Server 2019 VM</h2>
<br>

Generate a **Virtual Machine** and choose the "***Windows Server 2019 Datacenter***" image.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/49ea21f9-e8ba-4088-9cad-9aaacfc03621)" height="70%" width="70%" alt="9"/><br />
<br>


Create a user profile with the role "***Helpdesk***", establish a **Password**, and ensure that **Remote Desktop Protocol (RDP)** on port 3389 is selected.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/ab536883-6b4f-46e4-9b17-7ac9dbb01ad2)" height="70%" width="70%" alt="9"/><br />
<br>
<br>

<h2>Step 2: Sign Up for Duo Security and Create User</h2>
<br>

Register for a free trial on **Duo Security** (https://signup.duo.com/).

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/50533bed-b148-478b-83d0-3c022e538b5f" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Navigate to the "***User***" section on the left-hand side, then choose "***Add User***".

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/20f64f6e-a125-4324-818f-09327fdebad3" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Complete the necessary fields, and an email confirmation will be sent for login access.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/ab4ec5bf-8a19-4c8a-9d28-b65f74c5139b" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Launch the mobile application on your smartphone and **scan the QR code**.

The application will guide you through the steps.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/aea67b64-efa8-457b-9077-77483c97277c" height="30%" width="30%" alt="9"/><br />
<br>
<br>


<h2>Step 3: Install Duo Security on Server 2019 VM</h2>
<br>

Access the **Server 2019 VM**.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/b0032b4c-a16e-4e90-9ac7-3e0d73ac284e" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Log in to the **Duo Admin interface** (https://admin.duosecurity.com/login?next=%2F).

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/e5bcc116-8208-41a0-81e4-e9080fb706a9" height="30%" width="30%" alt="9"/><br />
<br>
<br>


Navigate to the left side and select "***Applications***", then choose "***Protect an Application***".

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/f8013466-3bfd-47c6-9ec3-7fb4a988422e" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Search for **RDP** and click on "***Protect***" to proceed.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/751ec7f9-b47e-4397-ab3f-1a317b0ce92a" height="70%" width="70%" alt="9"/><br />
<br>
<br>


On the next page ➜ Download the "***Duo Authentication for Windows Login Installer***" package and open the downloaded file when finished.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/c13f207f-c104-4f8c-9b6e-d0ab1f5ae9fc" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Copy and paste the **API Hostname**, **Integration Key**, and **Secret Key** into the Installer.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/a0bd0968-0831-45a6-bf64-fe21822d636a" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/f2b0230d-2ca0-4c4e-846a-b5f4b60d1d60" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/83f1cc48-3459-46b3-9394-d8f7fdcad566" height="50%" width="50%" alt="9"/><br />
<br>
<br>


<h2>Step 4: Log In as User</h2>
<br>

After the installer completes, log in to the **Server 2019 VM**.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/91f9caf6-e704-4c65-ad22-0ceebf2d19c9" height="70%" width="70%" alt="9"/><br />

✅ Congratulations!

The Server VM will now require **Multi-Factor Authentication (MFA)** each time a user logs in using **Remote Desktop Protocol (RDP)**.
<br>
<br>
<br>
<br>



<h2>Conclusion</h2>

Our **Duo Security-driven Multi-Factor Authentication (MFA)** enhances **Azure Server Security** by seamlessly adding an **Extra Layer of Authentication**.

With streamlined configuration, real-time monitoring, and customizable policies, it ensures robust protection for your digital assets.

Embrace this enhanced security for confident navigation in the dynamic realm of cybersecurity.
<br>
<br>
<br>
<br>


