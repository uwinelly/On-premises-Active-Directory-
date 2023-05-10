
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/66036fa5-7730-431a-9b83-98be01cb6b51)


This tutorial outlines the implementation of on-premises Active Directory-in Azure Virtual machines

We are going to run a resource group> virtual network(192.168.0.0/16)> subnet(192.168.1.0/24)

Next we will create two virtual machines:
     1) DC-1 Domain Controller which will be running windows server
     2) Client-1 running windows 10
     
We will go ahead and set Domain Controller’s NIC Private IP address to be static:

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/294987d6-f1f1-495b-bb9d-e52956a03d06)

Next we are going to make sure that we can ping the DC-1 from client-1 ensuring connectivity between both.

It is timing out because DC-1 windows firewall is blocking ICMP traffic

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/481b4afc-ef56-4333-adb9-6159189df067)





     
We are going to instaure Active Directory on DC-1 and then we will be joining the Client-1 to the DC-1 Domain.
We are going to create a bunch of user accounts on the domain with a powershell script.
