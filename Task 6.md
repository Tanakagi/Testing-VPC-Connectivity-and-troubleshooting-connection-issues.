# Task 6: Testing connectivity between my EC2 instances

<b>• I went back to the C2 console in a new tab.</br>
<b>• Selected Network Project Private Server.</br>
<b>• and copied my private server's Private IPv4 address. 10.0.1.170:</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/899764c498f01ef48d5e83189502a053e5de3e90/Project%20Images/image29.png" height="80%" width="80%" />
</br>
</br>

<b>• I Switched back to the EC2 Instance Connect tab.</br>
<b>• and used the ping command to test connectivity by pinging my Private server.</br>
<b>•I didn't get any replies, which tells me that there was a problem with the connection.</br>
<b>My private server was probably blocking ICMP (Internet Control Message Protocol) traffic which is usually blocked by default.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image30.png" height="60%" width="60%" />
</br>
</br>

### To resolve this connectivity error, I investigate whether the Network Project Private Server is allowing ICMP traffic.

<b>• I select Network Project Private Subnet.</br>
<b>• I investigated the Route tables and Network ACL tabs of my private subnet.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image31.png" height="80%" width="80%" />
</br>
</br>


<b>The Network ACL tab indicated that all traffic inbound and outbound are denied.</br> 
<b>This means even if the route table correctly directs the ping to the Network Project Private Server, the network ACL is checking the ping traffic at the entrance of the private subnet.</br>
<b>If it finds that ICMP traffic is not allowed, it stops the ping there.</br>
</br>
</br>

<b>• I resolved this by adding a new rule to let my Public Server ping my Private Server under Edit inbound rules under the NACL.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image32.png" height="80%" width="80%" />
</br>
</br>

<b>• I did the same for my outbound rules of the NACL.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/33.png" height="80%" width="80%" />
</br>
</br>

<b>• I then checked my Security group to see if they allow for ICMP - IPv4.</br>
<b>• I then discovered that both inbound and outbound rules did not.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image34.png" height="80%" width="80%" />
</br>
</br>

<b>• I then added a rule for both inbound and outbound traffic to allow for ICMP - IPv4.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image35.png" height="80%" width="80%" />
</br>
</br>

<b>• After adding the rules I went back to the EC2 Instance Connect tab that connected to my Public Server.</br>
<b>• The multiple new lines appearing in your terminal were a sign of successful communication between the two EC2 instances.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/b447e5fa74876d823349e9a43b5affe982a33003/Project%20Images/image36.png" height="50%" width="50%" />
</br>
</br>











