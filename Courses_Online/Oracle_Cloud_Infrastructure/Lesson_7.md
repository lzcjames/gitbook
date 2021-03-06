# OCI Database Services

> OCI DB Options, DB Systems, DB System Backup, DB Systems HA and DR, Autonomous Databases

## Overview

<img src="https://imgur.com/Rk4Drky.png" width="650" height="330">


## OCI DB Options

- Virtual Machine (VM DB Systems)
- Bare Metal (BM DB Systems)
- Real Application Clusters (RAC)
- Exadata DB Systems
- Automous

<img src="https://imgur.com/vdjmQoO.png" width="530" height="210">

## DB Systems Backup/Restore

- Manual or Automatic backups
- Automatic backups written to Oracle owned object storage buckets.
- Backups run between midnight - 6:00 AM in the DB system's time zone.
- Preset retention periods: 7, 15, 30, 45 and 60 days (can custom long periods)
- Recover a database from a backup stored in Object Storage

## Oracle Data Guard

- It provides a set of services that create, maintain, manage and monitor one or more standby databases to enable Oracle databases to survive disaster and data corruptions.
用于创建, 维护, 管理和监视一个或多个备用数据库从而使Oracle数据库能够在灾难或数据损坏中生存.

- It maintains synchronization between the primary and the standby DB.
它维护主数据库和备用数据库之间的同步.

- So if the primary database becomes unavailable, Oracle Data Guard can switch any standby database to the primary role, minimizing the downtime associated with the outage.
一旦主数据库变得不再可用,Oracle Data Guard可以将任一的备用数据库转变为新主数据库，从而最小化了中断停机时间.
 
  <img src="https://imgur.com/QVAtoqA.png" width="400" height="250">

- 2 modes:
	- Switchover ->planned migration, no data loss	. (when switching a standby DB to primary DB)
	- Failover -> unplanned migration, minimal data loss. (e.g. AD is not available, data corruptions 



#### Active Data Guard
It extends Data Guard, for Extreme Performance Edition and Exdata Service.

## DB Systems HA and DR (in multi ADs)

Using RAC DB + Data Guard so that you are guaranteeing the maximum High Availability Disaster Recovery  and for your database.

<img src="https://imgur.com/DkB0ell.png" width="700" height="300">

## DB Systems HA and DR (in single AD)
- If your primary and standby databases are 2-node RAC databases
- and both are in the same AD
- only one of the two nodes of the standby DB can be in a FD that does not include any other nodes from either the primary or standby DB.

如图示，我们有4个node节点, 一个是主DB的两节点(在FD1和FD2), 另一个是备用DB的两节点(在FD2和FD3). 
<img src="https://imgur.com/WD903Ps.png" width="400" height="250">

其中在FD1的主DB是独立的, FD2的主DB和备用DB是相互共享空间的, FD3的备用DB是独立的.

- 假设现在FD1或者FD3不可用, 则FD2节点的主DB和备用DB仍在运行:
<img src="https://imgur.com/hxqqk8g.png" width="400" height="250">

-  假设现在FD2不可用, 则FD1节点的主DB和FD3节点的备用DB仍在运行:
<img src="https://imgur.com/zUmMBmQ.png" width="400" height="250">

## Autonomous Database

Fully managed database with 2 workload types:
- Autonomous Transaction Processing (ATP)
- Autonomous Data Warehouse (ADW)

Deployment options:
- Dedicated

  You have exclusive use of the Exdata hardware. Supported for both ATP and ADW.

- Shared:

  You provision and manage only the Autonomous DB, while Oracle handles Exdata infrastructure deployment and management.

Automates the following tasks:
- Backing up the database
- Patching the database
- Upgrading the database
- Tuning the database





<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY2ODE2MzExMV19
-->
