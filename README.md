<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


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
- Traffic Inspection and Analysis with Wireshark
- Evaluation and Adjustment of NSG Rules
- Traffic Generation Between VMs


<h2>Actions and Observations</h2>

<p>

  

</p>
<p>
<h4>Deployment and Configuration of Azure Virtual Machines (VMs)</h4>

![image](https://github.com/user-attachments/assets/b5bfe402-fced-4971-8f1a-9de4f1657b16)

<p>
</p>
Deploy an Azure VM running Ubuntu Server 20.04 and configure Secure Shell (SSH) for secure access.
<p>
</p>

![image](https://github.com/user-attachments/assets/1ac38b9f-cb1f-4bb7-a8be-62c90aa38f54)

</p>
Deploy a second Azure VM running Windows 10 (22H2), ensuring it is on the same virtual network as the Ubuntu server to allow easy communication between the VMs. Remote Desktop (RDP) is set up on the Windows 10 VM.

<p>
</p>
<br />

<h4>Configuration of Network Security Groups (NSGs)</h4>

![Screenshot 2025-02-25 2 59 54 PM](https://github.com/user-attachments/assets/e1051019-955b-436f-9b52-42dfdabc801f)

</p>
<p>
Network Security Groups (NSGs) are used to control the incoming and outgoing traffic for both VMs. Rules are set up for different types of connections, like SSH, RDP, DNS, and ICMP, to make sure only the right kinds of access are allowed based on the security needs. These NSGs are applied to each VM’s network interface to protect their traffic.

</p>
<br />

<p>
<h4>Traffic Inspection and Analysis with Wireshark</h4>

![image](https://github.com/user-attachments/assets/8d8bd0b7-a83e-42c7-ad7b-827306af09af)

</p>
<p>
Use RDP to connect to the Windows 10 VM from the Ubuntu server VM. Download Wireshark to observe the network traffic between the Windows 10 and Ubuntu Server VMs.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/890654e2-2947-41c4-ada9-61fb7d2f723c)

</p>
<p>
Open Wireshark to monitor the traffic between the VMs.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/4830c1d1-81d8-4049-9ca9-25f9f9fbce99)

</p>
<p>
A perpetual ping is used to constantly test the ICMP traffic between the VMs, with the network packets checked to make sure the ping messages are sent and received correctly.
</p>
<p>

<h4>Evaluation and Adjustment of NSG Rules</h4>
  
![Screenshot 2025-02-25 2 59 54 PM](https://github.com/user-attachments/assets/e1051019-955b-436f-9b52-42dfdabc801f)

The Network Security Group (NSG) rules are instated and tested to ensure the security settings are controlling the traffic as expected. 
  
![image](https://github.com/user-attachments/assets/7508ef33-d0fe-4d9a-a346-34d4bbeda160)

</p>
<p>
The NSG rules are observed and noted in Wireshark to monitor the traffic flow.
</p>
<p>

![image](https://github.com/user-attachments/assets/766ffb27-ad21-4f96-bab1-c6fadea06ab5)

</p>
<p>
Then, the NSG rules are relaxed to allow more traffic and observed again in Wireshark to see the changes. The impact of the relaxed rules is assessed by comparing the observed traffic with the previous settings.  

</p>
<br />
<p>
<h4>Traffic Generation Between VMs</h4>
 
![image](https://github.com/user-attachments/assets/accdfbc4-31a1-42b7-9c9e-73d872216e12)

</p>
<p>
Using PowerShell to log into the Ubuntu server allows for SSH traffic to be observed in Wireshark.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/84f23c09-78ec-4484-a005-7c2b735d4cf4)

</p>
<p>

Running simple commands on the Ubuntu VM, such as id, ls, and hostname, sends these commands over the network to the Windows 10 VM. The resulting packets are captured and analyzed to ensure the SSH connection is secure and the traffic flows correctly between the VMs.

</p>
<p>
  

![image](https://github.com/user-attachments/assets/c14cbe16-9703-45a7-aeb1-c6f98e83c12f)

</p>
<p>
A simple script is run to watch the DHCP process.
</p>
<p>

![image](https://github.com/user-attachments/assets/c9b786e8-e07a-4434-805d-4ae53a9e8ac8)

</p>
<p>
Wireshark captures the steps of release, discover, offer, request, and acknowledge messages.
</p>
<p>

![image](https://github.com/user-attachments/assets/4823a644-8cd6-46ef-b720-7efdb7028f63)

</p>
<p>
DNS was tested by checking if disney.com could be resolved, and the traffic was monitored in Wireshark to ensure it was working properly.
</p>
<p>

![image](https://github.com/user-attachments/assets/6315eac7-487e-4a0a-8450-23b4373540c6)

</p>
<p>
The provided IP address is also tested in a web browser to confirm it is correct.
</p>
<p>

![image](https://github.com/user-attachments/assets/877b2320-f4d5-46c7-b0a7-b934ef4128de)

</p>

<p>
Also, RDP traffic between the VMs is monitored to capture the amount of information being processed through the remote connection.

</p>
<br />
<p>

