
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/66036fa5-7730-431a-9b83-98be01cb6b51)


This tutorial outlines the implementation of on-premises Active Directory-in Azure Virtual machines
The first thingthat we need to do is to set up a microsof Azure account using this link: https://azure.microsoft.com/en-us/free.
Click on "start free" and create your account.

We are going to run a resource group> virtual network(192.168.0.0/16)> subnet(192.168.1.0/24)

Next we will create two virtual machines:

     1) DC-1 Domain Controller which will be running windows server 2022
     
   
     

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/ebd22b3a-5615-4079-98ef-9f65e116288b)


![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/b5386f45-084b-4ac9-b260-d8f15adc0ee7)



![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/26225fcc-5ae1-4922-ad13-845c573b2250)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/a427c3b4-3654-4d7e-9a28-97ab55f4f102)


  2) Client-1 running windows 10

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/ab5c71cf-1531-40fe-8bf0-9a0aa1b79660)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/790447b9-4a5d-45cd-9181-a86d361c29f9)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/56931096-d017-4f11-838b-6261a1bcb24c)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/238473f8-12b9-4f43-a161-74035511878d)



We will go ahead and set Domain Controller’s NIC Private IP address to be static:

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/294987d6-f1f1-495b-bb9d-e52956a03d06)

Next we are going to make sure that we can ping the DC-1 from client-1 ensuring connectivity between both.

It is timing out because DC-1 windows firewall is blocking ICMP traffic

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/481b4afc-ef56-4333-adb9-6159189df067)

     
We are going to instaure Active Directory on DC-1 and then we will be joining the Client-1 to the DC-1 Domain.
We are going to create a bunch of user accounts on the domain with a powershell script.
