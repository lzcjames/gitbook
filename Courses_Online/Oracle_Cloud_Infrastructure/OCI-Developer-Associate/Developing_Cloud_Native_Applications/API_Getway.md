# Introduction to API Manegement

## What is an API, API gateway?

### API
An application programming interface, or API, enables companies to open up their applications’ data and functionality to external third-party developers, business partners, and internal departments within their companies.


### API Geteway
The API Gateway service is **regional in scope** and **fault-tolerant** across availability domains (in multiple-AD regions), and fault domains (in single AD regions).

API gateway is a **private endpoint** in a **regional subnet** which can be exposed over a public IP address as a public API gateway 

It applies serverless policy to enforce protection such as **authorization**. It also performs **validation**, **transformation**, **response caching** and **routing**,  add metrics, alarms, and logging for that endpoint (它使用无服务器策略以强制执行保护措施，例如**授权**。它还执行**验证**、**转换**、**响应缓存**和**路由**，为该端点添加指标、警报和日志记录)

Private API gateways can only be accessed by resources in the same subnet. Public API gateways are publicly accessible, including from the internet.  

To ensure **high availability**, you can **only** create API gateways in regional subnets (not AD-specific subnets).  (为确保**高可用性**，您可以**仅**在区域子网（而不是特定于 AD 的子网）中创建 API 网关)

# Networking and Security Policies

<img src="https://imgur.com/6IYy6RR.png" alt="alt text" width="360" heigh="400" />  

## Networking
- A API gateway must be created in a reional subnet, then API Gateway Service provides to API Gateiway an active and failover instance (活动和故障转移的实例, 故障转移是指当活动设备无法运作时，另一台设备立刻自动接手该设备所执行的工作)









