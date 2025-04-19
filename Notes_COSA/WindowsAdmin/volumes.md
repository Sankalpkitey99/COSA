NOTES---


Partition style---

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


