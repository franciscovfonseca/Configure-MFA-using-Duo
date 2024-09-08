<br>

<p align="center">
<img src="https://github.com/user-attachments/assets/bcca3ad5-3bac-493d-bb73-00117e0de0c1" height=40%" width="40%" alt="Duo Logo"/>
</p>

<br>

<h1 align="center">Configuring MFA & Protecting RDP Using Duo</h1> 

<br>

<h2>Description</h2>

In this lab, we'll increase our Azure Server 2019 security by integrating **Multi-Factor Authentication (MFA**) using **Duo Security** when using RDP.

Since we live in a world where cyber threats are constantly evolving ➜ **Securing our Digital Assets** is absolutely crucial.

This project focus on **Safeguarding our Azure Server Environment** by introducing an additional **Layer of Authentication**, ensuring only authorized users gain access.

  <details close> 
  
**<summary> 💡 </summary>**

➡️ Duo integrates with Microsoft Windows Client & Server Operating Systems to add Two-Factor Authentication to Remote Desktop.

  </details>

<p align="center">
<img src="https://github.com/user-attachments/assets/30f88f0e-d062-4180-bcb8-38c8f2b10da4" height=70%" width="70%" alt="Duo Logo"/>
</p>

<br>

<br>

<h2>Environments & Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- Remote Desktop
- Cisco Duo Security RDP: https://duo.com/docs/rdp#first-steps

<br>

<br>

<h2>Network Diagram</h2>

<br>

<p align="center">
<img src="https://github.com/user-attachments/assets/962cf86f-33b1-4472-8052-1e242a9e516c" height=70%" width="70%" alt="Duo Logo"/>
</p>




❶ RDP Connection.

❷ Primary Authentication of Windows Credentials (domain or local user).

❸ Duo Windows Logon Credential Provider connection established to Duo Security over TCP Port 443.

❹ Secondary Authentication via Duo Security’s Service.

❺ Duo Windows Logon Credential Provider receives Authentication Response.

❻ RDP Session logged in.

<br>

<br>

<details close> 
<summary> <h2>Step 1️⃣ - Create Azure Server 2019 VM</h2> </summary>
<br>

We'll first create an **Azure Virtual Machine** ➜ and select the ```Windows Server 2019 Datacenter - x64 Gen2``` as the **Image**.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/49ea21f9-e8ba-4088-9cad-9aaacfc03621)" height="70%" width="70%" alt="9"/><br />

<br>

We'll also create a User Account:

- **Username** ➜ ```Helpdesk```
- **Password** ➜ ⚠️ We'll take not of the Password because we'll be using it later
- Ensure that **Remote Desktop Protocol (RDP)** on ```Port 3389``` is selected.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/ab536883-6b4f-46e4-9b17-7ac9dbb01ad2)" height="70%" width="70%" alt="9"/><br />

<br>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Step 2️⃣ - Sign Up for Duo Security & Create a User</h2> </summary>
<br>

The next step is to register for a free trial on **Duo Security** (https://signup.duo.com/).

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/50533bed-b148-478b-83d0-3c022e538b5f" height="70%" width="70%" alt="9"/><br />
<br>
<br>


We'll navigate to the "**Users**" section on the left-hand side ➜ then click on "**Add User**".

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/20f64f6e-a125-4324-818f-09327fdebad3" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Fill out the necessary fields ➜ and an email confirmation will be sent for Login Access.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/ab4ec5bf-8a19-4c8a-9d28-b65f74c5139b" height="70%" width="70%" alt="9"/><br />
<br>
<br>


We'll then launch the **Mobile App** on our smartphone and **Scan the QR code**.

💡 The Application will guide us through the steps to take.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/aea67b64-efa8-457b-9077-77483c97277c" height="30%" width="30%" alt="9"/><br />

<br>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Step 3️⃣ - Install Duo Security on Server 2019 VM</h2> </summary>
<br>

The next thing we're going to do is RDP to the **Server 2019 VM**.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/b0032b4c-a16e-4e90-9ac7-3e0d73ac284e" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Then Log in to the **Duo Admin interface** thorugh this link [this link](https://admin.duosecurity.com/login?next=%2F)

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/e5bcc116-8208-41a0-81e4-e9080fb706a9" height="30%" width="30%" alt="9"/><br />
<br>
<br>


Under "**Applications**" ➜ we'll click on the "**Protect an Application**" buton:

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/f8013466-3bfd-47c6-9ec3-7fb4a988422e" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Search for **RDP** ➜ and click on "***Protect***" to proceed.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/751ec7f9-b47e-4397-ab3f-1a317b0ce92a" height="70%" width="70%" alt="9"/><br />
<br>
<br>


On the next page ➜ we'll click to Download the ```Duo Authentication for Windows Logon installer package```.

We'll open the downloaded file when it's ready.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/c13f207f-c104-4f8c-9b6e-d0ab1f5ae9fc" height="70%" width="70%" alt="9"/><br />
<br>
<br>


Copy and paste the **API Hostname**, the **Integration Key** and the **Secret Key** into the Installer.

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/a0bd0968-0831-45a6-bf64-fe21822d636a" height="70%" width="70%" alt="9"/><br />
<br>

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/f2b0230d-2ca0-4c4e-846a-b5f4b60d1d60" height="70%" width="70%" alt="9"/><br />
<br>

We'll proceed by clicking "**Next**" ➜ until we've finished **Installing DUO Security** ✅

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/83f1cc48-3459-46b3-9394-d8f7fdcad566" height="50%" width="50%" alt="9"/><br />
<br>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Step 4️⃣ - Log In as a User</h2> </summary>
<br>

Once **DUO Security is installed** ➜ log in again to the **Server 2019 VM** with the User ```Helpdesk```

<img src="https://github.com/franciscovfonseca/Setting-Up-MFA-and-Protecting-RDP/assets/172988970/91f9caf6-e704-4c65-ad22-0ceebf2d19c9" height="70%" width="70%" alt="9"/><br />

✅ Congratulations!

The Server VM will now require **Multi-Factor Authentication (MFA)** each time a user logs in using **Remote Desktop Protocol (RDP)**.

<br>

<h2></h2>

  </details>

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


