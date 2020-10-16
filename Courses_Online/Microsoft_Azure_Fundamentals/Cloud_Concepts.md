# Describe Cloud Concepts (15-20%)

:notebook: Exam Preparation Guide:  https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE3VwUY

:love_letter: Source from https://www.taygan.co/blog/2019/02/07/az-900-azure-fundamentals-exam-preparation 

## Basic Terms

### High Availability (HA)
The ability of the application to continue running in a healthy state, without significant downtime. By "healthy state," we mean the application is responsive, and users can connect to the application and interact with it.

### Scalability
Increase or decrease the resources and services used based on the demand or workload at any given time. Vertical Scaling (aka "scaling up) - add more resources to existing servers. Horizontal Scaling (aka "scaling out) - add more servers.

### Vertical Scaling (aka "scaling up")
The process of adding resources to increase the power of an existing server (e.g. adding a faster CPU, additional CPUs, more memory).

### Horizontal Scaling (aka "scaling out")
The process of adding more servers that function together as one unit (e.g. adding more servers).

### Elasticity
Automatically add or remove resources based on demand.

### Cloud Agility
Cloud agility is the ability to rapidly change an IT infrastructure in order to adapt to the evolving needs of the business (e.g. if your service peaks one month, you can scale to demand and pay a larger bill for the month. If the following month the demand drops, you can reduce the used resources and be charged less).

### Fault Tolerance
Redundancy is often built into cloud services architecture so if one component fails, a backup component takes its place. This is referred to as fault tolerance and it ensures that your customers aren't impacted when an unexpected accident occurs.

### Disaster Recovery
The ability to recover from rare but major incidents: non-transient, wide-scale failures, such as service disruption that affects an entire region. Disaster recovery includes data backup and archiving, and may include manual intervention, such as restoring a database from backup.

### Economies of Scale
Economies of scale is the ability to do things more efficiently or at a lower-cost per unit when operating at a larger scale (e.g. the ability to acquire hardware at a lower cost than if a single user or smaller business were purchasing it, cloud providers can also make deals with local governments and utilities to get tax savings, lower pricing on power, cooling, and high-speed network connectivity between sites).

## Compare CapEx vs OpEx

### Capital Expenditure (CapEx)
CapEx is the spending of money on physical infrastructure up front, and then deducting that expense from your tax bill over time. CapEx is an upfront cost, which has a value that reduces over time.

### Operational Expenditure (OpEx)
OpEx is spending money on services or products now and being billed for them now. You can deduct this expense from your tax bill in the same year. There is no upfront cost, you pay for a service or product as you use it.

## Define consumption-based models

Cloud service providers operate on a **consumption-based model**, which means that end users only pay for the resources that they use. Whatever they use is what they pay for.

A consumption-based model has many benefits, including:

- No upfront costs.
- No need to purchase and manage costly infrastructure that they may or may not use to its fullest.
- The ability to pay for additional resources when they are needed.
- The ability to stop paying for resources that are no longer needed.

## IaaS vs PaaS vs SaaS

![IaaS, Paas and SaaS](https://imgur.com/lpDPe5k.png)


|      | User                                                                                                                           | Cloud Provider                                                                                                                                   |
|------|--------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| IaaS | SaPurchase, installation, configuration, and management of their own software operating systems, middleware, and applications. | Responsible for ensuring that the underlying cloud infrastructure (such as virtual machines, storage, and networking) is available for the user. |
| PaaS | Responsible for the development of their own applications.                                                                     | Responsible for operating system management, and network and service configuration.                                                              |
| SaaS | Users just use the application software; they are not responsible for any maintenance or management of that software.          | The cloud provider is responsible for the provision, management, and maintenance of the application software.                                    |

##  Public, Private and Hybrid cloud models

### Public Cloud (most common)

This is the most common deployment model. In this case, you have no local hardware to manage or keep up-to-date – everything runs on your hosting provider’s hardware.

### Private Cloud (2nd most common)

In a private cloud, you create a cloud environment in your own datacenter and provide self-service access to compute resources to users in your organization.

### Hybrid Cloud (stepping stone to cloud, segmenting work, cloud bursting)

A hybrid cloud combines public and private clouds, allowing you to run your applications in the most appropriate location.

### Compare & Contrast (Advantages & Disadvantages)

|  | **Advantages** | **Disadvantages** |
|--|--|--|
| Public  | :+1: High Scalability/Agility <br> :+1: PAYG (No CapEx, OpEx model) <br> :+1: Not responsible for hardware maintenance <br> :+1: Minimal technical knowledge required| :shit: May not be able to meet specific security requirements <br> :shit: May not be able to meet specific compliance requirements <br> :shit: You don't own the hardware and may not be able to manage them as you wish <br> |
| Private | :+1: You have complete control <br> :+1: Can meet strict security and compliance requirements | :shit: Upfront CapEx costs <br> Owning equipment limits agility to scale <br> :shit: Requires high technical knowledge |
| Hybrid | :+1: Advantages of both Public and Private | :shit: Can be more expensive than selecting one deployment model <br> :shit:  Can be more complicated to set up and manage |
