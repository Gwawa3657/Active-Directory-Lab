# Active-Directory-Lab



During Virtual Box Setup Add an internal network adapter to the Domain Controller <img width="762" height="507" alt="Screenshot 2026-05-01 064628" src="https://github.com/user-attachments/assets/9cea5998-1205-438c-adc2-550fe7b612b9" />

User: Administrator
Password: Password123
Renaming PC to Domain Controller(DC)<img width="1134" height="813" alt="Screenshot 2026-05-01 074749" src="https://github.com/user-attachments/assets/0e87ce65-fdb1-4136-bf3e-0b35144ec9ec" />
Renamed both Ethernet adapters so they can be identified later<img width="776" height="583" alt="Screenshot 2026-05-01 072232" src="https://github.com/user-attachments/assets/3fdcf509-3896-4c5f-9a3a-5091a6d42ae4" />

The Internal Network got assigned an APIPA (Automatic Private IP Address)
<p align="left">
<img width="353" height="429" alt="Screenshot 2026-05-01 072916" src="https://github.com/user-attachments/assets/747cb866-9a26-47ac-ba32-77f745f1301f" />
</p>
The manually assigned IP is 172.16.0.1 with a subnet mask of 255.255.255.0
No need to setup a default gateway since the DC acts as its own gateway.
The DC will also use itself as a DNS server once I install active directory, so I can use the loopback address (127.0.0.1)
<p align="left">
<img width="391" height="472" alt="Screenshot 2026-05-01 073853" src="https://github.com/user-attachments/assets/ea55d61f-3989-4572-b1a9-f3c00c5ec4e8" />
</p>
In Server Manager download Active Directory Domain Services <img width="1143" height="864" alt="Screenshot 2026-05-01 075610" src="https://github.com/user-attachments/assets/63f3eac3-b3a4-4566-8e45-81949afc7f3f" />
Create domain by clicking Promote this server to a domain controller 
<p align="left">
<img width="412" height="187" alt="Screenshot 2026-05-01 075848" src="https://github.com/user-attachments/assets/07cf2e5a-ec8f-4697-b3a9-ac2aa4c7c901" />
</p>

Select Add a new forest and make the Root domain MyDomain.com <img width="749" height="545" alt="Screenshot 2026-05-01 080328" src="https://github.com/user-attachments/assets/d8918c3e-650c-4aca-8e09-daac3a98a6d3" />
<br>
That domain creation gave a default administrator login. Log in and create an admin account.
<br> <img width="1132" height="846" alt="Screenshot 2026-05-01 081432" src="https://github.com/user-attachments/assets/187c2b29-f9f3-4199-8af6-77fc2e7298ef" />
Select Active Directory Users and Computers 
<p align="left">
<img width="637" height="650" alt="Screenshot 2026-05-01 081958" src="https://github.com/user-attachments/assets/b500016d-d382-40b5-b535-d76b8eeaa649" />
</p>
Right click MyDomain.com New>Organizational Unit. Name it ADMINS. <img width="749" height="527" alt="Screenshot 2026-05-01 082222" src="https://github.com/user-attachments/assets/2d7019f5-80a9-4ebe-87c1-bd2157061911" />
<br>
I created an admin account for myself
<p align="left">
<img width="428" height="365" alt="Screenshot 2026-05-01 082552" src="https://github.com/user-attachments/assets/09f2fbb2-b245-4152-ad34-3d8ac77fd13a" />
<img width="426" height="364" alt="Screenshot 2026-05-01 082643" src="https://github.com/user-attachments/assets/63c27056-3b5a-428a-8a64-f67eb31fd63e" />
</p>
<img width="803" height="606" alt="Screenshot 2026-05-01 082824" src="https://github.com/user-attachments/assets/1d332029-7583-449c-8643-f9cf4352b54e" />
<br> Log out then log back in with the newly created account. <img width="1110" height="831" alt="Screenshot 2026-05-01 082923" src="https://github.com/user-attachments/assets/d76df663-f0f9-4364-90f3-54897c065240" />
<br> Once logged in, install Remote Access to enable machines connected to the Domain Controller to access the internet through it. Enable Routing and Direct Access and VPN (RAS)
<p align="left">
<img width="777" height="686" alt="Screenshot 2026-05-03 172256" src="https://github.com/user-attachments/assets/56f9a9ce-50f1-4ab4-8b5a-508736454ce5" />
</p>
<img width="772" height="548" alt="Screenshot 2026-05-03 172613" src="https://github.com/user-attachments/assets/4baf0dda-9ab5-4bec-8d60-7cad76821c03" />
<br> After installation, select tools and find Routing and Remote Access
<p align="left">
<img width="358" height="774" alt="Screenshot 2026-05-03 173603" src="https://github.com/user-attachments/assets/55f68279-859d-45ec-9554-ba4ae3336ceb" />
</p>






