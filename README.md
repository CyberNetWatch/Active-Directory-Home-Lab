# Active Directory Home Lab

## What’s This About?  
This project is my first attempt at setting up a **simulated corporate environment** using VirtualBox, Windows Server, and Windows 10. I wanted to learn how to configure **Active Directory**, **DHCP**, and **DNS**, and automate tasks using **PowerShell**. It’s been a fun way to get hands-on experience with enterprise IT tools and understand how everything works together.

---

### What I Learned  
- **Active Directory Basics**: Setting up a domain controller, creating users, and organizing them into groups.  
- **DHCP and DNS**: How to automatically assign IP addresses and make sure devices can find each other on the network.  
- **PowerShell Scripting**: Writing a script to create users automatically instead of doing it one by one.  
- **Troubleshooting**: Figuring out why things weren’t working (like why a client couldn’t get an IP address).  
- **Multilingual Setup**: Configuring a client in Russian to show I can work in different languages.  

---

### Tools I Used  
- **VirtualBox**: To create and manage virtual machines.  
- **Windows Server 2019**: For the domain controller, DHCP, and DNS.  
- **Windows 10**: For the client machines that joined the domain.  
- **PowerShell**: To automate boring tasks like creating users.  
- **Active Directory Users and Computers (ADUC)**: For managing users and groups.  

---

## How I Did It  

### 0. Diagram
![Diagram](screenshots/0-VirtualBox-Diagram.png)  
*This is the diagram I followed for the project. Big thanks to [@joshmadakor](https://github.com/joshmadakor) for the inspiration!*  

---

### 1. Setting Up the Domain Controller  
![Domain Controller Setup](screenshots/1-VirtualBox-server-creation-step-1.png)  
*I created a virtual machine for the domain controller using Windows Server 2019. I gave it 2GB of RAM, 3 CPUs, and 20GB of storage to make sure it runs smoothly.*  

---

### 2. Configuring Active Directory  
![Active Directory Setup](screenshots/VirtualBox-Domain-AD-DS-step-6.png)  
*I installed Active Directory and set up the domain `mydomain.com`. Then, I created some organizational units (OUs) to organize users and computers.*  

---

### 3. Setting Up DHCP  
![DHCP Configuration](screenshots/VirtualBox-DHCP-set-up-step-9.png)  
*I configured the DHCP server to automatically assign IP addresses in the range `172.16.0.100–172.16.0.200`. I left the lower IPs (like `172.16.0.1`) for the domain controller and other important devices.*  

---

### 4. Automating User Creation with PowerShell  
![PowerShell Automation](screenshots/VirtualBox-automated-creation-of-users-with-just-their-names-step-10.png)  
*I wrote a PowerShell script to create users automatically. It reads names from a file (`Names.txt`), generates usernames (like first initial + last name), and sets up accounts with secure passwords.*  

---

### 5. Joining Clients to the Domain  
![Client Domain Join](screenshots/VirtualBox-setting-up-client-step-12.png)  
*I joined a Windows 10 client (`CLIENT2`) to the domain `mydomain.com`. I set the interface to Russian to make it feel more realistic and show off my language skills!*  

---

### 6. Verifying DHCP Functionality  
![DHCP Leases](screenshots/VirtualBox-client-adress-proof-step-13.png)  
*I checked the DHCP server to make sure it was working. The client (`CLIENT2`) got an IP address (`172.16.0.101`), and I saw a temporary name (`minint-vuj5bw`) that Windows uses during setup.*  

---

### 7. Testing User Login  
![User Login](screenshots/last-screenshottttt.png)  
*I logged in as `pmesceriakov` on a domain-joined client to make sure everything worked. It felt like a real corporate environment!*  

---

## What I Got Out of This  
This project was a great way to learn the basics of Active Directory, DHCP, and PowerShell. I made mistakes along the way (like forgetting to enable the right network adapter), but I figured them out and learned a lot. It’s cool to see how all these pieces fit together in a real-world IT setup.  

---

## License  
This project is licensed under the [MIT License](LICENSE).  
