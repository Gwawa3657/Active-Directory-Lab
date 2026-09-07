# Active-Directory-Lab



During Virtual Box Setup Add an internal network adapter to the Domain Controller <img width="762" height="507" alt="Screenshot 2026-05-01 064628" src="https://github.com/user-attachments/assets/9cea5998-1205-438c-adc2-550fe7b612b9" />

User: ==Administrator==
Password: ==Password123==
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
Create domain by clicking Promote this server to a domain controller <img width="412" height="187" alt="Screenshot 2026-05-01 075848" src="https://github.com/user-attachments/assets/07cf2e5a-ec8f-4697-b3a9-ac2aa4c7c901" />
Select Add a new forest and make the Root domain ==MyDomain.com==
