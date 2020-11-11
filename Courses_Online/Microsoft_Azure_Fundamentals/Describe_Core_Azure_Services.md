# Describe Core Azure Services (15-20%)

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

It provides a management layer that enables you to create, update, and delete resources in your Azure account. You use management features like access control, locks, and tags to secure and organize your resources after deployment.

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

<img src="https://docs.microsoft.com/en-us/learn/wwl-azure/discuss-core-azure-architectural-components/media/availability-options.png"/>

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

| Serverless computing |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-functions.png" width="30" height="30"> Azure Functions | An event-driven - often via a REST request, timer, or message. Serverless compute service, scale automatically. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-logic-app.png" width="30" height="30"> Azure Logic Apps | Help you automate and orchestrate tasks, business processes, and workflows when you need to integrate apps, data, systems, and services across enterprises or organizations. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-eventgrid.png" width="30" height="30"> Azure Logic Apps |Allows you to easily build applications with event-based architectures. It's a fully-managed, intelligent event routing service that uses a publish-subscribe model for uniform event consumption. |

## Azure DevOps

DevOps  (Development and Operations) brings together people, processes, and technology, automating software delivery to provide continuous value to your users. Azure DevOps Services allows you to create, build, and release pipelines that provide continuous integration, delivery, and deployment for your applications. 

Some of the main DevOps services available with Azure are Azure DevOps Services, and Azure DevTest Labs.

| DevOps services |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-devops.png" width="30" height="30"> Azure DevOps Services | An event-driven - often via a REST request, timer, or message. Serverless compute service, scale automatically. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-devtest.png" width="30" height="30"> Azure Lab Services | a service that helps developers and testers quickly create environments in Azure, while minimizing waste and controlling cost. |

## Azure Management tools

| Azure Management tools |  |
|--|--|
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/differentiate-azure-management-tools/media/icon-portal.png" width="30" height="30"> Azure portal | The portal is a web-based administration site that lets you interact with all of your subscriptions and resources you have created. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/differentiate-azure-management-tools/media/icon-3.png" width="30" height="30"> Azure PowerShell | A module that you add to Windows PowerShell or PowerShell Core that enables you to connect to your Azure subscription and manage resources. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/differentiate-azure-management-tools/media/icon-2.png" width="30" height="30"> Azure Command Line Interface (CLI) | A cross-platform command-line program that connects to Azure and executes administrative commands on Azure resources. Cross-platform means that it can be run on Windows, Linux, or macOS. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/differentiate-azure-management-tools/media/icon-shell.png" width="30" height="30"> Azure Cloud Shell | A browser-based scripting environment in your portal. It provides the flexibility of choosing the shell experience that best suits the way you work. Linux users can opt for a Bash experience, while Windows users can opt for PowerShell. |
| <img src="https://docs.microsoft.com/en-us/learn/wwl-azure/identify-azure-solutions/media/icon-devtest.png" width="30" height="30"> Azure Lab Services | a service that helps developers and testers quickly create environments in Azure, while minimizing waste and controlling cost. |
| <img src="https://www.e-apostolidis.gr/wp-content/uploads/2018/10/advisor.png" width="60" height="30"> Azure Advisor | A free service built into Azure that provides recommendations on high availability, security, performance, and cost. Advisor analyzes your deployed services and looks for ways to improve your environment across those four areas. |



