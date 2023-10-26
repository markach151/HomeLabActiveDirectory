<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.333 seconds.


Using this HTML file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Thu Oct 26 2023 13:32:03 GMT-0700 (PDT)
* Source doc: Basic Home Lab Running Active Directory
----->


<p>
<strong>Summary </strong>
</p>
<p>
For this project, I created an Active Directory lab using VirtualBox. The first virtual machine I created acted as the Domain Controller housing Active Directory. Two network adaptors were used for this virtual machine. One was used to connect to the outside internet while the other one was used to connect to the VirtualBox private network. IP addressing was assigned for the internal network. The external networking automatically got IP addressing from my home network. Active Directory was installed and then I created the domain. I configured Network Address Translation (NAT) and routing next so the clients on the private network could reach the internet through the Domain Controller. Dynamic Host Configuration Protocol (DHCP) was set up on the Domain Controller so when the client machine was created it could automatically get an IP address. Lastly, I ran a PowerShell script on the Domain Controller that automatically created over a thousand users in Active Directory. Another virtual machine was created and connected to the private VirtualBox network. The client was joined to the domain and a domain account was used to login to it.            
</p>
<p>
<strong>Setup</strong>
</p>
<p>
Using Oracle VirtualBox, I created a Windows Server 2019 computer that acted as the Domain Controller.
</p>
<p>
Two Network Interface Cards (NIC) were created: one was dedicated to the internet that is running NAT and the other one is dedicated to the internal VirtualBox network.
</p>
<p>
Active Directory Domain Services installed.
</p>
<p>
The domain ‘mydomain.com’ was created.
</p>
<p>
I created an _ADMINS organizational unit and added myself as a user.
</p>
<p>
Remote Access role installed.
</p>
<p>

</p>
<p>
DHCP Server role installed. 
</p>
<p>
Randomized names for the created users. I also placed my name on the list.
</p>
<p>
PowerShell script used to create users in Active Directory. 
</p>
<p>

</p>
<p>
I created a Windows 10 virtual machine using an internal NIC. This virtual machine acted as the client. 
</p>
<p>
Changed the computer name to ‘CLIENT1’ and joined the domain ‘mydomain.com’.
</p>
<p>

</p>
<p>
We can see I have one address lease from the client computer I created. This is because when I created the client computer and joined it to the network it reached out to the DHCP server automatically and requested an IP address.     
</p>
<p>
After joining the client computer to the domain we can now see it in the Active Directory Users and Computers. If I were to delete this I would not be able to login with one of the user accounts I created.  
</p>
