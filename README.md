<h1>Active DIrectory Lab</h1>

<p align="center">
<img src="https://valto.co.uk/wp-content/uploads/2023/05/microsoft-azure-1.png" height="50%" width="50%"/>

<h2>Description</h2>

Project consists in: <br> 

- Creating two VMs, one server and one client on a network with two subnets 
- Using PowerShell to Install ACDC and a Forest
- Joining a computer to the domain
- Create a new user and login with it through the client machine
<h2>Environments and Technologies Used</h2>

- <b>Microsoft Azure</b> 
- <b>Remote Desktop</b>
- <b>PowerShell</b> 
- <b>Active Directory Domain Services</b>

<h2>Operating Systems used </h2>

- <b>Windows Server 2022</b>
- <b>Windows 10</b> (22H2)

<h2>Deployment and configuring walk-through:</h2>


First we are starting with the creation of our network named Labnetwork with an address range of 192.168.0.0/23 which will give our network a total of 512 addresses. We will split our network in 2 subnets. The first range 192.168.0.0/24 will be dedicated to the servers and the other one 192.168.1.0/24 to the hosts.<br/>
 <br/> 
<p align="center">
<img src="https://imgur.com/nFREDwV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 <br />
<br />
We then created our virtual machines: Labserver running Windows Server 2022, and Labuser running Windows 10, each auto-configured with their respective public and private IP addresses. :  <br/> <br>
<p align="center">
<img src="https://imgur.com/g73k5Io.png" height="80%" width="80%" /><img src="https://imgur.com/1v2bNZP.png" height="80%" width="80%" />
</p>
<br />
<br />
Next, we'll configure the server's private IP address to use a static assignment instead of a dynamic one. <br/> <br>
<p align="center">
<img src="https://imgur.com/Xz2d4oW.png" height="80%" width="80%" />
</p>
<br />
<br />
We’ll do this by creating a new network interface (NIC) for the Labserver machine. We'll select the intended subnet, set the IP assignment to 'Static', and assign the address 192.168.0.5.<br/><br>
<p align="center">
<img src="https://imgur.com/hKZi2DZ.png" height="80%" width="80%" />
</p>
<br />
<br />
After creating it, we'll edit the IP configuration of our new NIC to associate a public IP address provided by Azure.  <br/><br>
<p align="center">
<img src="https://imgur.com/CwqSzsx.png" height="80%" width="80%" />
<p/>
<br />
<br />
Next, we’ll access each VM and run ipconfig to verify their network configurations. <br/><br>
<p align="center">
<img src="https://imgur.com/8ceD2Oq.png" height="80%" width="80%" /><img src="https://imgur.com/XZ8GLlW.png" height="80%" width="80%" />
</p>
<br />
<br />
To ensure connectivity we will try to ping Server from the Client. At first the ping will not work correctly. We need to create a new firewall rule on Labserver-DC to allow ICMPv4 traffic, both inbound and outbound, and then repeat the same for the Client VM. Now we can ping Labserver-DC successfully from Labuser. <br/><br>
<p align="center">
<img src="https://imgur.com/t5loLK2.png" height="80%" width="80%" /><img src="https://imgur.com/RkefCsw.png" height="80%" width="80%" /><img src="https://imgur.com/lLF6vrL.png" height="80%" width="80%" />
</p>
<br />
<br />
Next, we'll configure the IP settings on the Server machine and set the DNS server to point to itself. And we will also change the DNS on our VNET in Azure. <br/><br>
<p align="center">
<img src="https://imgur.com/bz6NnBn.png" height="40%" width="40%" /> <br> <img src="https://imgur.com/iNnAHp7.png" height="40%" width="40%" />
</p>
<br />
<br />
At this stage, we’ll open an elevated PowerShell and we will use the command **Install-WindowsFeature AD-Domain-Services -IncludeManagementTools** to install Active Directory Domain Services and set up a new forest. <br/><br>
<p align="center">
<img src="https://imgur.com/FYyEF6R.png" height="80%" width="80%" /><img src="https://imgur.com/3MLi6Yb.png" height="80%" width="80%" /><img src="https://imgur.com/IE21nLp.png" height="80%" width="80%" /><img src="https://imgur.com/bz6NnBn.png" height="80%" width="80%" />
</p>
<br />
<br />
 
 
 
 
 
 
 
 
 <!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
