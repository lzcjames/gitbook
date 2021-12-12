# Introduction to API Manegement

## What is an API, API gateway?

### API
An application programming interface, or API, enables companies to open up their applications’ data and functionality to external third-party developers, business partners, and internal departments within their companies.


### API Geteway
API gateway is a **private endpoint** in a **regional subnet** which can be exposed over a public IP address as a public API gateway 

An API gateway routes inbound traffic to back-end services including public, private, and partner HTTP APIs  (API 网关将入站流量路由到后端服务，包括公共、私有和合作伙伴 HTTP API)

Private API gateways can only be accessed by resources in the same subnet. Public API gateways are publicly accessible, including from the internet.  

To ensure **high availability**, you can **only** create API gateways in regional subnets (not AD-specific subnets).  






