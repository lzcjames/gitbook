# OCI Architecture

## OCI Regions

Region is localized geographic area, comprised of one or more Availability Domains (AD).

## Availability Domains

ADs is one or more **fault-tolerant**, **isolated data centers** located within a region, but connected to each other by a low latency, high bandwidth network.

## Fault Domains

3 FDs in one AD.

Grouping of hardware and infrastructure within an AD to provide anti-affinity (**logical data center**)
故障域是在AD中用于提供反关联性**1**的硬件和基础结构的分组，FD也称为**逻辑数据中心** . 

Not share single points of hardware failure such as same physical server, physical rack or power distribution unit.
不共享单个硬件故障点，例如同一物理服务器，物理机架或配电单元。



## High Availability Design

1. Region is launched one by one new geograpgique likes US, UK, CN with **one AD**
一个Region建立在一个新的地理区域，并只含**一个AD**

2. For any region with one AD, a **second AD** is used to enable further option for **Disaster Recovery** and **Data Residency** within a year
对于只含一个AD的Region, 第二个备用AD在一年内提供**灾难恢复**和**数据驻留**服务

3. **Avoid single points of failure**

- different FDs in one AD in one Region



To avoid single points of failure, first thing should you have always **multiple instances** of the same type. So you have **a second copy application** in the second FD. They are all stateless.

Don't put it in the same FD, because this FD can be unavailable as well.

- In different ADs for multiple Regions



Between 2 ADs, we use *Data Guard* to manage data. And in this case, if your whole AD1 becomes unavailable, you still have your same application up and running in AD2, because you're replicating your data to AD2 in the same Region, that's saying avoid single points of failure.

## Compartments

A compartment is a collection of related resources. It helps you **isolate** and **control access** to your resources.

- Each resource belongs to a single compartment
- Resources can interact with other resources in different compartments
- Resources and compartments can be added and deleted anytime
- Resources can be removed from one compartment to another
- Resources from multiple regions can be in the same compartment
- Compartments can be nested, 嵌套 (six levels)
- Access control by writing Policies
- Analyze cost and assign budget for resources in compartments





---
**1:** 反关联性规则, 比如将一组虚拟机放置在不同的主机上，这样可以防止所有虚拟机在单个主机发生故障时立即发生故障

# OCI Architecture

## OCI Regions

Region is localired geographic area, comprised of one or more Availablity Domains (AD).

## Availability Domains

ADs is one or more **fault-tolerant**, **isolated data centers** located within a region, but conntected to each other by a low latency, high bandwidth network.

## Fault Domains

3 FDs in one AD.

Grouping of hardware and infrastructure within an AD to provide anti-affinity (**logical data center**)
故障域是在AD中用于提供反关联性**1**的硬件和基础结构的分组，FD也称为**逻辑数据中心** . 

Not share single points of hardware failure such as same physical server, physical rack or power distribution unit.
不共享单个硬件故障点，例如同一物理服务器，物理机架或配电单元。



## High Availability Design

1. Region is launched one by one new geograpgique likes US, UK, CN with **one AD**
一个Region建立在一个新的地理区域，并只含**一个AD**

2. For any region with one AD, a **second AD** is used to enable further option for **Disaster Recovery** and **Data Residency** within a year
对于只含一个AD的Region, 第二个备用AD在一年内提供**灾难恢复**和**数据驻留**服务

3. **Avoid single points of failure**

- In different FDs in one AD in one Region



To avoid single points of failure, first thing is you should always have **multiple instances** of the same type. So you have **a second copy application** in the second FD. They are all stateless.
Don't put it in the same FD, because this FD can be unavailable as well.

- In different ADs for multiple Regions



Between 2 ADs, we use *Data Guard* to manage data. And in this case, if your whole AD1 becomes unavailable, you still have your same application up and running in AD2, because you're replicating your data to AD2 in the same Region, that's saying avoid single points of failure.

## Compartments

A compartment is a collection of related resources. It helps you **isolate** and **control access** to your resources.

- Each resource belongs to a single compartment
- Resources can interact with other resources in different compartments
- Resources and compartments can be added and deleted anytime
- Resources can be removed from one compartment to another
- Resources from multiple regions can be in the same compartment
- Compartments can be nested, 嵌套 (six levels)
- Access control by writing Policies
- Analyze cost and assign budget for resources in compartments





---
**1:** 反关联性规则, 比如将一组虚拟机放置在不同的主机上，这样可以防止所有虚拟机在单个主机发生故障时立即发生故障
