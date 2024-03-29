



![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/66036fa5-7730-431a-9b83-98be01cb6b51)



ENVIRONMENT AND TECHNOLOGIES USED:

	Microsoft Azure (Virtual Machines\Compute)
	Remote Desktop
	Active Directory Domain Services 
	PowerShell
	Windows Server 2022
	Windows 10 Pro 2022

HIGH-LEVEL DEPLOYMENT AND CONFIGURATION STEPS:

	Sign into Microsoft Azure Account 
	Create new resource group 
	Add virtual machines to the resource group
	Remote into Windows Server 2022
	Configure windows server with Active Directory Domain services and DNS 
	Create Users 
	Login to the client machine and test connectivity 



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

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/82423108-34a2-4ad2-b55f-a0dc52efa658)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/094e753d-56bf-4cf8-af9c-04fdb9737cb0)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/fae131c3-a8c4-46df-812d-0ed899b9e9e6)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/5a7f7ff4-8de1-4c70-91d7-341ef891ca44)





Next we are going to make sure that we can ping the DC-1 from client-1 ensuring connectivity between both.

It is timing out because DC-1 windows firewall is blocking ICMP traffic

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/481b4afc-ef56-4333-adb9-6159189df067)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/83cc3387-0a9a-40a7-b514-d8247d2290a6)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/2ccdb9a7-a6a1-47af-950f-ae6cbd1e4122)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/df1f85c2-fd35-495b-8f53-025479742e7c)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/fda7037b-54c2-4982-a4b1-a2795dd30fc9)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/e3216640-2ccb-4005-8d47-5af9c343377a)


![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/a2007fd5-df4b-4f62-b022-db1ae0b6cfa5)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/72879a63-5257-49b7-a415-927f12aa57c5)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/336fceac-ae08-4f19-9fb9-cd74f015b2b9)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/ad8a74f9-afdd-4ea3-8f1b-003234fe79b0)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/97af5e01-451f-4133-85df-1176f31b1b9f)

![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/b86e4747-7750-44ba-8f12-9dd397762d5c)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/45e364ec-7d6d-4eb0-8427-675a3ecf5d7c)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/511f2fe3-67dc-4a9f-aa7f-8f853048a6f2)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/48709bf0-0dfd-4010-9307-5e104630c6dd)
![image](https://github.com/uwinelly/On-premises-Active-Directory-/assets/129979322/e02ea3ad-ac09-43a5-b94d-320ef5c6ab78)











     
We are going to instaure Active Directory on DC-1 and then we will be joining the Client-1 to the DC-1 Domain.
We are going to create a bunch of user accounts on the domain with a powershell script.
