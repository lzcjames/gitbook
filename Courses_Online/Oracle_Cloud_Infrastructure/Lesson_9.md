# OCI Pricing and Billing

>  Pricing Models, Pricing Example, Billing, Cost Management, Free Tier


## Pricing Models

### Pay as you go (PAYG)

- Chared only for the resource consumed 仅对消耗的资源收费

- No upfront commitment 没有前期承诺

- No minimum service period 无最低服务期限

- Usage metered hourly 按小时计费
  
- Consumption based model for services like Oracle Functions 基于Oracle Functions等服务的消耗

### Monthly Flex (Universal Credits)

- A minimum of **$1000 monthly charge** and a minimum **12 months** fixed commitment

- Observed 33%-60% saving vs PAYG

- Discounts based on size of deal and term of deal

- Usage is consumed from monthly **prepaid** commitment

###  Bring Your Own License (BYOL)

- Apply your current on-premises Oracle licenses to equivalent, highly automated Oracle **IaaS & PaaS services** in the cloud

- Complete license mobility with on-premises


## Factor that impact Pricing

- Resource Size
- Resource Type
	- VMs or BMs
	- VMS or Functions
	- BYOL or managed DBs
	- CPU
	- GPU
	- HPC
- Data Transfer
	- **No Ingress cost**
	- Careful with Egress cost
- All OCI Regions have the **same pricing**

## Pricing Example

### Block Volume Pricing
- Storage cost
- Performance cost (VPU/GB)

### Data Transfer costs
- In the same AD: FREE
- bbetween ADs: FREE
- Between Regions:
	- Engress: **CHARGE**
	- Ingress: FREE
- Rrgion and Internet:
	- To Internet: **CHARGE**
	- From Internet: FREE
- Dynamic Routing Gateway: FREE
- FastConnect: FREE

## Billing, Cost Management

### Cost Tracking Tags

When you tag your resources, you could tag them with these cost tracking tags.

### Cost Analysis
- Visualization tool Help understand spending patterns at a glance
     可视化工具有助于一目了然地了解支出模式
- Filter costs by Date, Tags and Compartments
- To use Cost Analysis you must be a member of the **Administrators group**

## Budgets

- A monthly threshold you define for your OCI spend
- Can be set on cost-tracking tags or compartments
- Alerts are evaluated every 15 minutes
- Can set email alterts

## Usage Reports

- Detailed information about your OCI consumption
- Contained 24 hours of usage data
- Retained for one year
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5NTg0MzA5NV19
-->