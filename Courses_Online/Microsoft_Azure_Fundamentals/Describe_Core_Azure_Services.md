
> Describe Core Azure Services (15-20%)

## [The core Azure architectural components](https://docs.microsoft.com/en-us/learn/modules/azure-architecture-fundamentals/)

### Azure Subscriptions

A subscription provides you with *authenticated* and *authorized* access to Azure products and services, it also allows you to provision resources.

An Azure subscription is a logical unit of Azure services that links to an Azure account, which is an identity in Azure Active Directory (Azure AD) or in a directory that Azure AD trusts.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-architecture-fundamentals/media/subscriptions-expanded.png" width="650" height="250"/>

### Azure Management Groups

Azure management groups provide a level of scope above subscriptions, all subscriptions within a management group automatically inherit the conditions applied to the management group.

For example, you can apply policies to a management group that limits the regions available for VM creation. This policy would be applied to all management groups, subscriptions, and resources under that management group by only allowing VMs to be created in that region.

Important facts about management groups:

- 10,000 management groups can be supported in a single directory.
- A management group tree can support up to six levels of depth. This limit doesn't include the root level or the subscription level.
- Each management group and subscription can support only one parent.
- Each management group can have many children.
- All subscriptions and management groups are within a single hierarchy in each directory.

### Azure Resource Groups

Resource is a manageable item that's available through Azure. Virtual machines (VMs), storage accounts, web apps, databases, and virtual networks are examples of resources.

Resource groups are a fundamental element of the Azure platform. A resource group is a **logical container** for resources deployed on Azure, Resource groups can't be nested.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-architecture-fundamentals/media/resource-group.png" width="280" height="120"/>

### Azure Resource Manager

Azure Resource Manager is the interface for managing and organizing cloud resources. Think of Resource Manager as a way to deploy cloud resources

With Azure Resource Manager, you can:

- Deploy Application resources. 
- Organize resources. 
- Control access and resources.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-architecture-fundamentals/media/consistent-management-layer-expanded.png" width="600" height="320"/>

#### The benefits of using Resource Manager

- Manage your infrastructure through declarative templates rather than scripts. A Resource Manager template is a JSON file that defines what you want to deploy to Azure.
- Deploy, manage, and monitor all the resources for your solution as a group, rather than handling these resources individually.
- Redeploy your solution throughout the development life cycle and have confidence your resources are deployed in a consistent state.
- Define the dependencies between resources so they're deployed in the correct order.
- Apply access control to all services because RBAC is natively integrated into the management platform.
- Apply tags to resources to logically organize all the resources in your subscription.
- Clarify your organization's billing by viewing costs for a group of resources that share the same tag.

### Region (e.g. North Europe, West Europe, Germany North, Germany West Central) 

A region is a geographical area on the planet containing at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.

#### The benefits of regions

Azure has more global regions than any other cloud provider. These regions give you the flexibility to bring applications closer to your users no matter where they are. Global regions provide better scalability and redundancy. They also preserve data residency for your services.

### Region Pair

Each Azure region is always paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away. 
This approach allows for the replication of resources (such as virtual machine storage) across a geography that helps reduce the likelihood of interruptions.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-architecture-fundamentals/media/region-pairs-expanded.png" width="900" height="220"/>

#### Additional advantages of region pairs

-   If an extensive Azure outage occurs, one region out of every pair is prioritized to make sure at least one is restored as quickly as possible for applications hosted in that region pair.
-   Planned Azure updates are rolled out to paired regions one region at a time to minimize downtime and risk of application outage.
-   Data continues to reside within the same geography as its pair (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.

### Availability Zone (e.g. Zone 1, Zone 2, Zone 3 - within a particular region) 

Availability Zones are physically separate datacenters within an Azure region. Each Availability Zone is made up of one or more datacenters equipped with independent power, cooling, and networking.

Availability zones are connected through high-speed, private fiber-optic networks.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-architecture-fundamentals/media/availability-zones-expanded.png" width="600" height="500" />

## Describe core resources available in Azure

### Azure Compute Services

| Azure Compute Services | Service function  | Advantages |
|--|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-compute-fundamentals/media/icon-virtual-machine.png" width="30" height="30"> [Virtual Machines](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/azure-virtual-machines)  |Windows or Linux virtual machines (VMs) hosted in Azure | - Total control over OS<br>- The ability to run custom software. <br>- To use custom hosting configurations. |
| <img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-compute-fundamentals/media/icon-app-service.png" width="30" height="30"> [App Services](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/azure-app-services) | PaaS offerings to build, deploy, and scale enterprise-grade web, mobile, and API apps.  | - language upon your choices without managing infra<br> - automatic scaling and high availability <br> deploy automated from GitHub, Azuez DevOps etc
| <img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-compute-fundamentals/media/icon-functions.png" width="30" height="30"> [Azure Functions](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/azure-functions) | An event-driven, serverless compute service | - Reduce costs <br> - High availability <br> - Write just fouctions, not applications |
| <img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-compute-fundamentals/media/icon-container-instance.png" width="30" height="30"> [Azure Container Instances](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/azure-container-services)  | Offers the fastest and simplest way to run a container. <br> Without having to manage any virtual machines or adopt any additional services. <br> It is a PaaS offering. | - Reduce costs <br> - High availability <br> - Fault tolerance |
| <img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-compute-fundamentals/media/icon-kubernetes.png" width="30" height="30"> [Azure Kubernetes Service](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/azure-container-services) | A **complete orchestration<sup>1</sup> service** for containers with distributed architectures and large volumes of containers. | Idem |
| <img src="https://azure.microsoft.com/svghandler/virtual-desktop/" width="35" height="30"> [Windows Virtual Desktop](https://docs.microsoft.com/en-us/learn/modules/azure-compute-fundamentals/windows-virtual-desktop) | It's a Windows desktop and application virtualization service that runs on the cloud. | - Facility for remote workers <br> - Reduce costs <br> - Enhance security <br> - Simplified management |


**Orchestration<sup>1</sup>**: It is the task of automating and managing a large number of containers and how they interact.


## Azure network services

| Azure network services |  Service function  | Advantages |
|--|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-4.png" width="30" height="30"> Azure Virtual Network  | Connects VMs to incoming Virtual Private Network (VPN) connections | 
| <img src="https://symbols.getvecta.com/stencil_28/37_expressroute.796d8d6f8b.png" width="30" height="30"> Azure ExpressRoute  | Connects to Azure over high-bandwidth dedicated secure connections |
| <img src="https://abouconde335669239.files.wordpress.com/2019/08/azure-vnet-peering.png" width="30" height="30"> Virtual network peering | enables you to seamlessly connect two or more [Virtual Networks](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview) in Azure |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-gateway.png" width="30" height="30"> Azure VPN Gateway | Accesses Azure Virtual Networks through high-performance VPN gateways |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-app-gateway.png" width="30" height="30"> *Azure Application Gateway* | *Optimizes app server farm delivery while increasing application security* |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-2.png" width="30" height="30"> *Azure Load Balancer* | *Balances inbound and outbound connections to applications or service endpoints* |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-1.png" width="30" height="30"> *Azure Content Delivery Network* | *Delivers high-bandwidth content to customers globally* |

## Azure Storage

| Azure Storages | Service function  | Advantages |
|--|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-blob.png" width="30" height="30"> Container(Blob) Storage  | Storage service for very large objects, such as video files or bitmaps. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-disks.png" width="30" height="30"> Disk Storage | Provides disks for virtual machines, applications, and other services. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-files.png" width="30" height="30"> File Storage | Azure Files offers fully-managed file shares in the cloud. |
| <img src="https://azurecomcdn.azureedge.net/cvt-6ef370aa9a2f3452dfe1c2fdc1f3ba16dd38153b9e5a25c85872818eb280a39b/images/page/solutions/backup-archive/back-up-archive-banner.png" width="30" height="30"> *Archive Storage* | *Storage facility for data that is rarely accessed*. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-queue.png" width="30" height="30"> *Queues* | *To store lists of messages to be processed asynchronously*. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-table.png" width="30" height="30"> *Tables*| *Stores large amounts of structured data, uses NoSQL* |

Azure storage offers **different access tiers**, which allow you to store blob object data in the most cost-effective manner. The available access tiers include:

-   **Hot**  - Optimized for storing data that is accessed frequently.
-   **Cool**  - Optimized for storing data that is infrequently accessed and stored for at least 30 days.
-   **Archive**  - Optimized for storing data that is rarely accessed and stored for at least 180 days with flexible latency requirements (on the order of hours).

## Azure database services

| Azure Database Services | Service function  | Advantages |
|--|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-cosmos-db.png" width="30" height="30"> Azure Cosmos DB  | Globally distributed database that supports NoSQL options. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-3.png" width="30" height="30"> Azure SQL Database | Fully managed relational database with auto-scale, integral intelligence, and robust security. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-3.png" width="30" height="30"> Azure Database for MySQL | Fully managed and scalable MySQL relational database with high availability and security |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-3.png" width="30" height="30"> Azure Database for PostgreSQL | Fully managed and scalable PostgreSQL relational database with high availability and security |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/icon-db-migration.png" width="30" height="30"> *Azure Database Migration* |  *Fully managed service designed to enable seamless migrations from multiple database sources to Azure data platforms with minimal downtime (online migrations).* |

##### Azure SQL Managed Instance

SQL Managed Instance has near 100% compatibility with the latest SQL Server (Enterprise Edition) database engine, providing a native [virtual network (VNet)](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview) implementation that addresses common security concerns, and a [business model](https://azure.microsoft.com/pricing/details/sql-database/) favorable for existing SQL Server customers.

## Azure Marketplace

The Marketplace allows customers to find, try, purchase, and provision applications and services from hundreds of leading service providers, all certified to run on Azure. Azure Marketplace is a service on Azure that helps connect end users with Microsoft partners, independent software vendors (ISVs), and start-ups that are offering their solutions and services, which are optimized to run on Azure.

<img src="https://docs.microsoft.com/en-us/learn/wwl-azure/define-core-azure-services-products/media/marketplace.png" width="810" height="540">
