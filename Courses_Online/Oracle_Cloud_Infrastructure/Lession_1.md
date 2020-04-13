# Lession 1

## 1. Cloud Computing
- On-demande self-service (随需应变的自助服务)
- Broad network access
- Resource pooling
- Rapid elasticity (快速弹性)
- Measured service (监控，报告服务)

## 2. Service Models
![IaaS, Paas and SaaS](https://pictshare.net/kkc5uv.png)

## 3. High Availability  objectives

- Full-time availability
- Redundant hardware and software that makes the system available despite failures (具有冗余的硬件和软件使系统可用，尽管发生任何故障).
- Avoid having single points of failure (避免了单点故障).
- When failures occur, the process moves processing performed by the failed component to the backup component  (当系统发生故障时，故障转移进程会将失败组件执行的处理移至备份组件).

## Disaster Recovery (灾难恢复)
Disaster Recovery involves a set of policiesm tools and procedures to enable the recovery of infra and system (它涉及一组策略，工具和过程，以实现技术基础架构和系统的恢复).

In the Disaster Recovery, the keys metrics are:

-   RPO (Recovery Point Objective), 恢复点目标: 意味着公司可以承受的最大数据损失(以时间为单位).
-   RTO (Recovery Time Objective)，恢复时间目标: 意味着你的业务可以承受多少停机时间.

## Cloud Terminology
- Fault Tolerance (容错)
- Scalability (可伸缩性)
	- Scaling Out (horizontal scaling)
	- Scaling up (vertical scaling)
- Elasticity (弹性)
It is the ablity to quickly increase or decrease resourcesNot just limited to virtual machines, it can be your storage. It can be your database. It can be any other load balancer
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNzQyMzY4MDRdfQ==
-->