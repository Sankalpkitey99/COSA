
----COSA NOTES-----
Types of Volume 



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





