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
<img src="https://imgur.com/TL5wJEZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 <br />
<br />
Then we create out VMs :  <br/> <br>
<p align="center">
<img src="https://imgur.com/7IHbJhG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><img src="https://imgur.com/OFrd2u5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
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


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
