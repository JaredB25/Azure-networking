<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this experiment, we use Wireshark to analyze different types of network traffic going to and coming from Azure Virtual Machines. We also explore Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (ICMP, SSH, DNS, DHCP, RDP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 22.04

<h2>Procedure</h2>

* Using Azure create two virtual machines one running the Windows OS and the other running the Ubuntu linux distribution.
* Install the Wireshark application on the windows virtual machine. 
* Generate various types of newtwork traffic icluding : ICMP, SSH, DNS, DHCP and RDP. Observe the network traffic by capturing packets with Wireshark.
* Configure a Network Security Group using Azure and observe the effects on network traffic with Wireshark.

<h2>Actions and Observations</h2>

<p>
  First we create and properly configure the Virtual Machines
  
<img width="775" alt="Image" src="https://github.com/user-attachments/assets/40c8266f-6a4b-4595-a937-b55425b07da6" />

<img width="746" alt="Image" src="https://github.com/user-attachments/assets/188a26e9-351a-4a8d-8f51-b38fabf95608" />


</p>
<p>
The two virtual machines were created in the in the Azure portal: two virtual CPUs apiece, one running a Linux image and the other running a Windows 10 Pro image.  During setup, make sure both virtual machines are connected to the same virtual network.  
</p>

<br />
Next we will use the Remote desktop windows appliction to log into  our Windows 10 virtual machine.

<p>
  
![Image](https://github.com/user-attachments/assets/95292757-87d2-4b27-a17e-e135dd8563d2)

</p>

<p>
Using the public IP address of the machine along with the  credientials we configured during the set up process we will be able to log into the Windows VM. 
</p>
<br />
Once we are on the windows VM naviagte to https://www.wireshark.org to download and install Wireshark.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
