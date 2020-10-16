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
