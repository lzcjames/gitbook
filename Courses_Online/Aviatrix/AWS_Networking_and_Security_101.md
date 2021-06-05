## [AWS Services ](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#aws-services)

### [EC2](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#ec2)

Is the virtual machine, or as AWS calls them, instances.

这是一个虚拟机，或者按 AWS 的说法，称它为实例。

### [IAM](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#iam)

This is Identity and Access Management, and it allows users to get access to the instances or applications.

这是一个身份与访问的管理，它允许用户访问实例或应用程序。

### [VPC](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#vpc)

This is a Virtual Private Cloud, which is essentially a data center in the cloud.

这是一个虚拟私有云，本质上是云中的一个数据中心。

### [S3](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#s3)

It allows users to access storage using a Public IP Address.

它允许用户使用公共 IP 地址来访问存储空间。

### [Direct Connect](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#direct-connect)

It helps users connect their on-premise Data Center to AWS.

它帮助用户将其内部数据中心连接到 AWS。

### [Route 53](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#route-53)

It’s the DNS System that allows users to build applications and different services using a domain name resolution.

这是DNS系统，允许用户使用域名解析建立应用程序和不同的服务。

### [Global Accelerator ](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#global-accelerator)

Allows users to connect their remote branches to the closest point in the AWS System.

允许用户将其远程分支连接到 AWS 系统中最近的点。

### [CloudFront](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#cloudfront)

This caches frequently used data. This is the CDN service.

这将缓存经常使用的数据。这就是CDN服务。

![](https://s3-us-west-2.amazonaws.com/media.forumbee.com/i/b1c2ebd7-1425-4506-876f-32d474e7759a/h/547.png)

## [The AWS Cloud Computing  Structure and Components AWS](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#the-aws-cloud-computing-structure-and-components)

1.  In a region

    1.1 The first thing to do is to create a VPC using a specified CIDR. VPC’s are regional concepts in AWS. 
  
2.  Specify an AZ within the VPC. 

3.  Specify a subnet in the AZ.

    3.1  This will be part of the CIDR that was already created. 这将是已经创建的CIDR的一部分。
 
    3.2 There is now an AZ to subnet affinity. 现在有一个AZ的子网亲和性

4.  Define or deploy the instances within the subnet. 在子网中定义或部署实例

5.  Once the instances are defined, users must now define a level of security. 一旦实例被定义，用户现在必须定义一个安全级别

    5.1  Create a security group and apply it to multiple instances, or have one security group per instance. 
    
    创建一个安全组并将其应用于多个实例，或者每个实例有一个安全组

6.  Network ACL  

    6.1  This is a stateless Access Control List that is applied at a subnet level. 
    这是在子网级应用的无状态访问控制列表

7.  Route-table and router  

    7.1  Users have basic access to the route-table, but do not have access to the actual router. 
    用户可以基本访问路由表，但不能访问实际的路由器

![](https://s3-us-west-2.amazonaws.com/media.forumbee.com/i/228f1fc9-ae1f-4e88-9b91-c76f0d759a9d/h/547.png)

## [Some AWS Gateways](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#some-aws-gateways)

### [Internet Gateway (IGW)](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#internet-gateway-igw)

A service that provides internet connection to the Virtual Machine.

提供到虚拟机的 internet 连接的服务。

### [Virtual Private Gateway (VGW)](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#virtual-private-gateway-vgw)

A service that allows users to build IPSec tunnels.

允许用户建立 IPSec 隧道的服务。

### [NAT Gateway](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#nat-gateway)

This gateway allows private subnets to connect to the Internet.

这个网关允许私有子网连接到互联网。

### [Transit Gateway (TGW) ](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#transit-gateway-tgw)

This provides hub and spoke connectivity for the VPCs in the  system.

这为系统中的VPC提供枢纽和轴辐式连接。

### [VPN Gateway](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#vpn-gateway)

This connects the on prem network to the VPC or creates a hub and spoke technology between third party VPN devices and the AWS VPN Gateway.

这连接了企业内部网络和VPC，或者在第三方VPN设备和AWS VPN网关之间创建了一个枢纽和轴辐式技术。
![spoke connectivity](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/_images/azure-best-practices/network-hub-spokes-cluster.png)
### [Customer Gateway (CGW)](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#customer-gateway-cgw)

This is allows users to create a shell or definition for the gateway sitting on the on-prem site and then apply the configuration on the actual router.

这允许用户为位于 on-prem 站点上的网关创建 shell 或定义，然后在实际的路由器上应用配置。

### [Direct Connect Gateway (DXGW)](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#direct-connect-gateway-dxgw)

This is a service that allows multiple regions to connect to a physical Direct Connect circuit.

这是一种允许多个区域连接到物理直连电路的服务。

## [The Architecture of the AWS Gateways](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#the-architecture-of-the-aws-gateways)

1.  The region holds the VPC’s. 该地区拥有 VPC
2.  These VPC’s connect to their own TGW’s. 这些 VPC 连接到他们自己的 TGW
3.  The CGW connects to the DXGW. CGW 连接到 DXGW
4.  The DXGW connects to the TGW’s. DXGW 连接到 TGW

## [AWS Transit Gateway (AWS TGW)](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#aws-transitgateway-aws-tgw)

-   This allows many VPCs to talk to each other without VPC Peering.  
这使得许多 VPC 可以在没有 vpcpeering 的情况下彼此通信
    -   The difference between using VPC Peering or using the TGW is that the VPC peering doesn’t allow transitive routing while the TGW does. 
    使用 vpcpeering 和使用 TGW 的区别在于 VPC Peering 不允许传递路由，而 TGW 允许传递路由
-   This native service supports multiple  route tables and also has a VPN attachment type. 
这种本地服务支持多个路由表，也有一个VPN附件类型。
-   However, this has its own **limitations**. 
    -   The enterprises are responsible for programming the VPC routes manually when using the AWS platform without Aviatrix. 
    企业在使用 AWS 平台时，无需使用 Aviatrix，负责手工编程 VPC 路由
    -   The IPSec Tunnel throughput is only about 1.25Gbps. IPSec 
    隧道吞吐量只有约1.25 Gbps
    -   The scalability is a problem. 
    可伸缩性是一个问题
    -   There is no overlapping IP support. 
    没有重叠的 IP 支持

## [How Aviatrix Solves for the Limitations of the AWS Transit Gateway](https://community.aviatrix.com/t/h7hxphg/aws-networking-and-security-101#how-aviatrix-solves-for-the-limitations-of-the-aws-transit-gateway)

-   Aviatrix manages and controls the AWS TGW which removes AWS TGWthe routing limitations. 
   Aviatrix管理和控制AWS TGW，消除了AWS TGW的路由限制。
-   Aviatrix takes care of the initial configuration of the routes and any updates.
   Aviatrix负责路由的初始配置和任何更新。
-   It helps to simplify the BGP over Direct Connect. 
    它有助于简化BGP over Direct Connect。
-   Aviatrix provides network correctness and propagates all the on-prem routes to the VPCs. 
 Aviatrix提供网络正确性，并将所有的内部路由传播到VPC上
