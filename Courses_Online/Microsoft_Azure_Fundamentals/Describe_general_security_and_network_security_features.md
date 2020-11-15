> Describe general security and network security features (10-15%)

# Azure security features

## What's Azure Security Center?

[Azure Security Center](https://docs.microsoft.com/en-us/learn/modules/protect-against-security-threats-azure/2-protect-threats-security-center) is a monitoring service that provides visibility of your security posture across all of your services, both on Azure and on-premises. 

## What's Azure Key Vault ?

[Azure Key Vault](https://docs.microsoft.com/en-us/learn/modules/protect-against-security-threats-azure/4-manage-secrets-key-vault) is a centralized cloud service for storing an application's secrets in a single, central location. It provides secure access to sensitive information by providing access control and logging capabilities.

Azure Key Vault can help you:

-   **Manage secrets**
    
    You can use Key Vault to securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets.
    
-   **Manage encryption keys**
    
    You can use Key Vault as a key management solution. Key Vault makes it easier to create and control the encryption keys that are used to encrypt your data.
    
-   **Manage SSL/TLS certificates**
    
    Key Vault enables you to provision, manage, and deploy your public and private Secure Sockets Layer / Transport Layer Security (SSL/TLS) certificates for both your Azure resources and your internal resources.
    
-   **Store secrets backed by hardware security modules (HSMs)**
    
    These secrets and keys can be protected either by software or by FIPS 140-2 Level 2 validated HSMs.

##  What's Azure Sentinel ?

[Azure Sentinel](https://docs.microsoft.com/en-us/learn/modules/protect-against-security-threats-azure/3-detect-respond-threats-sentinel) is Microsoft's cloud-based SIEM system. It uses intelligent security analytics and threat analysis.

Azure Sentinel enables you to:

-   **Collect cloud data at scale**
    
    Collect data across all users, devices, applications, and infrastructure, both on-premises and from multiple clouds.
    
-   **Detect previously undetected threats**
    
    Minimize false positives by using Microsoft's comprehensive analytics and threat intelligence.
    
-   **Investigate threats with artificial intelligence**
    
    Examine suspicious activities at scale, tapping into years of cybersecurity experience from Microsoft.
    
-   **Respond to incidents rapidly**
    
    Utilize built-in orchestration and automation of common tasks.
    
## What's Azure Dedicated Hosts?

[Azure Dedicated Host](https://azure.microsoft.com/services/virtual-machines/dedicated-host/) provides dedicated physical servers to host your Azure VMs for Windows and Linux.

You're charged per dedicated host, independent of how many virtual machines you deploy to it. The host price is based on the VM family, type (hardware size), and region.

# Describe Azure network security

## Defense in depth

The objective of defense in depth is to protect information and prevent it from being stolen by those who aren't authorized to access it.

### [Layers of defense in depth](https://docs.microsoft.com/en-us/learn/modules/secure-network-connectivity-azure/2-what-is-defense-in-depth)

Each layer provides protection so that if one layer is breached, a subsequent layer is already in place to prevent further exposure

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/secure-network-connectivity-azure/media/2-defense-depth.png" width="250" height="300">

Here's a brief overview of the role of each layer:

-   The  _physical security_  layer is the first line of defense to protect computing hardware in the datacenter.
-   The  _identity and access_  layer controls access to infrastructure and change control.
-   The  _perimeter_  layer uses distributed denial of service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for users.
-   The  _network_  layer limits communication between resources through segmentation and access controls.
-   The  _compute_  layer secures access to virtual machines.
-   The  _application_  layer helps ensure that applications are secure and free of security vulnerabilities.
-   The  _data_  layer controls access to business and customer data that you need to protect.

## Network Security Groups (NSG)

NSGs operate at layers 3 & 4, it allows you to filter network traffic to/from Azure resources in an Azure virtual network. 
An NSG can contain multiple inbound and outbound security rules that enable you to filter traffic to and from resources by source and destination IP address, port, and protocol.

## Azure Firewall

[Azure Firewall](https://azure.microsoft.com/services/azure-firewall) is a managed, cloud-based network security service that helps protect resources in your Azure virtual networks.
Azure Firewall is a stateful firewall. A stateful firewall analyzes the complete context of a network connection, not just an individual packet of network traffic.

With Azure Firewall, you can configure:

-   Application rules that define fully qualified domain names (FQDNs) that can be accessed from a subnet.
-   Network rules that define source address, protocol, destination port, and destination address.
-   Network Address Translation (NAT) rules that define destination IP addresses and ports to translate inbound requests.

## Azure DDoS protection

[Azure DDoS Protection](https://azure.microsoft.com/services/ddos-protection/) (Standard) helps protect your Azure resources from DDoS attacks.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/secure-network-connectivity-azure/media/4-distributed-denial-service.png">

### What kinds of attacks can DDoS Protection help prevent?

The Standard service tier can help prevent:

-   **Volumetric attacks**
    
    The goal of this attack is to flood the network layer with a substantial amount of seemingly legitimate traffic.
    
-   **Protocol attacks**
    
    These attacks render a target inaccessible by exploiting a weakness in the layer 3 and layer 4 protocol stack.
    
-   **Resource-layer (application-layer) attacks (only with web application firewall)**
    
    These attacks target web application packets to disrupt the transmission of data between hosts. You need a web application firewall (WAF) to protect against L7 attacks. DDoS Protection Standard protects the WAF from volumetric and protocol attacks.

