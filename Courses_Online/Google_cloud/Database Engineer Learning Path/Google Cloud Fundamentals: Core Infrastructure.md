# Introducing Google Cloud
> Source: https://www.polarsparc.com/xhtml/GCP-Core-Infra-1.html
## What is Cloud Computing

Cloud computing is a way of using information technology (IT) that has these five equally important traits.

1. Customers get computing resources that are on-demand and self-service.
2. Customers get access to those resources over the internet, from anywhere.
3. Cloud provider has a big pool of those resources and allocates them to users out of that pool.
4. The resources are elasticwhich means theyre flexible, so customers can be.
5. Customers pay only for what they use, or reserve as they go.

## IaaS and PaaS
- IaaS
    - Raw compute, storage, and network organized similar to a data center
    - Pay for what is allocated

- PaaS
    - Bind application code to libraries that give access to the infrastructure the application needs
    - Pay for what is used

![](https://i.imgur.com/hhFAcr5.png)


## Google Cloud Platform (GCP)
- Compute Engine (IaaS)
- Kubernetes Engine (Hybrid)
- App Engine (PaaS)
- Cloud Functions (Serverless)
- Managed Services (Elastic Resources)

## Google Network
- Network interconnects at more than 90 internet exchanges and more that 100 points of presence worldwide

## GCP Zones and Regions
- A `Zone` is a deployment area - think of it as a logical data center (not physical)

- *Zones* are grouped into `Regions`

- A *Region* is an independent geographic area
    
- All Zones in a *Region* have fast internet connectivity
    
- Think of a *Zone* as a single failure domain within a *Region*
    
- Multi-Region are geographic locations separated by at least 160 kms
    

## GCP Pricing

- Bill by the second for VMs
    
- Compute Engine offers sustained use discounts
    
- If an instance runs 25% of a month, GCP gives discount for every incremental minute of use
    

# GCP Resource Hierarchy

## Projects, Folder, and Organization Nodes

- `Projects` are used to organize resources in GCP
    
- *Projects* are used to group related resources in GCP
    
- Optionally, *Projects* may be organized into `Folders`
    
- All *Folders* and *Projects* used by a company is brought under an `Organization` node
    
- *Projects*, *Folders*, and *Organization* nodes are places where the security policies can be defined
    
- Policies are inherited downward in the hierarchy (Inheritence is transitive)
    
- Each *Project* is a separate compartment and each resource belongs to exactly one *Project*
    
- Each *Project* has a name and an ID that the user assigns
    
- *Project ID* is a permanent, unchangeable identifier and has to be unique across GCP
    
- GCP assigns a unique *Project number*
    
- To use a *Folder* we need an *Organization* at the top
    
- Most firms want the ability to have a centralized visibility on how the resources are being used and to apply security policies centrally. That is what the *Organization* node is for
    
- Use the *Googe Cloud Identity* to create an Organization node
    

# Identity and Access Management

## Roles and Service Account

- Who (identity), do What (roles), on Which (resources)
    
- Primitive roles - `Owner`, `Editor`, `Viewer`
    
- *Viewer* can examine but not change state
    
- *Editor* is *Viewer* + can change state
    
- *Owner* is *Editor* + manage roles and permissions + setup billing
    
- *InstanceAdmin* role is specific to Compute Engine and can perform the actions - listing, reading, & changing the VM configuration + starting & stopping the VM
    
- Custom roles only apply to *Project* or *Organization* nodes (and **NOT** *Folder*)
    
- Service accounts are named with an email address and use cryptographic keys to access resources
    
- Service accounts are similar to other cloud resources - they can have IAM policies attached to it
    

# Virtual Private Cloud (VPC) Network

## Virtual Private Cloud (VPC) Network Concepts

- VPCs connect GCP resources to each other and to the internet
    
- Many users get started by defining their own VPC inside their *Project*. For getting started quick (not for PROD), one can use the *Default* VPC
    
- Use firewall rules to - segment networks, restrict access to instances, and create static routes to forward traffic to specific destinations
    
- VPCs have `Global` scope in GCP
    
- VPCs can have subnets in any GCP region worldwide and subnets can span the zones that make up the region
    
- One can have resources in different zones in the same subnet. For example, one can have VMs in two different zones in the same subnet to build resilient solutions
    
- One can dynamically increase the size of a subnet in a custom network by expanding the range of the IP address allocated to it
    
- Dynamically adjusting a subnet does not affect the already configured VMs
    
- Subnets have `Regional` scope
    

# Google Compute Engine (GCE)

## Compute Engine Concepts

- VMs can be created by either using the GCP Console or the `gcloud` command-line tool
    
- VMs can run **Linux** and **Windows** server images provided by Google or customized versions of these images. One can also import and run images provided by the customer
    
- There are two types of storage options for the VMs - `Local` storage and `Persistent` storage
    
- If applications need a high performance scratch space, attach a **Local** SSD storage
    
- The contents of a Local SSD storage are destroyed when the VM terminates
    
- **Persistent** storage are of two types - **Standard** or **SSD**. The default is **Standard**
    
- Many users want their VMs to always come up with certain configuration (with certain software installed) on the first boot. It is very common to pass GCP VM `Startup` scripts that do just that
    
- One can take `Snapshots` of a VM disks as backups or to use them to migrate a VM to another region
    
- One can save a lot of money with `Preemptive` VMs. Make sure that the application is able to be stopped and restarted
    

# VPC Capabilities

## Important VPC Capabilities

- Much like physical networks, VPCs have `Routing Tables`. They are used to forward traffic from one instance to another instance within the same network, across sub-networks, and between GCP zones without requiring an external IP address
    
- VPC `Firewalls` and routing tables are built in and don't have to provisioned or managed
    
- VPCs provide a globally distributed firewall that can be used to control access to instances for both incoming and outgoing traffic
    
- One can define firewall rules in terms of metadata tags on Compute Engine instances. For example, one can tag all web servers with the name "web" and write a firewall rule saying that traffic on ports 80 or 443 is allowed into all VMs with the "web" tag no matter what their IP address happens to be
    
- VPCs like any other GCP resources belong to GCP Projects. If a company has several GCP Projects and the VPCs need to talk to each other, then that can be achieved using VPC **Peering**
    
- One can also leverage a `Shared` VPC to control who and what in one Project can interact with a VPC in another Project through the use of IAM policies
    
- `Cloud Load Balancing` is a fully distributed and managed software-defined load balancer service for all traffic (HTTP and HTTPS, other TCP and SSL traffic, and UDP traffic) coming in to the auto-scaled VMs
    
- With *Cloud Load Balancing*, a **single anycast IP** frontends all the backend instances in regions around the world. It provides **cross-region load balancing**, including **automatic multi-region failover** (if backends become unhealthy)
    
- *Cloud Load Balancing* reacts quickly to changes in users, traffic, backend health, network conditions, and other related conditions
    
- Use `HTTPS Load Balancer` for *cross regional load balancing of a web application*
    
- For Secure Sockets Layer traffic that is **NOT** HTTP, use the `Global SSL Proxy Load Balancer`
    
- For **other TCP traffic** that **does not use** Secure Sockets Layer, use the `Global TCP Proxy Load Balancer`
    
- The *Global SSL Proxy Load Balancer* and *Global TCP Proxy Load Balancer* proxy services **only work for specific port numbers** in the TCP protocol
    
- To load balance **UDP traffic or traffic on any port number** (across GCP regions) with the `Regional Load Balancer`
    
- To load balance traffic inside your project (between the presentation layer and the business logic layer of your application), use the `Internal Load Balancer`. It accepts traffic on a GCP internal IP address and load balances it across Compute Engine VMs
    
- *Internal Load Balancer* has **Regional** scope
    
- The following is a side-by-side comparison of the various Load Balancing options in GCP:

![](https://i.imgur.com/PTGjg0l.png)

![](https://cloud.google.com/static/load-balancing/images/choose-lb.svg)


- `DNS` is what translates internet host names to addresses. Google has a highly developed DNS infrastructure with the IP 8.8.8.8 and makes it available so that everybody can take advantage of it
    
- GCP offers `Cloud DNS` to help the world find the internet host names and addresses of applications you build in GCP. It is a managed DNS service running on the same infrastructure as Google. It has low latency and high availability and it is a cost-effective way to make your applications and services available to your users
    
- The DNS information you publish is served from redundant locations around the world. *Cloud DNS* is also programmable
    
- Google has a global system of edge caches. You can use `Google Cloud CDN` to accelerate content delivery from your application. Your customers will experience lower network latency
    
- Once you've set up HTTPS Load Balancing, simply enable *Cloud CDN* with a single checkbox
    
- Lots of GCP customers want to interconnect their other networks to their Google VPCs, such as on-premises networks or their networks in other clouds. They can start with a *Virtual Private Network* connection over the internet using the **IPSEC protocol**. To make that dynamic, they use a GCP feature called `Cloud Router`. *Cloud Router* lets your other networks and your Google VPC exchange route information over the VPN using the **Border Gateway Protocol**. For instance, if you add a new subnet to your Google VPC, your on-premises network will automatically get routes to it
    
- Some customers don't want to use the internet either because of security concerns or because they need more reliable bandwidth. In those cases, they can consider peering with Google using `Direct Peering`. Peering here means putting a router in the same public data center as a Google point of presence and exchanging traffic. Google has more than 100 points of presence across the world
    
- One downside of peering though is that it isn't covered by a Google service level agreement
    
- Customers who want the highest uptimes for their interconnection with Google should use `Dedicated Interconnect`, in which customers get one or more direct private connections to Google. If these connections have topologies that meet Google's specifications, they can be covered by up to a 99.99 percent SLA. These connections can be backed up by a VPN for even greater reliability
    
- The following is a comparison of the various Interconnect options in GCP:
    
![](https://i.imgur.com/NTajR7c.png)


## Compute Engine Lab

The following are some of the **gcloud** commands from the **Compute Engine** lab:

- List all the zones in a region (ex: us-central1):
    
```
gcloud compute zones list | grep us-central1
```
- Set the Compute Engine zone (ex: us-central1-b) to use:
    
```
gcloud config set compute/zone us-central1-b
```

- Create a VM of type n1-standard-1 with Debian Linux image using the default VPC network:
    
```
gcloud compute instances create "my-vm-2" \\

\--machine-type "n1-standard-1" \\

\--image-project "debian-cloud" \\

\--image "debian-9-stretch-v20190213" \\

\--subnet "default"
```