# On-premises-Active-Directory-in Azure Virtual machine
We are going to run a resource group> virtual network(192.168.0.0/16)> subnet(192.168.1.0/24)

Next we will create two virtual machines:
     1) DC-1 Domain Controller which will be running windows server
     2) Client-1 running windows 10
     
We are going to instaure Active Directory on DC-1 and then we will be joining the Client-1 to the DC-1 Domain.
We rae going to create a bunch of user accounts on the domain with a powershell script.
