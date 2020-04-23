
# OCI IAM

> IAM, Authentication, Authorization, Policies

## Identity and Access Management (IAM)
It lets you control who has access to your cloud resources.

IAM has 2 principals<sup>**1**</sup> :
- IAM Users
- Instance Principals

### IAM Users and Groups
- Users = ndividual people or applications

- First IAM User = default administrator

- Users enforce security principle of least privilege:
	- Users -> Groups
	- Group -> at least one policy with permission to tenancy or a compartment

### Instance Principals
- Instance Principals lets instances and applications to make API calls against other OCI services removing the need to configure user credentials or a configuration file.
允许实例和应用程序在实例上运行，以便于对其他OCI服务进行API调用，从而除去用户凭证或配置文件的需要。

<img src="https://imgur.com/OUrwEVH.png" width="720" height="310">

## Authentication

Authentication Service authenticates by:
- User name, Password
 
- API Signing key (e.g. github API public key)

  Required wiehn using the OCI API in conjunction with the SDK/CLI
  
- Auth Tokens

  Oracle-generated toekn strings to authenticate with 3rd party APIs that do no support OCI signature-based authentication

## Authorization
Authorization specifies various actions an authenticated Principal can perform.

**OCI Authorization = Policies** 

Policies attachment, can be attached to a compartment or can be attached to an account.

### Policies Syntax

<img src="https://imgur.com/qN8d7kB.png" width="560" height="250">

### Common Policies

<img src="https://imgur.com/uogHaSe.png" width="630" height="310">




---
<sup>**1**</sup> **principal**: is an IAM entity that is allowed to interact with OCI resources

<!--stackedit_data:
eyJoaXN0b3J5IjpbODk3NDA0MTc3LDEzNDI0MDIzMjZdfQ==
-->