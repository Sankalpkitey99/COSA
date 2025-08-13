
🔹 Simple Volume
A basic volume created from unallocated space on a single disk.

🔹 Spanned Volume
Combines space from multiple disks into one large volume (no fault tolerance).
eg:- may take 10GB from disk1 and 20GB from disk2 to form a 30GB spanned volume

🔹 Striped Volume (RAID 0)
Splits data evenly across two or more disks for better performance (no redundancy).
eg:- will take 10GB from disk1 and disk2 to form a 20GB spanned volume the data will be divided into 20 parts one part will write to disk1 and the other part to disk2.

🔹 Mirrored Volume (RAID 1)
Duplicates data across two disks for redundancy and fault tolerance.

🔹 RAID-5 Volume (Windows Server only)
Distributes data and parity across three or more disks for performance and fault tolerance.


## To open disk mangement you can press *win + x* and search disk mgm /or/ you can *win+r* and type *diskmgmt.msc*

## MBR (Master Boot Record)
An older partitioning system.

Supports up to 4 primary partitions.

Works with disks up to 2 TB.

Used with BIOS-based systems.

Stores partition data in one place, so it's more prone to corruption.

## GPT (GUID Partition Table)
A modern partitioning system.

Supports up to 128 partitions.

Works with disks larger than 2 TB.

Used with UEFI-based systems.

Stores multiple copies of partition data for better reliability.



## for volume creation do refer 
https://onlinecomputertips.com/support-categories/hardware/create-spanned-or-striped-volume-windows-11/




🔹 NTFS (New Technology File System)
Used in modern Windows systems.

Supports very large files (over 4 GB).

Handles large volumes (TBs and more).

Supports file permissions, encryption, and compression.

More secure and reliable (with journaling and error recovery).

Best for internal drives and Windows OS.

🔹 FAT32 (File Allocation Table 32)
Older and simpler file system.

Max file size is 4 GB.

Max partition size is 2 TB.

No support for file permissions or security.

Compatible with almost all devices (Windows, macOS, Linux, game consoles).

Best for USB drives or external drives for universal compatibility.


=============================================

*to create user*
-need to go *win + r* and type ( compmgmt.msc )
- select local users and group 
- in users right click add user
- remember to see the passwords policy
- 


🔹 Domain
A domain is a logical group of network objects (like users, computers, and devices) that share the same Active Directory database.

Example: company.local

It has its own security policies and user authentication.

Everything inside a domain is managed centrally.

🔹 Domain Controller (DC)
A Domain Controller is a server that runs Active Directory Domain Services (AD DS) and manages the domain.

Authenticates logins.

Enforces security policies.

Stores a copy of the AD database.

🔹 Additional Domain Controller (ADC)
An Additional Domain Controller is another DC in the same domain.

Provides redundancy and load balancing.

Has a copy of the same AD database.

Keeps syncing data with the main (or primary) domain controller.

🔹 Domain Tree
A domain tree is a collection of related domains that share a common root name.

Example:

company.com (parent domain)

hr.company.com (child domain)

sales.company.com (another child domain)

All trust each other and share the same namespace.

🧠 In Simple Words:
Term	Simple Explanation
Domain	Group of users/computers with shared rules and access.
Domain Controller	The brain of the domain – handles logins and rules.
Additional DC	A backup brain – same job, helps if main DC is busy/down.
Domain Tree	A structure of related domains under a common root.

An Active Directory Forest is the top-level container in Active Directory — it represents the entire AD environment.

🔹 In Simple Terms:
A forest is like the entire organization, and inside it, there can be multiple domain trees (which can have multiple domains).

🧠 Key Points:
It is the security boundary — trust exists within a forest.

All domains in a forest share the same schema and configuration.

You can have one or many domains in a single forest.

Domains in a forest trust each other by default.

🧱 Forest Structure:
less
Copy
Edit
   [Forest: company.com]
         |
     ┌───┴────────┐
 [Domain A]   [Domain Tree B]
                ├────────┐
           [Domain B1] [Domain B2]
💡 Example:
If company.com is your root domain:

You can have child domains like sales.company.com or hr.company.com.

You can even add a separate tree like branch.local in the same forest.


=======================================

TO create a ADDS

go to manage> add roles and features>
next>next>next> select the server i.e Active directory domain service

click next select appropriate name.lab you may also give .com, .in but it will be propritory so be careful

next then install and restart




                                                                Windows Administration

Disk Management

Partition style

MBR - Master Boot record

Upto 2TB
Max  of 4 partition
Stores boot info in the first sector
GPT - GUID partition table

Larger than 2TB
Max part - upto 128
More reliable - keep backup of partition table


File system

NTFS - New Technology file system 

More secure 
provides ACL or access control over files

FAT32 - File Allocation Table
Older tech
Used to store 32 bit chunks
Acts as primary partitions for multiboot system

https://testbook.com/key-differences/difference-between-fat32-and-ntfs


File system
In Windows - NTFS, FAT32 ,exFAT32
In Linux - ext3, ext4
In MAC- HFS , APFS










 Partionation of disk
Primary 
Extended
Logical
ESP

Types of Volume

1- Simple volume
Stores the volume in single or one disk 
Eg. Storing 10GB of volume in D drive
2- Spanned volume 
Storing data in into multiple files
E.g Storing 10 GB in HD1 and 20 GB in HD2 to create a HD of total 30GB
Such that creating a big volume from multiple volume
3- Striped volume(RAID 0)
Storing data from multiple file for having faster access
Such that  storing data of 10GB in HD1 and 10 GB in HD2, total volume created to be 20 GB
4- Mirrored Volume (RAID 1)
Mirroring  is done if one Hard  disk fails then we can mirror the data back form another hard disk
If both fails , data loss and e.g the HD1 - 10GB and HD2-10GB the total volume remains the same i.e 10GB only
5- RAID 5 (Redundant Array of Independent Data)
Data stores in Disk can be retrieved using another another disk having parity 
So there are 3 disk required from which one disk stores the parity 
3 disk used to have faster access as of striped volume and to recover the data we used the parity in it

Format
Formatting a storage device is preparing it to store and organize the data

Two types of formatting
Normal format
Quick format

Normal formal
Slow process of formatting in which it scan for entire bad sector  & erases all data so no data retrieval possible here


Quick format
Faster process of formatting in which it does not scan for bad sectors & erases only the file allocation table, data retrieval is possible here 


User and Group Mangement

SAM File - (Security Account Manager)
Stores username and password of hashes for all the local users
Located in C:\Windows\System32\config\SAM
Stores in registry hives in SYSKEY - requires administrator account to access

To use Computer management we can (Win + R)-> and then compmgmt.msc

Password expires after 42 days

When creating a new user account on a Windows machine, the "Users" group is automatically assigned to that user. This means that the user will have access to common tasks like running applications, using printers, and locking the computer. Additionally, the "Authenticated Users" group, which represents all users who have successfully logged in, is also a member of the "Users" group. 

SID-Security Identifier is a unique, immutable value that identifies security principals like users, groups, and computer



ADDS - Active Directory Domain Service

A Directory of hirarchical structure which store information related to   object on a network
It generally store data related to user info such as username , passwords etc
It provides authentication for users


ADDS includes schema and global catlog
Schema is defined as classes of objects and attribute contained in a directory 
Global catlog that contains information about evey object in the directory 
-  users and administrators can use the catalog to find directory information regardless
 of the directory domain that actually contains the data

Logical components of ADDS
Domain- Logical group of computer , which follow common security databases
ADD- Active Directory Domain - Its a group of computer which follows common security databases
Domain Tree- Its a group of domain which shares a common name space
This domain are bing with a parent and child relationship
Forest - Collection of one or more that one domain tree which have common ADDS root
Or Logical Boundary which contains multiple domain  trees 
OU - organizational Unit - which stores information of users and group which allows to implement the group policy and administrative rights


Physical components

1)Domain  Control- First server which creates the security databases
Contains a copy of
 ADDS databases
2) Additional Domain Controller - This servers copies the security databases from DC or ADC
This  server holds read and write copy of a database.




DNS - Domain Name System
Industry standard protocol , providing computer name to ip addresss mapping and name resolution services to computer and users

Dynamic Host Configuration Protocol (DHCP) is a client/server protocol that automatically provides an Internet Protocol (IP) host with its IP address and other related configuration information such as the subnet mask and default gateway

How DHCP provides IP to the PCs?

Default lease period in windows for DHCP server?
8 days
How many previous password remember by the windows ?
24









LDAP
Lightweight Directory Access Protocol
We can access and mange directory servers over the network



LDAP do’s
User Authentication
Access Control 
Manages obj in AD
Search for user/ groups /computer

LDAP   port - 389
LDAPS port  - 636

LDAP’s Destination add-  .ldif

OU - Organizational Unit
Folder inside the active directory 
Organizes ussr/computer./group 
Apply and allow  group policies
Delegates administrative control


Kerberos
User Authentication Protocol , use to identify and verify user & host
Genrates something c/as Realams(similar to domain), kerberos build trust between those realms for SSO (Single sing  on) , also known/as  Third party Authentication
Port no : 88
Have 3 services:
AS(Authentication Services)= accepts username & passwd for authentication	
TGS(Ticket Granting Services)= Generates tickets for services
KDS(Key Distribution Services)= Generates Key for the services

Also know/as Ticket based Authentication
 
As verify the username & passwd verifies by LDAP databases- upon successful verification AS ask TGS to Gerate the ticket know/as TGT - Ticket Granting Ticket and based upon the AS and TGS  then KDS generates and gives the Key 


Superscope- user to group multiple scope under a single administrative entity 


DNS Zones
 Forward lookup Zones
Converts domain name tp  IP 
Reverse Lookup Zones
Converts IP to Domain name
Stub Zones:
Used to maintain info about another DNS Zone

DNS
Domain Name Server
Industry Standard protocol , used to convert Computer name to Ip address
Mapping name resolution services tp computer & user

When client gives a DNS Query to resolves, this server respons back with DC hostname and IP , The DNS looks into SRV records -> services records used to find DC for LDAP dns provide back and then PC know which DC to contact via port no 88 (Kerberos) and then authentication happens (Kerberos process contd..)


FQDN- Fully qualified domain Name

Essentially complete Internet address of  a Services/server
Hostname + domain name
E.g . www.example.com,  www.google.com
ANS- Authoritative Name Server
Has a authority for Domain and its record

Types of Records 
 Host -A- IPV4
 Record -AAAA -  IPV6  
These bot name to UP 


PTR record - Pointer record - map name to ip address
Host record - Map  ip to name

CName: Canonical Name - Hold multiple names for single IP address

MX record - Mail Exchange Record - Use to provide the email server IP address of a domain
Direts email to mail server using SMTP-Simple mail transfer protocol - port 25
So it sets equal pritoy no. so that the load gets balance

SRV- Service records- Database which hold info about ldap, kerberos etc.

FSRM- FIle Server Management
Manages file data stored on file server
Features -
Quota management
File restrictions
Reporting

NLB- Network Load Balancing 
Manges 2 or more server in Single virtual cluster
Distributes traffic from 2 or more server using TCP/IP protocol

32 host in single virtual Cluster

WDS - Windows Deployment Server
Service allows you to deploy windows os on a LAN computer over the network

PReReq:
1- Active Directory Domain
2- DHCP Server
3-PXE- Preboot Exection Enviorment (allow booting over the network) 
4- NTFS  partition

After TFTP (Trivial File Transfer Protocol) - port no 69
Boot img - boot win
Install img - install win

Install img - contains windows/any other os installation files
Boot img - allows boot after they get IP
Capture img - Allows to capture hard disk of a comp over which capt img is created from boot img



FSMO - Flexible Single Master Operation

Single master mode
Slave & master relation
If masters fails or mainDC fails then due to single point of failure, system fails, adn not been able to add on other user

Multi master model

AD and eacg DC maintains a writable copy of the databases and permissions so any one can have access over them , which can create conflict at any point
FSMO - 
Domain Controller that holds opr master roles
Provide unique set of domain/forest management task
Prevents conflicts in  directory by ensurng certain updates

Roles -
  2 Forest wide
Schema Master - have structure of AD
Domain Naming - Unique domain name within forest and authority change for domain name space
 3 Domain Wide
RID - Resource ID - allocated RIF to avoid duplication of SIDno
PDC - Time synchronous ,m password sync or update
Infrastructure - Manges reference from obj i  its domain  to obj in other domain


VPN - Give remote access to interal Client 

Network policy Service
RADIUS - Remote Authentication for dail in user services

Allow you to create and enforocrce organization wide network access policies for connection request authentication and authorization








