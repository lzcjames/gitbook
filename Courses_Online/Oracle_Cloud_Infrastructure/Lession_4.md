# OCI Storage Services

## Block Storage

- Like a hard drive in a server except the hard drive happens to be installed in a **remote** chassis.
如同服务器中的硬盘驱动器，但硬盘驱动器恰好安装在**远程**机箱中

- Data is typically stored on device in fixed sized blocks (e.g 512 Bytes).

- Accessed by operating system as mounted drive volume.
Block storage 通过操作系统作为已安装的驱动器卷进行访问

- Applications/file systems decide how blocks are combined and accessed.

- Data is stored **without** any **higher-level metadata** e.g for data format, type or ownership.
数据存储时没有任何更高级别的元数据，例如数据格式，类型或所有权

- You can place any kind of file system on block level storage. E.g Windows uses NTFS; VMware uses VMFS.

### Block Volume Service

- Storage for compute instances (REMOTE)

- 2 types of Block volumes:
	- Boot Volume (OS disk)
	- Block Volume (data disks)
	
- Why do we use Block Volume: it lets you store **data independently** and **beyond** the lifespan of compute instances. 它使可以独立存储数据和独立于实例的使用寿命

- When instance  dies,  Your  boot  volume  and  your  data  volumes  are  all  still  available. So Block Volume is used for  **data durability** 数据持久化.

### Block Volume Use cases

- Databases
- Exchange (supports block level storage only)
- VMware (VMFS volumes on block level storage)
- Server boot (in public clouds, instances are configured to boot from block level storage)

<img src="https://imgur.com/PO5DbHp.png" width="420" height="480">

### Block Volume Highly durable

- Storage is highly durable and persistent
- Block Volume store replica of data in 3 separate FDs
- You don't need to configure any software based protection (RAID 10 etc)
- A backup is recommend for minimize losing data. 

<img src="https://imgur.com/UwItVxH.png" width="400" height="220">

### Block Volume Backup
- Complete point-in-time snapshot copy of your block volumes
- Encrypted and stored in the Object Storage, and can be restored as new volumes to any AD within the same region
- Can copy block volume backups from one-region to another
- Backups can be scheduled

### Block Volume Tiers
<img src="https://imgur.com/JGrdTwk.png" width="500" height="290">

## Local NVMe
- **Temporary** storage **locally** attached **directly** to the compute instances*
-  Desi


<!--stackedit_data:
eyJoaXN0b3J5IjpbMzM5NzM0MTgyLC02MzYxMDMyNTAsLTE2Mz
A4MTc5MzYsLTQ0NzU0MjA1MCwtMTk4MjcwNzAxNyw3ODkzNTQ3
MzRdfQ==
-->