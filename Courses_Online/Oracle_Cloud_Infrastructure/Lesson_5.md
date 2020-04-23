
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
It provides private traffic for the communication to on-premises.
There are 2 mechanisms of DRG:
- IPSec VPN
- FastConnect

#### IPSec VPN



#### 






<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUyNTMyMzY1MywxMTI0ODI4MjYwLDQzMD
Q4NTY5MV19
-->