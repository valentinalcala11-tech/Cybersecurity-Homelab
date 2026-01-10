<h1>Cybersecurity Homelab</h1>


<h2>Description</h2>
In this lab, I designed and built a small enterprise style network from the ground up and used it to practice real-world system administration, networking, and security tasks, from configuring services and managing users to troubleshooting issues and identifying vulnerabilities.
<br />
<hr>
<h3>Core Technologies Learned</h3>

<ul>
  <li>Active Directory</li>
  <li>DNS</li>
  <li>DHCP</li>
  <li>RDP</li>
  <li>VPN/RRAS</li>
  <li>VMware</li>
  <li>Nessus Essentials (vulnerability scanning)</li>
</ul>
<hr>
<h2>Tools and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Command Prompt</b>
- <b>Bash</b>
- <b>VMware Workstation</b>
- <b>Nessus Essentials</b>
- <b>Windows Administrative Tools</b>
- <b>ipconfig / nslookup / netstat</b>
- <b>Nano / Vi</b>

<h2>Guides/References Used</h2>
-<a href="https://cybercademy.org/cybersecurity-homelab-project/" target="_blank">
  Cybersecurity Homelab Project 
</a>
(with modifications)

-<a href="https://www.lepide.com/blog/top-10-most-important-group-policy-settings-for-preventing-security-breaches/" target="_blank">
  GPO Policy Settings
</a>

<h2>Environments Used </h2>

- <b>Windows 10 enterprise VM (Domain Client)</b>
- <b>Kali Linux VM (Domain Client)</b>
- <b>Windows XP VM (Test Machine)</b>
- <b>Windows Server 2016 VM (Domain Controller)</b>

<h2>Before You Start</h2>

- <b>This lab was built solely through Windows 11 laptop. (Make sure your CPU can support virtualization via BIOS)</b>
- <b>I originally tested a VNC/SSH for remote access as per the guide, but ultimately never ended up using it since it's not required for the final setup.</b>
- <b>Some steps may differ depending your choice of the linux distro or OS you implement.</b>
- <b>Screenshots are included to show my process, however, not every step is required.</b>

<h2>Home-Lab Walkthrough:</h2>

<p align="center">
Install VMWare and a Linux Distribution using an ISO: <br/>
<img src="images/Screenshot (5).png" height="80%" width="80%" />
<br />
<br />
Create a Windows server VM using an ISO, select the disk, remove the floppy disk if it appears:  <br/>
<img src="images/Screenshot 2025-12-20 115217.png" height="80%" width="80%" />
<br />
<br />
Install Active Directory on Windows 2016 Server: <br/>
<img src="images/Screenshot 2025-12-20 195158.png" height="80%" width="80%" />
<br />
<br />
Confirm your selection and check for prereqs:  <br/>
<img src="images/Screenshot 2025-12-20 195458.png" height="80%" width="80%" />
<br />
<br />
Select a new zone for the DNS:  <br/>
<img src="images/Screenshot 2025-12-21 111743.png" height="80%" width="80%" />
<br />
<br />
Create a Reverse Lookup Zone for DNS:  <br/>
<img src="images/Screenshot 2025-12-21 111942.png" height="80%" width="80%" />
<br />
<br />
Create an IP address pool range:  <br/>
<img src="images/Screenshot 2025-12-21 113411.png" height="80%" width="80%" />
<br />
<br />
Install Windows 10 enterprise:  <br/>
<img src="images/Screenshot 2025-12-21 115609.png" height="80%" width="80%" />
<br />
<br />
Configure VMNet1 (virtual network) and turn off local dhcp client:  <br/>
<img src="images/Screenshot 2025-12-21 122659.png" height="80%" width="80%" />
<br />
<br />
Configure auto ipv4 settings to test DHCP on Windows 10 enterprise:  <br/>
<img src="images/Screenshot 2025-12-21 125448.png" height="80%" width="80%" />
<br />
<br />
Verify its connection in the AD:  <br/>
<img src="images/Screenshot 2025-12-21 125753.png" height="80%" width="80%" />
<br />
<br />
Connect the Windows 10 VM to the domain:  <br/>
<img src="images/Screenshot 2025-12-21 130402.png" height="80%" width="80%"/>
<br />
<br />
Create a user in AD and login through the Windows 10 VM:  <br/>
<img src="images/Screenshot 2025-12-21 130759.png" height="80%" width="80%" />
<br />
<br />
Create a OU and add recommended GPO Policy settings:  <br/>
<img src="images/Screenshot 2025-12-22 121926.png" height="80%" width="80%" />
<br />
<br />
Enable ethernet connection state on Linux VM:  <br/>
<img src="images/Screenshot 2025-12-23 052700.png" height="80%" width="80%" />
<br />
<br />
Download DHClient:  <br/>
<img src="images/Screenshot 2025-12-23 053812.png" height="80%" width="80%" />
<br />
<br />
Download Active Directory Packages:  <br/>
<img src="images/Screenshot 2025-12-23 064113.png" height="80%" width="80%" />
<br />
<br />
Use Nano/Vi to change the Linux VM hostname by appending mylab.local to join AD domain:  <br/>
<img src="images/Screenshot 2025-12-23 073709.png" height="80%" width="80%" />
<img src="images/Screenshot 2025-12-24 012948.png" height="80%" width="80%" />
<br />
<br />
Install RDP services through AD:  <br/>
<img src="images/Screenshot 2025-12-24 014317.png" height="80%" width="80%" />
<br />
<br />
Deploy the RDP Service:  <br/>
<img src="images/Screenshot 2025-12-24 014452.png" height="80%" width="80%" />
<br />
<br />
Configure a certificate for the RDP server:  <br/>
<img src="images/Screenshot 2025-12-24 021313.png" height="80%" width="80%" />
<br />
<br />
Verify the RDP connnection from Windows 10 VM using Windows 2016 server ipv4:  <br/>
<img src="images/Screenshot 2025-12-24 024137.png" height="80%" width="80%" />
<img src="images/Screenshot 2025-12-24 025400.png" height="80%" width="80%" />
<br />
<br />
Install VPN/RRAS through Active Directory:  <br/>
<img src="images/Screenshot 2025-12-26 154532.png" height="80%" width="80%" />
<br />
<br />
Add the DirectAccess and RAS service:  <br/>
<img src="images/Screenshot 2025-12-26 154618.png" height="80%" width="80%" />
<br />
<br />
Deploy the VPN only:  <br/>
<img src="images/Screenshot 2025-12-26 155056.png" height="80%" width="80%"/>
<br />
<br />
Choose a custom configuration:  <br/>
<img src="images/Screenshot 2025-12-26 155217.png" height="80%" width="80%"/>
<br />
<br />
Start the VPN Service:  <br/>
<img src="images/Screenshot 2025-12-26 155327.png" height="80%" width="80%"/>
<br />
<br />
Add a VPN connection on linux machine using PTPP and connect:  <br/>
<img src="images/Screenshot 2025-12-28 061953.png" height="80%" width="80%" />
<br />
<br />
Download Nessus on Linux VM:  <br/>
<img src="images/Screenshot 2025-12-28 155026.png" height="80%" width="80%" />
<br />
<br />
Download extracted packages:  <br/>
<img src="images/Screenshot 2025-12-28 160737.png" height="80%" width="80%" />
<br />
<br />
Go to the linux browser and login through "https://localhost:8834/", Register for essentials:  <br/>
<img src="images/Screenshot 2025-12-28 160841.png" height="80%" width="80%" />
<br />
<br />
After creating a login and downlading nessus plugins, you should see the Nessus dashboard:  <br/>
<img src="images/Screenshot 2025-12-28 162036.png" height="80%" width="80%" />
<br />
<br />
Install a vulnerable host (Windows XP) using VMWare:  <br/>
<img src="images/Screenshot 2025-12-30 090520.png" height="80%" width="80%" />
<img src="images/Screenshot 2025-12-30 094844.png" height="80%" width="80%" />
<br />
<br />
Use Nessus to discover host and run a network vulnerability scan using WinXP VM ipv4:  <br/>
<img src="images/Screenshot 2025-12-30 095455.png" height="80%" width="80%"/>
<img src="images/Screenshot 2025-12-30 095730.png" height="80%" width="80%" />
<br />
Make sure to allow ICMP echo (pings) from Windows XP VM using admin account:  <br/>
<img src="images/Screenshot 2025-12-30 103620.png" height="80%" width="80%" />
<br />
Finally, observe the findings. Not many due to it being a VM:  <br/>
<img src="images/Screenshot 2025-12-30 111012.png" height="80%" width="80%" />
</p>

<h2 style="text-align: center;"> Conclusion</h2>
<ul>This homelab project was built to simulate a small enterprise environment with services like centralized user management, group policies, VPN access, and basic security tools. Most of the setup went smoothly once the core systems were in place, but the VPN caused several issues related to routing, authentication, and client connectivity that took time to troubleshoot. Fixing these problems helped me better understand how VPNs interact with firewalls, user permissions, and different operating systems. Through this project, I learned how individual services depend on each other and how small misconfigurations can break connectivity. The lab also showed areas that could be improved, such as clearer VPN documentation, stronger access controls, and better testing. Overall, this project helped strengthen my troubleshooting skills and gave me practical experience with real-world networking and security concepts.</ul>
