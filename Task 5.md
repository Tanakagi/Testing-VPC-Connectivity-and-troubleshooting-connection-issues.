# Task 5: Connecting to the Network Project Public Server.

<b>• I Selected Connect on the Network Project Public Server.</br>
<img src="" height="80%" width="80%" />
</br>
</br>

<b>• and Kept all of the default settings.</br>
<img src="" height="80%" width="80%" />
</br>
</br>

<b> I then got this error message which indicated the connection failed.</br>
<img src="" height="80%" width="80%" />
</br>
</br>

## I then investigated what happened, first I read the error message and went to reviewing my security settings.

<b> I started Investigating the Route table and Network ACL tabs, to see if any rules were the cause of the error message. Everything seemed fine to me, my Network ACL allows all traffic in and out, and the route table is correctly setting up a route to the Internet Gateway.</br>
<img src="" height="80%" width="80%" />
<img src="" height="80%" width="80%" />
</br>
</br>

<b>• I went to the Security Groups page to investigate further.</br>
<b>• I selected the checkbox next to Network Project Public Security Group.</br>
<b>• Selected the Inbound rules tab.</br>
<b>• I noticed that no rule allowed SSH inbound traffic.</br>
<img src="" height="80%" width="80%" />
</br>
</br>
</br>


<b>• So to fix the issue I will update the  Network Project Public Server's security group so it can let in SSH traffic. Choosing Anywhere-IPv4 as the source lets in SSH connections from any IPv4 address. I then Saved the rules.</br>

<b>•If this was a long-term project, we'd search for the specific CIDR block of IP addresses that EC2 Instance Connect uses and restrict inbound SSH traffic to that range instead of using *any IPv4 address.</br>
<img src="" height="80%" width="80%" />
</br>
</br>

<b>• With that modification, I refreshed my EC2 console's Instances page.</br>
<b>• Selected my Public Server and Connected again.</br>
<b>• I was now able to successfully connect. This allows me to directly access an ec2 instance using the Amazon console we no longer need to manage key pairs or use an SSH client to get access.</br>
<img src="" height="80%" width="80%" />
</br>
</br>













</br>

<b>• and Kept all of the default settings.</br>
<img src="" height="80%" width="80%" />
</br>
</br>
