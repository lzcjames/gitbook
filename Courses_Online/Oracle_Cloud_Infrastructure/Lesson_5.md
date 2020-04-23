
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
It enables outbound connections to the internet, but blocks inbound connections initiated from the internet. 允许出站连接但禁止从Internet到VCN的入站连接

### Dynamic Routing Gateway (DRG)

when connecting your existing on-premises network to your virtual cloud network (VCN).

<img src="https://imgur.com/6B9z5Nl.png" width="320" height="310">

There are 2 mechanisms of DRG:
- VPN Connect (IPSec VPN)
encrypt the traffic between your on-premises network (a data center or corporate LAN) and your Oracle virtual cloud network (VCN)
- FastConnect
private connection between your data center and Oracle Cloud Infrastructure.

### Service Gateway

which  lets  resources  in  VCN  access  public  services  such  as  **Object  Storage**,  but  **without** using  an  internet  or  NAT  gateway.  So  your  traffic  is  not  going  over  the  internet

<img src="https://imgur.com/PBSsDP7.png" width="320" height="300">

## VCN Security

- Firewall rules to protect subnets
- Network Security Group consists of set of rules applied only for VNICs







<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NzI4NzcwNzcsMTYyNDcwNzAxNCwxND
IyODk3MDUyLC03MDU2NjIxODAsLTgwNzg1MTA5NSwtOTMyMzgy
NDU1LDE1MjUzMjM2NTMsMTEyNDgyODI2MCw0MzA0ODU2OTFdfQ
==
-->