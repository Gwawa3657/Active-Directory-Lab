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
<br> Right click the DC and go into configuration so select Network Address Translation (NAT)
<p align="left">
<img width="486" height="403" alt="Screenshot 2026-05-03 173833" src="https://github.com/user-attachments/assets/ef46bcdc-348c-4c2f-ad1b-a7492e871ea3" />
</p>
<br> Here we can see the Network Adapters that were named earlier
<p align="left">
<img width="490" height="411" alt="Screenshot 2026-05-03 174058" src="https://github.com/user-attachments/assets/eb2f22d1-89dd-45df-a40a-80c41c32812c" />
</p>
<br> We can confirm that Remote Access is set up through Server Manager
<img width="1122" height="807" alt="Screenshot 2026-05-03 174258" src="https://github.com/user-attachments/assets/2d13b9a8-a339-41cb-8602-8522f12891a4" />
<br> Now to setup a DHCP server on the DC so machines will be automatically assigned an IP Address. Go back to add roles and features but select DHCP Server.
<p align="left">
<img width="791" height="744" alt="Screenshot 2026-05-03 175246" src="https://github.com/user-attachments/assets/0eab5082-65bb-4c22-bca8-9974d0c3f931" />
</p>
<br> Select tools then DHCP
<p align="left">
<img width="373" height="562" alt="Screenshot 2026-05-03 175446" src="https://github.com/user-attachments/assets/6dcd2d09-bc1f-4784-a704-db32fa0852ec" />
</p>
<br> Right click and New Scope
<p align="left">
<img width="501" height="535" alt="Screenshot 2026-05-03 175657" src="https://github.com/user-attachments/assets/15f0fe5b-45c7-4ec2-8046-5654c1102677" />
</p>
<br> The starting IP address will be 172.168.0.100 and the ending IP address is 172.168.0.200. Set Length to 24
<p align="left">
<img width="496" height="379" alt="Screenshot 2026-05-03 175949" src="https://github.com/user-attachments/assets/f1c7d655-b176-43cf-9396-a41362d2f0ea" />
<img width="500" height="409" alt="Screenshot 2026-05-03 180842" src="https://github.com/user-attachments/assets/0a42e841-3676-4e41-8cc5-3be52ed983c4" />
</p>
<br> The DC is essentially the gateway so add the Internal IP(Internal Network Adapter) and select add.
<p align="left">
<img width="504" height="406" alt="Screenshot 2026-05-03 181107" src="https://github.com/user-attachments/assets/1d47994a-8e91-4e5b-ab68-666aee332819" />
</p>
<br> The Dc is also the DNS server so select next
<p align="left">
<img width="503" height="411" alt="Screenshot 2026-05-03 181224" src="https://github.com/user-attachments/assets/d242b55e-53c9-4691-92fe-75d3531ac861" />
<img width="500" height="409" alt="Screenshot 2026-05-03 181311" src="https://github.com/user-attachments/assets/89f68f32-8d78-49fc-807d-6b66888076fa" />
</p>
<br> Right click the DC and then Authorize. Then right click IPv4 and refresh. The DHCP server is configured.
<p align="left">
<img width="576" height="529" alt="Screenshot 2026-05-03 181421" src="https://github.com/user-attachments/assets/9a3dafc0-7b37-4528-ba0d-39ec8ff8ba9d" />
<img width="271" height="173" alt="Screenshot 2026-05-03 181621" src="https://github.com/user-attachments/assets/25e91f0a-64f3-46dc-b490-b45ee5c5e5e6" />
</p>
<br> The DC is done at the moment so set up a Windows 11 client to join the domain. Create a new Virtual Machine (VM) and make sure the OS version is set to Pro
<br> In the VM manager change adapter 1 to Internal Network instead of NAT.
<p align="left">
<img width="759" height="502" alt="Screenshot 2026-05-03 205032" src="https://github.com/user-attachments/assets/47aa4959-a1fd-43e9-a27a-be5efb9bfbec" />
</p>
<br> Windows 11 won't let you proceed with the installation without being connected to a network.
<br> Shift+F10 then type the command oobe\bypassnro and press enter.
<br> This command lets you bypass that.
<p align="left">
<img width="996" height="663" alt="Screenshot 2026-05-03 212933" src="https://github.com/user-attachments/assets/bd618107-fdc0-4620-b167-96f14e55b404" />
</p>
<br> Select I don't have internet and continue with the setup.
<p align="left">
<img width="983" height="726" alt="Screenshot 2026-05-03 213358" src="https://github.com/user-attachments/assets/ecf82bb6-4189-431a-a913-bb182e2a3acd" />
</p>
<br> Go to System > About then Domain or workgroup
<p align="left">
<img width="774" height="613" alt="Screenshot 2026-05-03 233700" src="https://github.com/user-attachments/assets/cb283a65-89e8-4278-a92c-f0246d9c1359" />
</p>
<br> Select change then check the circle for domain and enter the DC name.
<p align="left">
<img width="397" height="452" alt="Screenshot 2026-05-03 234805" src="https://github.com/user-attachments/assets/c53d22c6-4629-4fa4-a180-897755a4c634" />
<img width="311" height="373" alt="Screenshot 2026-05-03 235344" src="https://github.com/user-attachments/assets/88dabe25-fd77-46f8-96d2-a0f681c6e64f" />
</p>
<br> Log in with the admin account that was created earlier.
<p align="left">
<img width="435" height="365" alt="Screenshot 2026-05-03 235514" src="https://github.com/user-attachments/assets/d85efa7b-d850-4589-a671-cd0105fac21e" />
</p>
<br> After a short wait the client machine has joined. Restart the client.'
<p align="left">
<img width="292" height="139" alt="Screenshot 2026-05-03 235608" src="https://github.com/user-attachments/assets/0ff3773d-afc2-4e2f-8063-dae031f4145b" />
</p>
<br> Can verify the w11 client is in the domain by going back to the DC. 
<br> Search Active Directory Users and Computers.
<br> Go to computers and the w11 client is there.
<p align="left">
<img width="741" height="520" alt="Screenshot 2026-05-03 235937" src="https://github.com/user-attachments/assets/5d101607-50a4-454c-bcbd-6ed321955b06" />
</p>
# Generating Users with PowerShell






