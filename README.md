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
<img src="https://cdn.discordapp.com/attachments/1456367844487987378/1456368248621764728/w1.png?ex=6960ade0&is=695f5c60&hm=4c71631df76f5bfbf152890b8b5ce5f31c9d9004942844950383ff3360dce174&" height="80%" width="80%" alt=""/>
<br />
<br />
Create a Windows server VM using an ISO, select the disk, remove the floppy disk if it appears:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1451995757728239818/Screenshot_2025-12-20_115217.png?ex=6959576d&is=695805ed&hm=cc51de3bbc88f99f39af3ec0d98a9da1eaf65e7f4ccdc28d92c3ccc263c1768a" height="80%" width="80%" />
<br />
<br />
Install Active Directory on Windows 2016 Server: <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1451991491546451978/image.png?ex=696093b4&is=695f4234&hm=f04151678218772d654c166d95cf749d94ffdffc0f2b719db3e2c0af444050d9&" height="80%" width="80%" />
<br />
<br />
Confirm your selection and check for prereqs:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452332347977629999/Screenshot_2025-12-20_195458.png?ex=69593f66&is=6957ede6&hm=1da86a166899f7e54b4a82e7ea8ffe96758da83754644383fa6c7c4328e28061" height="80%" width="80%" />
<br />
<br />
Select a new zone for the DNS:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452349350566166720/image.png?ex=69594f3c&is=6957fdbc&hm=ffd1761d29ac4f847db60b40ab96763d1f485711b0ea8fc27034f3d3ab8e05d8" height="80%" width="80%" />
<br />
<br />
Create a Reverse Lookup Zone for DNS:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452349350566166720/image.png?ex=69608f7c&is=695f3dfc&hm=0bdfedc9d022f99f6afdc46a183a08e38cbb528189ac3b1bbc4d47470d871928&" height="80%" width="80%" />
<br />
<br />
Create an IP address pool range:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452353513358102732/image.png?ex=6959531d&is=6958019d&hm=62a3a8dd08329f768d3b20e68390fb9cead379f157bce4fb409f8c42c8560a9a" height="80%" width="80%" />
<br />
<br />
Install Windows 10 enterprise:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452359028612272311/image.png?ex=6960987f&is=695f46ff&hm=2fcf483e1d650efff4c49b3bb60de233daaf57a714152ba0076350f190414699&" height="80%" width="80%" />
<br />
<br />
Configure VMNet1 (virtual network) and turn off local dhcp client:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452366780474462381/image.png?ex=69609fb8&is=695f4e38&hm=06fe51fa9e8a7c48f840c907b6c0845bbee4f61fababb6dfcfa35645c72ad0b9&" height="80%" width="80%" />
<br />
<br />
Configure auto ipv4 settings to test DHCP on Windows 10 enterprise:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452373845255131157/image.png?ex=6959660c&is=6958148c&hm=a86684db70b1d61a30e39b1c60f6e7a1a16136b3c28dbc66e8235a74032172e6" height="80%" width="80%" />
<br />
<br />
Verify its connection in the AD:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452374567686508717/image.png?ex=695966b8&is=69581538&hm=a1624deff8d2cb110ecf57ffacfab5b8dcc88a59aa6595d9e453c0abd72fea9b" height="80%" width="80%" />
<br />
<br />
Connect the Windows 10 VM to the domain:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452376117108412566/image.png?ex=6958bf6a&is=69576dea&hm=5801ff6dd404b8694bfd26175be90050a5675850bb23ae2793a4da6e130015ff" height="80%" width="80%"/>
<br />
<br />
Create a user in AD and login through the Windows 10 VM:  <br/>
<img src="https://cdn.discordapp.com/attachments/1451059973282074765/1452377105613590729/image.png?ex=6958c055&is=69576ed5&hm=44db9a01b45c6081c6e82d08b539d3bdf37ea9975432ca8c68b28e51fb257a21" height="80%" width="80%" />
<br />
<br />
Create a OU and add recommended GPO Policy settings:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1452716845697335417/image.png?ex=695953fe&is=6958027e&hm=96d7f1ebd6e4814368c33c2da1bd92a227e903d48644001361a40b6593464ac8" height="80%" width="80%" />
<br />
<br />
Enable ethernet connection state on Linux VM:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1452986280894922822/image.png?ex=6960e66c&is=695f94ec&hm=b41dd8fe8aeedea3e32e934c73adf205d8fccbd0be4b12da44c23beb75d4bd7e&" height="80%" width="80%" />
<br />
<br />
Download DHClient:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1452988698382696449/image.png?ex=6958ffac&is=6957ae2c&hm=0fed44532c38a4d9683883c8901a0dfa6d6d569c861e567e1faf1757a2c17a10" height="80%" width="80%" />
<br />
<br />
Download Active Directory Packages:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453004578017644676/image.png?ex=69604eb6&is=695efd36&hm=9ec2c6512cffabaf799eda5aa05f4fb2afb2419370dd4cc2f324cf31de3d0537&" height="80%" width="80%" />
<br />
<br />
Use Nano/Vi to change the Linux VM hostname by appending mylab.local to join AD domain:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453018636796166356/image.png?ex=69591b8e&is=6957ca0e&hm=a671547935d302bb45aa3ff094cf6954d245fac438c59fd66cc992a5e8a8ddc7" height="80%" width="80%" />
<br />
<br />
Install RDP services through AD:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453291961996808222/image.png?ex=6958c89c&is=6957771c&hm=92fffafef0d7fe02efc8c4e7dc9b2e44c6cff066785245be3d2369a53c374bbd" height="80%" width="80%" />
<br />
<br />
Deploy the RDP Service:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453292994806677534/image.png?ex=6958c992&is=69577812&hm=96519b884045935093a1854071c562fb63f39a8d4d87d0c4239fe7d4028890ec" height="80%" width="80%" />
<br />
<br />
Configure a certificate for the RDP server:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453299496326004737/image.png?ex=6958cfa0&is=69577e20&hm=4e3c8698bfe7e37b196e7f94fab885d23a17eb3605b166a68b62a2cfe44eb781" height="80%" width="80%" />
<br />
<br />
Verify the RDP connnection from Windows 10 VM using Windows 2016 server ipv4:  <br/>
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453306969971757056/image.png?ex=6958d696&is=69578516&hm=06286ca1d640d2f3f6f508addf4e0bfbabc2fdafbfdb9659e73c823a1c7aafc3" height="80%" width="80%" />
<img src="https://cdn.discordapp.com/attachments/1452715517545808013/1453310215217741845/image.png?ex=6960c29c&is=695f711c&hm=3261ef9e64586b69a37917bedc834ae198f68bc849aa26bfc611b1ca10efb473&" height="80%" width="80%" />
<br />
<br />
Install VPN/RRAS through Active Directory:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454228173448544306/image.png?ex=6958e4c6&is=69579346&hm=fb8c18b222274e67cee258f893d08ef2c30a6415d89f399336fab5573cb9da4e" height="80%" width="80%" />
<br />
<br />
Add the DirectAccess and RAS service:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454228691004428389/image.png?ex=6958e542&is=695793c2&hm=9b7e64e73c19dca8fa5084f3e683606a02d5149a5f11645b781c6aed569f0d41" height="80%" width="80%" />
<br />
<br />
Deploy the VPN only:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454230049854062672/image.png?ex=6958e686&is=69579506&hm=ca13e72ebcb2fd76bf732e8586ff3d0776b31d7ef6709d2036b17b05ed5b0d80" height="80%" width="80%"/>
<br />
<br />
Choose a custom configuration:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454230400590286869/image.png?ex=6960cfd9&is=695f7e59&hm=a8c9bb88b23281315eaf29f73054b2691fd2756d16a778de65f876088deacc92&" height="80%" width="80%"/>
<br />
<br />
Start the VPN Service:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454230682510430502/image.png?ex=6960d01d&is=695f7e9d&hm=bb4986b2cc5cb458bf58563d1d04ebd8bafcd040ba24f35a4f07ed795374517b&" height="80%" width="80%"/>
<br />
<br />
Add a VPN connection on linux machine using PTPP and connect:  <br/>
<img src="https://cdn.discordapp.com/attachments/1453310711404171328/1454811105947025561/image.png?ex=6959096c&is=6957b7ec&hm=aca054256d635f547e57d75d9b871715b0fd99d29518bbb47dd450fb17c8a6b2" height="80%" width="80%" />
<br />
<br />
Download Nessus on Linux VM:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1454954710011220092/image.png?ex=6958e66a&is=695794ea&hm=032bff1f445fb3eef8b22bfd8da541a004d5f05039cbe76d7d8a35b40474d136" height="80%" width="80%" />
<br />
<br />
Download extracted packages:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1454959031574728834/image.png?ex=6960d370&is=695f81f0&hm=c142fe6c843229bdc47ab32580da2812bc2f9c2f2958e86260294a34d2bde6c3&" height="80%" width="80%" />
<br />
<br />
Go to the linux browser and login through "https://localhost:8834/", Register for essentials:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1454960361563230271/image.png?ex=6958ebae&is=69579a2e&hm=f5a77436e78d52640d62293d8918ff291f0c9b647009ff1b4feff4cac9629162" height="80%" width="80%" />
<br />
<br />
After creating a login and downlading nessus plugins, you should see the Nessus dashboard:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1454962332869591201/image.png?ex=6958ed84&is=69579c04&hm=d6340b45d364bf05b52ac1a3d8320f9c19262c470bc73c1f4599771916e82dd5" height="80%" width="80%" />
<br />
<br />
Install a vulnerable host (Windows XP) using VMWare:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455577645998669918/image.png?ex=69593052&is=6957ded2&hm=a892bb0ed707d7e6dbbff50504f57a0e6962995f314dd294b80a84084f832563" height="80%" width="80%" />
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455588979125518523/image.png?ex=69593ae0&is=6957e960&hm=4fbcd65e51f2b59e7a1b6fa6ee8c9ccdfc590c4ad43e3ef9670fbe1dad23ba9a" height="80%" width="80%" />
<br />
<br />
Use Nessus to discover host and run a network vulnerability scan using WinXP VM ipv4:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455590131724587271/image.png?ex=69593bf2&is=6957ea72&hm=2ad58383ea61795fde63253e02b6e7eb5473fa6b165a08ce238f4057f6d953b4" height="80%" width="80%"/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455604189915775143/image.png?ex=6959490a&is=6957f78a&hm=bf48af06f1c8eb5c59d423747bf06230204703c12d1904c02f0ea1d8cdab4849" height="80%" width="80%" />
<br />
Make sure to allow ICMP echo (pings) from Windows XP VM using admin account:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455600461582307348/image.png?ex=69594591&is=6957f411&hm=d47f7574efa68e843dc9cbf2196d9c254900c3c6beb4755945de9df8ab3ac7eb" height="80%" width="80%" />
<br />
Finally, observe the findings. Not many due to it being a VM:  <br/>
<img src="https://cdn.discordapp.com/attachments/1454949151035883612/1455608974253621368/image.png?ex=69608dbf&is=695f3c3f&hm=1d7fe6a38f39c02768c1564bb3834f8cfe7848247cd930c17d97ae9470253673&" height="80%" width="80%" />
</p>

<h2 style="text-align: center;"> Conclusion</h2>
<ul>This homelab project was built to simulate a small enterprise environment with services like centralized user management, group policies, VPN access, and basic security tools. Most of the setup went smoothly once the core systems were in place, but the VPN caused several issues related to routing, authentication, and client connectivity that took time to troubleshoot. Fixing these problems helped me better understand how VPNs interact with firewalls, user permissions, and different operating systems. Through this project, I learned how individual services depend on each other and how small misconfigurations can break connectivity. The lab also showed areas that could be improved, such as clearer VPN documentation, stronger access controls, and better testing. Overall, this project helped strengthen my troubleshooting skills and gave me practical experience with real-world networking and security concepts.</ul>
