
# OCI Networking Services


> Virtual Cloud Network, Gateways, Peering, VCN Security, Load Balancer

## Virtual Cloud Network (VCN)

- A private network in Software layer which lives in an OCI Region.
- Enables OCI resources to securely communicate with **Internet**, other **instances** or **on-premises(内部, 本地) data center**.
- Highly Available, Scalable and Secure.

### How to establish a VCN

- Private address pool assigned to a VCN
- Subnets in private address pool

## Gateways

### Internet Gateway 

It provides a path for network traffic between your **VCN** and the **internet**.

### Nat Gateway
It enables outbound connections to the internet, but blocks inbound connections initiated from the internet. 允许出站连接但禁止从Internet到VCN的入站连接

### Dynamic Routing Gateway (DRG)
It provides private IPv4 traffic for the communication mixed to on-premises and through the internet
There are 2 mechanisms of DRG:
- VPN Connect (IPSec VPN)
encrypt the traffic goes through the internet.
- FastConnect


#### VPN Connect (IPSec VPN)

encrypt the traffic goes through the internet.

#### 






<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwNzg1MTA5NSwtOTMyMzgyNDU1LDE1Mj
UzMjM2NTMsMTEyNDgyODI2MCw0MzA0ODU2OTFdfQ==
-->