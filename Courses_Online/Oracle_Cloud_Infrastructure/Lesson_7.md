# OCI Database Services

> OCI DB Options, DB Systems, DB System Backup, DB Systems HA and DR, Autonomous Databases

## OCI DB Options

- Virtual Machine (VM DB Systems)
- Bare Metal (BM DB Systems)
- Real Application Clusters (RAC)
- Exadata DB Systems
- Automous
	- Shared
	- Dedicated

<img src="https://imgur.com/vdjmQoO.png" width="730" height="300">

## DB Systems Backup/Restore

- Manual or Automatic backups
- Automatic backups written to Oracle owned object storage buckets.
- Backups run between midnight - 6:00 AM in the DB system's time zone.
- Preset retention periods: , 15, 30, 45 and 60 days (can custom long periods)
- Recover a database from a backup stored in Object Storage

## Oracle Data Guard

- It provides a set of services that create, maintain, manage and monitor one or more standby DBs to enable Oracle DBs to survive disaster and data corruptions.
用于创建, 维护, 管理和监视一个或多个备用数据库从而使Oracle数据库能够在灾难或数据损坏中生存.

- It maintains synchronization between the primary and the standby DB.
它维护主数据库和备用数据库之间的同步.

- So if the primary database becomes unavailable, Oracle Data Guard can switch any standby database to the primary role, minimizing the downtime associated with the outage.
一旦主数据库变得不再可用,Oracle Data Guard可以将任一的备用数据库转变为新主数据库，从而最小化了中断停机时间.
 
  <img src="https://imgur.com/QVAtoqA.png" width="440" height="300">

- 2 modes:
	- Switchover ->planned migration, no data loss	. (when switching a standby DB to primary DB)
	- Failover -> unplanned migration, minimal data loss. (e.g. AD is not available, data corruptions 



#### Active Data Guard
It extends Data Guard, for Extreme Performance Edition and Exdata Service.

## DB Systems HA and DR (in multi ADs)

Using RAC DB + Data Guard so that you are guaranteeing the maximum High Availability Disaster Recovery  and for your database.

<img src="https://imgur.com/DkB0ell.png" width="700" height="300">

## DB Systems HA and DR (in single AD)
If your primary and standby DBs are 2-node RAC DBs in the same AD, only one of the two nodes of the standby DB can be in a FD that does not include any other nodes from either the primary or standby DB.
如图示，








<!--stackedit_data:
eyJoaXN0b3J5IjpbNTMzNTc3Mjc1LDE4MDEyNzg4MzBdfQ==
-->