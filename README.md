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
Install VMWare and a Linux Distribution: <br/>
<img src="https://cdn.discordapp.com/attachments/1456367844487987378/1456368248621764728/w1.png?ex=69581c20&is=6956caa0&hm=67042b8e7a9e9f8024f0c6463820ec1932340b316620747db6421def4abfaef5" height="80%" width="80%" alt=""/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
