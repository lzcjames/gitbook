# Core Azure Services (30-35%)

## The core Azure architectural components

### Region (e.g. North Europe, West Europe, Germany North, Germany West Central) 

A region is a geographical area on the planet containing at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.

### Region Pair

Each Azure region is always paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away. This approach allows for the replication of resources (such as virtual machine storage) across a geography that helps reduce the likelihood of interruptions due to events such as natural disasters, civil unrest, power outages, or physical network outages affecting both regions at once. 

### Geography (Americas, Europe, Asia Pacific, Middle East and Africa)

An Azure geography is a discrete market typically containing two or more regions that preserve data residency and compliance boundaries.

### Availability Sets

Availability Sets comprise of update and fault domains.

- Update Domain

  When a maintenance event occurs, the update is sequenced through update domains. 
  
- Fault Domain

  Fault domains provide for the physical separation of a workload across different hardware in the datacenter.

### Availability Zone (e.g. Zone 1, Zone 2, Zone 3 - within a particular region) 

Availability Zones are physically separate datacenters within an Azure region. Each Availability Zone is made up of one or more datacenters equipped with independent power, cooling, and networking.

### Determine availability options

<img src="https://docs.microsoft.com/en-us/learn/wwl-azure/discuss-core-azure-architectural-components/media/availability-options.png" width="780" height="280">

**SLA:** The Service Level Agreement (SLA) describes Microsoft's commitments for uptime and connectivity.


- A single virtual machine with premium storage has an SLA of 99.9%. You can quickly migrate existing virtual machines to Azure through “lift and shift”. Lift and shift is a no-code option where each application is migrated as-is, providing the benefits of the cloud without the risks or costs of making code changes.

- By placing virtual machines in an availability set, you protect against datacenter failures and increases the SLA to 99.95%.

- Adding virtual machines to availability zones protects from entire datacenter failures and increases the SLA to 99.99%, which is highest level of protection that is provided.

- For multi-region disaster recovery, region pairs protect and provide data residency boundaries.

### Resource Group 

Resource groups are a fundamental element of the Azure platform. A resource group is a **logical container** for resources deployed on Azure

### Azure Resource Manager

Azure Resource Manager is the interface for managing and organizing cloud resources. Think of Resource Manager as a way to deploy cloud resources

With Azure Resource Manager, you can:

- Deploy Application resources. 
- Organize resources. 
- Control access and resources.


## Azure Compute Services

| Azure Compute Services |  |
|--|--|
| Virtual Machines  | Windows or Linux virtual machines (VMs) hosted in Azure |
| Virtual Machine Scale Sets | Scaling for Windows or Linux VMs hosted in Azure |
| App Services | PaaS offerings to build, deploy, and scale enterprise-grade web, mobile, and API apps.  |
| Azure Functions | An event-driven, serverless compute service |


## Container services

Azure supports Docker containers, There are two ways to manage both Docker and Microsoft-based containers in Azure.

| Azure Compute Services |  |
|--|--|
| Azure Container Instances  | Offers the fastest and simplest way to run a container. <br> Without having to manage any virtual machines or adopt any additional services. <br> It is a PaaS offering. |
| Azure Kubernetes Service | A **complete orchestration service** for containers with distributed architectures and large volumes of containers. |

ps. Orchestration is the task of automating and managing a large number of containers and how they interact.

## Azure network services

| Azure network services |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-4.png" width="30" height="30"> Azure Virtual Network  | Connects VMs to incoming Virtual Private Network (VPN) connections |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-2.png" width="30" height="30"> Azure Load Balancer | Balances inbound and outbound connections to applications or service endpoints |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-gateway.png" width="30" height="30"> Azure VPN Gateway | Accesses Azure Virtual Networks through high-performance VPN gateways |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-app-gateway.png" width="30" height="30"> Azure Application Gateway | Optimizes app server farm delivery while increasing application security |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-1.png" width="30" height="30"> Azure Content Delivery Network | Delivers high-bandwidth content to customers globally |

## Azure Storage

| Azure Storages |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-blob.png" width="30" height="30"> Container(Blob) Storage  | Storage service for very large objects, such as video files or bitmaps. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-disks.png" width="30" height="30"> Disk Storage | Provides disks for virtual machines, applications, and other services. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-files.png" width="30" height="30"> File Storage | Azure Files offers fully-managed file shares in the cloud. |
| <img src="https://azurecomcdn.azureedge.net/cvt-6ef370aa9a2f3452dfe1c2fdc1f3ba16dd38153b9e5a25c85872818eb280a39b/images/page/solutions/backup-archive/back-up-archive-banner.png" width="30" height="30"> Archive Storage | Storage facility for data that is rarely accessed. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-queue.png" width="30" height="30"> Queues | To store lists of messages to be processed asynchronously. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-table.png" width="30" height="30"> Tables| Stores large amounts of structured data, uses NoSQL |

## Azure database services

| Azure Database Services |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-cosmos-db.png" width="30" height="30"> Azure Cosmos DB  | Globally distributed database that supports NoSQL options. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-3.png" width="30" height="30"> Azure SQL Database | Fully managed relational database with auto-scale, integral intelligence, and robust security. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-db-migration.png" width="30" height="30"> Azure Database Migration |  Fully managed service designed to enable seamless migrations from multiple database sources to Azure data platforms with minimal downtime (online migrations). |

<img src="https://azurecomcdn.azureedge.net/cvt-6ef370aa9a2f3452dfe1c2fdc1f3ba16dd38153b9e5a25c85872818eb280a39b/images/page/services/database-migration/discover.png" width="840" height="480">

## Azure Marketplace

The Marketplace allows customers to find, try, purchase, and provision applications and services from hundreds of leading service providers, all certified to run on Azure. Azure Marketplace is a service on Azure that helps connect end users with Microsoft partners, independent software vendors (ISVs), and start-ups that are offering their solutions and services, which are optimized to run on Azure.

<img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/marketplace.png" width="810" height="540">

## Azure IoT services

Two of the core Azure IoT service types are Azure IoT Central, and Azure IoT Hub.

| Azure IoT service types |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-1.png" width="30" height="30"> IoT Central | Fully-managed global IoT software as a service (SaaS) solution that makes it easy to connect, monitor, and manage your IoT assets at scale. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-2.png" width="30" height="30"> Azure IoT Hub | FMessaging hub that provides secure communications and monitoring between millions of IoT devices. |

## Big Data and Analytics

| Big Data and Analytics |  |
|--|--|
| Azure Synapse Analytics(Azure SQL Data Warehouse) | Run analytics at a massive scale using a cloud-based Enterprise Data Warehouse (EDW) that leverages massive parallel processing (MPP) to run complex queries quickly across petabytes of data. |
| Azure HDInsight | Process massive amounts of data with managed clusters of Hadoop clusters in the cloud. |
| Azure Data Lake Analytics | On-demand ("pay as you go") scalable analytics service that allows you to write queries to transform your data and extract valuable insights. |

## Azure Artificial Intelligence

| Azure Artificial Intelligence |  |
|--|--|
| Azure Cognitive Services | Cognitive services are a collection of domain-specific pre-trained AI models that can be customized with your data. They are categorized broadly into vision, speech, language, and search. |
| Azure Machine Learning Service | Cloud-based environment you can use to develop, train, test, deploy, manage, and track machine learning models. It can auto-generate a model and auto-tune it for you. It will let you start training on your local machine, and then scale out to the cloud. |

## Serverless Computing

https://www.taygan.co/blog/2019/02/07/az-900-azure-fundamentals-exam-preparation
https://docs.microsoft.com/en-us/learn/modules/identify-azure-solutions/6-define-serverless-computing


