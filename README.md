# Home Lab Running Active Directory (Users Added w/PowerShell)


## Project Description
For this project, I created an Active Directory lab using VirtualBox. The first virtual machine I created acted as the Domain Controller housing Active Directory. Two network adaptors were used for this virtual machine. One was used to connect to the outside internet while the other one was used to connect to the VirtualBox private network. IP addressing was assigned for the internal network. The external networking automatically got IP addressing from my home network. Active Directory was installed and then I created the domain. I configured Network Address Translation (NAT) and routing next so the clients on the private network could reach the internet through the Domain Controller. Dynamic Host Configuration Protocol (DHCP) was set up on the Domain Controller so when the client machine was created it could automatically get an IP address. Lastly, I ran a PowerShell script on the Domain Controller that automatically created over a thousand users in Active Directory. Another virtual machine was created and connected to the private VirtualBox network. The client was joined to the domain and a domain account was used to login to it.   

![image1](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/ff7ef5e2-d050-4543-ba0a-0496b2e836ee)


## Setup 

Using Oracle VirtualBox, I created a Windows Server 2019 computer that acted as the Domain Controller.

![image14](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/35fbd29a-9bd3-47cb-bdd1-e18433ce59eb)

Two Network Interface Cards (NIC) were created: one was dedicated to the internet that is running NAT and the other one is dedicated to the internal VirtualBox network.

![image13](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/dc231875-d559-4035-818b-a7d068566bec) ![image9](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/d4e91276-26b2-4e7a-8c88-6fa5ccb3b6da)

Active Directory Domain Services installed.

![image12](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/35400c87-4fd5-4d25-8d9e-07e21d287979)

The domain ‘mydomain.com’ was created.

![image4](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/5c92d67d-f684-4d87-96cb-1cf044bcc374)

I created an _ADMINS organizational unit and added myself as a user.

![image6](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/b291cd23-5ea0-46d3-8b92-0c1c08f7f4ba)

Remote Access role installed.

![image2](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/66fa0f89-ab9e-4002-87dd-496e3bec4009)

![image7](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/9211d685-096a-4ac4-bc9c-08b6931d4637) ![image11](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/61aadf5f-18a9-4795-8991-4b26c9588dee)

DHCP Server role installed.

![image18](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/2e9635a7-faff-4aef-a4dc-c350de4667f4) ![image19](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/1d81c286-20b4-470d-a2df-1d014cddd2e9) 

Randomized names for the created users. I also placed my name on the list.

![image20](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/5b326011-fbee-4062-85bd-07d07cc499bc) ![image8](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/c7861ccd-86f7-4923-b496-57eb245d422a)

PowerShell script used to create users in Active Directory. 

![image17](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/1aed81d5-0f39-426a-90d9-b360a8d907b9)
![image5](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/5989ca1b-1bd2-4897-8de2-ac023b2e52ad)

I created a Windows 10 virtual machine using an internal NIC. This virtual machine acted as the client. 

![image16](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/c9bfc80a-3161-4044-97b4-52bc69e14cd2)
![image10](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/a0550521-b114-45df-8618-a39e25e9c9c9)

Changed the computer name to ‘CLIENT1’ and joined the domain ‘mydomain.com’.

![image1](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/434ff631-ec95-4239-b83c-1799a9b65f7d)

We can see I have one address lease from the client computer I created. This is because when I created the client computer and joined it to the network it reached out to the DHCP server automatically and requested an IP address.     

![image15](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/dd22c0f3-0edc-4584-91bb-aa571c821f11)

After joining the client computer to the domain we can now see it in the Active Directory Users and Computers. If I were to delete this I would not be able to login with one of the user accounts I created.

![image21](https://github.com/markach151/HomeLabActiveDirectory/assets/84886088/55798a50-0c22-4692-ba5f-f70c59953a40)

## Credit to Josh Madakor for the project tutorial!
