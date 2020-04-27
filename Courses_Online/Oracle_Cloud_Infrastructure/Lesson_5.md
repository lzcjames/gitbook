
# OCI Networking Services


> Virtual Cloud Network, Gateways, Peering, VCN Security, Load Balancer

## Virtual Cloud Network (VCN)

- A private network in Software layer which lives in an OCI Region.
- Enables OCI resources to securely communicate with **Internet**, other **instances** or **on-premises(内部, 本地) data center**.
- Highly Available, Scalable and Secure.

### How to establish a VCN

- Private address pool assigned to a VCN
- Subnets in private address pool

<img src="https://imgur.com/pZME7IM.png" width="320" height="320">

## Gateways

### Internet Gateway 

It provides a path for network traffic between your **VCN** and the **internet**.

### Nat Gateway

It gives cloud resources without public IP addresses access to the internet without exposing those resources to incoming internet connections.
它提供的云资源无需公共IP地址即可访问Internet，而不会将这些资源暴露于传入的Internet连接中。

### Dynamic Routing Gateway (DRG)

when connecting your existing on-premises network to your virtual cloud network (VCN).

<img src="https://imgur.com/6B9z5Nl.png" width="320" height="310">

There are 2 mechanisms of DRG:
- VPN Connect (IPSec VPN)

  An **encrypted connection over the internet** between between your on-premises network (a data center or corporate LAN) and your Oracle virtual cloud network (VCN)

- FastConnect

  An **dedicated, private connection** between your data center and Oracle Cloud Infrastructure, **bypasses the internet** (绕过internet)

### Service Gateway

which lets resources in VCN  access public services such as **Object  Storage**, but **without** using  an internet or NAT gateway. So your traffic is not going over the internet

<img src="https://imgur.com/PBSsDP7.png" width="300" height="300">

## VCN Security

- Firewall rules to protect subnets
- Network Security Group consists of set of rules applied only for VNICs

## Peering
**communicate to other VCNs**, it has 2 types of peering:

- Local VCN peering

  Connect 2 VCNs in the **same region** so that their resources can communicate using private IP addresses.
  
  <img src="https://imgur.com/t4tCxes.png" width="220" height="300">

- Remote VCN peering

  Connect 2 VCNS in **different regions** so that their resources can communicate using private IP addresses.
  
  <img src="https://imgur.com/FToNNM8.png" width="440" height="300">

## Load Balancer
It provides automated traffic distribution from one entry point to multiple servers reachable from your virtual cloud network (VCN)
A load balancer improves **resource utilization**, facilitates **scaling**, **fault tolerance** and helps ensure **high availability**. 
You can configure multiple load balancing policies and application-specific **health checks** to ensure that the load balancer directs traffic only to healthy instances.

It has 2 types of LB:

- Public Load Balancer

  To accept traffic from the internet, you create a public load balancer.
<img src="https://imgur.com/hIQJLW5.png" width="430" height="350">

- Private Load Balancer
 
   To isolate your load balancer from the internet and simplify your security posture 处境












<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzk0OTAxOTEsLTQ4NDc0NDQyMSwzNj
kyMTQ0MCwtNTcxNjcyNTk3LC03NDI4ODk4NTMsNDA4MjYwMzAz
LDE2MjQ3MDcwMTQsMTQyMjg5NzA1MiwtNzA1NjYyMTgwLC04MD
c4NTEwOTUsLTkzMjM4MjQ1NSwxNTI1MzIzNjUzLDExMjQ4Mjgy
NjAsNDMwNDg1NjkxXX0=
-->
