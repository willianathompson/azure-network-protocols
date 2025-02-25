<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Deployment and Configuration of Azure Virtual Machines (VMs)
- Configuration of Network Security Groups (NSGs)
- Traffic Generation Between VMs
- Traffic Inspection and Analysis with Wireshark
- Evaluation and Adjustment of NSG Rules

<h2>Actions and Observations</h2>

<p>

  

</p>
<p>
The project successfully deployed two Azure Virtual Machines (VMs), one running Windows 10 (22H2) and the other running Ubuntu Server 20.04. Remote Desktop (RDP) was configured for the Windows 10 VM, and SSH was set up for the Ubuntu Server VM, enabling secure administrative access to both VMs. Both VMs were connected to the same virtual network, ensuring seamless communication between them.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Network Security Groups (NSGs) were created and applied to control inbound and outbound traffic for both VMs. Specific rules were defined for protocols like SSH, RDP, HTTP/S, DNS, and ICMP, ensuring that access was granted appropriately based on the project’s security requirements. These NSGs were applied at the network interface level on both VMs to secure their traffic according to the established rules.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Traffic was generated between the Windows 10 and Ubuntu Server VMs to test connectivity and validate the security configurations. SSH was used to remotely manage both VMs, and RDP was accessed for Windows remote desktop connections from the Ubuntu VM. A basic web server was set up on the Ubuntu VM to test HTTP/S access from the Windows 10 VM. DNS resolution and ICMP (ping) connectivity were also tested between the two VMs.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Wireshark was installed and used on both VMs to capture and analyze network traffic. Detailed packet information was captured for protocols like TCP/IP, SSH, HTTP/S, and ICMP, verifying that the data flow between the VMs was correct. The network packets were examined to ensure proper communication and confirm that the security rules were being followed.
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After reviewing the Wireshark traffic analysis, it was confirmed that the NSG rules were correctly implemented to permit or block the necessary traffic. Any adjustments to the NSG configurations were made to ensure only authorized traffic was allowed between the VMs. The final step ensured that all required traffic was flowing securely and efficiently, in line with the project’s security protocols.
</p>
<p>
</p>
The lab project successfully deployed the Azure VMs, configured Network Security Groups to secure traffic, and used Wireshark for network analysis to ensure that the communication between the VMs adhered to the specified security requirements.
</p>
<br />
<p>

