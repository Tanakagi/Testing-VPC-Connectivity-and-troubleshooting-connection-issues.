# Task 4: Launching an EC2 instance in the Network Project Private Subnet.

<b>• I repeated the previous steps with the following differences.</br>
<b>• I Disabled Auto-assign public IP.</br>
<b>• Selected the Network Project Private Subnet.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/6c7c1e72fbe191792337121515a698338de60957/Project%20Images/image19.png" height="60%" width="60%" />
</br>
</br>

<b>• For Firewall (security groups): I Selected Create security group, with the following settings:</br>
<b>• I added an SSH rule as a way for developers to securely log in from a computer to another remote computer, which is the EC2 instance in this case.</br>
<b>• Selected Network Project Public Security Group as the source so only resources that are part of the Network Project Public Security Group can communicate with your instance.</br>
<img src="https://github.com/Tanakagi/Testing-VPC-Connectivity-and-troubleshooting-connection-issues./blob/6c7c1e72fbe191792337121515a698338de60957/Project%20Images/image20.png" height="80%" width="80%" />
</br>
</br>
