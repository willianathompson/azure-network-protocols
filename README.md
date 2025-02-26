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

![image](https://github.com/user-attachments/assets/1ac38b9f-cb1f-4bb7-a8be-62c90aa38f54)
![image](https://github.com/user-attachments/assets/b5bfe402-fced-4971-8f1a-9de4f1657b16)

The project successfully deployed two Azure Virtual Machines (VMs), one running Windows 10 (22H2) and the other running Ubuntu Server 20.04. Remote Desktop (RDP) was configured for the Windows 10 VM, and SSH was set up for the Ubuntu Server VM, enabling secure administrative access to both VMs. Both VMs were connected to the same virtual network, ensuring seamless communication between them.
</p>
<br />

<p>

![Screenshot 2025-02-25 2 59 54 PM](https://github.com/user-attachments/assets/e1051019-955b-436f-9b52-42dfdabc801f)

</p>
<p>
Network Security Groups (NSGs) were created and applied to control inbound and outbound traffic for both VMs. Specific rules were defined for protocols like SSH, RDP, DNS, and ICMP, ensuring that access was granted appropriately based on the project’s security requirements. These NSGs were applied at the network interface level on both VMs to secure their traffic according to the established rules.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/8d8bd0b7-a83e-42c7-ad7b-827306af09af)
![image](https://github.com/user-attachments/assets/0d0c16a7-4d74-4e9c-a754-edaeaedd0710)
capture observe network traffic
![image](https://github.com/user-attachments/assets/890654e2-2947-41c4-ada9-61fb7d2f723c)
download wireshark, traffic observed
</p>
<p>
Traffic was generated between the Windows 10 and Ubuntu Server VMs to test connectivity and validate the security configurations. SSH was used to remotely manage both VMs, and RDP was accessed for Windows remote desktop connections from the Ubuntu VM. A basic web server was set up on the Ubuntu VM to test HTTP/S access from the Windows 10 VM. DNS resolution and ICMP (ping) connectivity were also tested between the two VMs.
</p>
<br />

<p>
window ICMP traffic
  
![image](https://github.com/user-attachments/assets/3ca9ae4d-40c0-4a01-8711-27bde450c709)
ping windows to linux server IP
![image](https://github.com/user-attachments/assets/4dce6460-50d1-4585-878e-5f38feff6499)
![image](https://github.com/user-attachments/assets/3957c179-2b4c-4f96-b7b3-af0ba4667fb7)
observe ping payload and traffic between hosts
![image](https://github.com/user-attachments/assets/da688141-ecc0-4926-bb9f-efbdcc459fb1)
observe source and desination IP
![image](https://github.com/user-attachments/assets/6c359dd5-c658-4754-8898-d7d2faf13be1)
perpetual ping 
![image](https://github.com/user-attachments/assets/4830c1d1-81d8-4049-9ca9-25f9f9fbce99)

tested ICMP traffic (ping)
</p>
<p>
Wireshark was installed and used on both VMs to capture and analyze network traffic. Detailed packet information was captured for protocols like TCP/IP, SSH, HTTP/S, and ICMP, verifying that the data flow between the VMs was correct. The network packets were examined to ensure proper communication and confirm that the security rules were being followed.
</p>
<br />
<p>

start packet capture and filter for ssh traffic
![image](https://github.com/user-attachments/assets/92df24ec-3e94-4cfc-a51c-58f3af561135)
connect to linux vm ssh filter 
![image](https://github.com/user-attachments/assets/accdfbc4-31a1-42b7-9c9e-73d872216e12)
![image](https://github.com/user-attachments/assets/724795e4-c949-4e37-94a5-6bb4356a934a)
![image](https://github.com/user-attachments/assets/07c3be5f-408c-4c13-b63b-40ca4bbc1a4b)
SSH connection closed
![image](https://github.com/user-attachments/assets/84f23c09-78ec-4484-a005-7c2b735d4cf4)

observed SSH traffice
</p>
<p>
After reviewing the Wireshark traffic analysis, it was confirmed that the NSG rules were correctly implemented to permit or block the necessary traffic. Any adjustments to the NSG configurations were made to ensure only authorized traffic was allowed between the VMs. The final step ensured that all required traffic was flowing securely and efficiently, in line with the project’s security protocols.
</p>
<p>
  
observe dhcp traffic
run scipt
![image](https://github.com/user-attachments/assets/c14cbe16-9703-45a7-aeb1-c6f98e83c12f)
release-discover-offer-reequest-ack
![image](https://github.com/user-attachments/assets/c9b786e8-e07a-4434-805d-4ae53a9e8ac8)
DNS observe
![image](https://github.com/user-attachments/assets/4823a644-8cd6-46ef-b720-7efdb7028f63)
![image](https://github.com/user-attachments/assets/6315eac7-487e-4a0a-8450-23b4373540c6)
rdp tcp.port == 3389
![image](https://github.com/user-attachments/assets/877b2320-f4d5-46c7-b0a7-b934ef4128de)
 observe dhcp dns and rdp traffice 
</p>
The lab project successfully deployed the Azure VMs, configured Network Security Groups to secure traffic, and used Wireshark for network analysis to ensure that the communication between the VMs adhered to the specified security requirements.
</p>
<br />
<p>

