
# OCI Security

> Shared Security Model, SecurityServices, Identity and Access Management, Data Protection, OS and workload management, Infrastructure protection

## OCI Shared Security Model

In OCI, Oracle maanages **Networking, Storage, Servers** and **Virtualization**,  
and you manage just Operating System, Middleware, Runtime, Data and Applications.

The responbility of OCI Shared Security Model is **security of data-center facilites**

## OCI Security Services

<img src="https://imgur.com/y0XudwR.png" width="720" height="310">

## OCI Identity and Access Management

### IAM

<img src="https://imgur.com/GAZjd4X.png" width="500" height="250">


### Multi-factor Authentication (MFA)

Use of more than one factor to verify a user's identify

<img src="https://imgur.com/O4TeJWP.png" width="450" height="150">

### Federation (联合)

Federation means an identity provider manages your user login and password, and the basic idea is you simplify your authentication. 
Entreprises use **an indentify provider (IdP)** to manage user login/passwords and to authentications.

E.g. Single sign-on (SSO)
<img src="https://qualifio.com/blog/wp-content/uploads/ilustration-sso-1.png" width="280" height="150">

## OCI Data protection

<img src="https://imgur.com/COM8PD7.png" width="700" height="250">


### Key Management

- Managesd service that enables you to encrypt your data using keys that you control.
- Key management provides you with:
    - Centralized key managements capabilities
	- Highly available durable, and secure key storage in hardware security modules (HSM)
	- Integration with select OCI services

### OCI Data safe
- Managed service that provides a complete and integrated set of features for protecting **sensitive and regulated** data in OCI.
- Features include Security Assessment, User Assessment, Data Discovery, Data Masking, and Activity Auditing.
- No extra costs to use

## OCI OS and workload management

### Dedicated VM Host

- Security of Bare MEtal combined with ease and flexibility of VMs
- Single-tenant(单租户): never share HW with another customer's VMs
- Pay only for dedicated VM Host, no addtional charge for the VMs running on it

### Management Service

- Executes and automates common and complex management tasks
- Package management, configuration management
- Seurity/compliance reporting
- Enables live patching of critical components and Linux kernel w/o downtime
- Configured by default for Oracle Linux instances in OCI

##  OCI Infrastructure protection

### Network protection

Tiered subnet strategy for the VCN
- DMZ subnet for load balancers
- Public subnet for web servers
- Private subnet for internal hosts such as databases

Gateways
- NAT Gateway - for connectivity to internet for pathching
- Service Gateway - for connectivity to public OCI services
- Dynamic Routing Gateway - for connectivity to on-premises

Security Lists, NSG
- SL determines the types of traffic allowed in and out pf the subnet
- NSG the types of traffic allowed in and out of a VNIC

<img src="https://imgur.com/8G6fzEu.png" width="350" height="350">

### OCI Web Application Firewall

classic WAF:
- WAF refers to a device, server-side plugin, or filter that applies a set of rules to HTTP/S traffic
- By intercepting HTTP/S traffic and passing them through a set of filterand rules, WAF is ables to uncover and protect against attack streams hitting a web application
它拦截流量，并通过一组过滤器和规则来传递流量，从而对攻击Web应用程序的攻击流进行覆盖和保护
-  Rules cover common attacks (XSS, SQL Injection) and ability to filter specific source IPs or bad bots.
- Typical reponses from WAF will either be allowing the request to pass through, audit logging the request, or blocking the request by responding with an error page.

OCI WAF is a cloud-based, PCI-compliant, global security service that protects applications from malicious and unwanted internet traffic

Use cases:

- Protect any internet-facing endpoint from cyberattacks and malicious actors
- Portect against XSS and SQL injection
- Bot management - dynamically blocking bad bots
- Protection against layer 7 DDos attacks















<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE1OTgzMzc1Ml19
-->
