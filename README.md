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
  
![Image](https://github.com/user-attachments/assets/7e4c4ef2-919a-46cf-bc46-f8582d05232a)
  
</p>
Once we have it installed, we can launch the application and begin observing network protocol traffic.
</p>
<br />

Starting of with ICMP, open the application and filter for ICMP traffic in the search bar. ICMP is used by network devices to send error messages and check connectivity.


<img width="491" alt="Image" src="https://github.com/user-attachments/assets/d169b367-3ace-4b23-8c43-d06cac9249c5" />

<p>
As we can see in the image above no packets are being captured in wireshark lets change that by utilizing the ping command to send ICMP traffic to the IP address of the Linux machine.
  </p>
<br />

  <img width="485" alt="Image" src="https://github.com/user-attachments/assets/f699e2a7-d897-4aea-85ef-3d603baa79a0" />

We can view each packet sent while pinging the machine in Wireshark where it it displays the ICMP traffic for our analysis.
</p>
<br />

Next we will use create a new rule to deny ICMP requests on the Ubuntu VMs Network Security Group. 

<img width="296" alt="Image" src="https://github.com/user-attachments/assets/cfcd15a1-e07a-42e1-9064-be112b26aa34" />
</p>
<br />

With this rule in place we will check Wireshark to observe that the pings no longer receive replies and in PowerShell, we see a message saying "Request Timed Out." 

<img width="611" alt="Image" src="https://github.com/user-attachments/assets/ecc6d407-63a8-4984-8f22-7753b639c382" />

</p>
<br />
After making these observations we will now delete the rule from the network security group. 

<img width="587" alt="Image" src="https://github.com/user-attachments/assets/6fabddbc-cecb-4dce-9f02-c8faae03ac03" />


</p>
<br />

Next we will observe 

