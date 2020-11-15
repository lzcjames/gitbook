> Describe identity, governance, privacy, and compliance features (20-25%)

# Core Azure identity services

## Authentication vs Authorization

Authentication establishes the user's identity, but authorization is the process of establishing what level of access an authenticated person or service has. 

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/secure-access-azure-identity-services/media/2-id-card-access.png" width="600" height="200">

##  Azure Active Directory

Azure Active Directory (Azure AD) provides identity services that enable your users to sign in and access both Microsoft cloud applications and cloud applications that you develop. 

Azure AD provides services such as:

-   **Authentication**
    
    This includes verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, multifactor authentication, a custom list of banned passwords, and smart lockout services.
    
-   **Single sign-on**
    
    SSO enables you to remember only one username and one password to access multiple applications. A single identity is tied to a user, which simplifies the security model. As users change roles or leave an organization, access modifications are tied to that identity, which greatly reduces the effort needed to change or disable accounts.
    
-   **Application management**
    
    You can manage your cloud and on-premises apps by using Azure AD. Features like Application Proxy, SaaS apps, the My Apps portal (also called the  _access panel_), and single-sign on provide a better user experience.
    
-   **Device management**
    
    Along with accounts for individual people, Azure AD supports the registration of devices. Registration enables devices to be managed through tools like Microsoft Intune. It also allows for device-based conditional access policies to restrict access attempts to only those coming from known devices, regardless of the requesting user account.
    
##  Conditional Access, Multi-Factor Authentication(MFA), and Single Sign-On (SSO)

### [Multifactor authentication](https://docs.microsoft.com/en-us/learn/modules/secure-access-azure-identity-services/4-what-are-mfa-conditional-access)
A process where a user is prompted during the sign-in process for an additional form of identification. Examples include a code on their mobile phone or a fingerprint scan.

### [Conditional Access](https://docs.microsoft.com/en-us/learn/modules/secure-access-azure-identity-services/4-what-are-mfa-conditional-access)
A tool that Azure Active Directory uses to allow (or deny) access to resources based on identity signals. These signals include who the user is, where the user is, and what device the user is requesting access from.

### [Single Sign-On](https://docs.microsoft.com/en-us/learn/modules/secure-access-azure-identity-services/3-what-is-azure-active-directory)

Single sign-on enables a user to sign in one time and use that credential to access multiple resources and applications from different providers.

# Azure governance features

The [Cloud Adoption Framework for Azure](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/) provides you with proven guidance to help with your cloud adoption journey.

The Cloud Adoption Framework includes these stages:

1.  Define your strategy.
2.  Make a plan.
3.  Ready your organization.
4.  Adopt the cloud.
5.  Govern and manage your cloud environments.
## Cloud Adoption Framework

## Role-Based Access Control (RBAC)

Role-based access control is applied to a  _scope_, which is a resource or set of resources that this access applies to.

Here's a diagram that shows the relationship between roles and scopes.

<img src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/build-cloud-governance-strategy-azure/media/4-role-scope.png" width="488" height="267">

### When should I use Azure RBAC?

Use Azure RBAC when you need to:

-   Allow one user to manage VMs in a subscription and another user to manage virtual networks.
-   Allow a database administrator group to manage SQL databases in a subscription.
-   Allow a user to manage all resources in a resource group, such as virtual machines, websites, and subnets.
-   Allow an application to access all resources in a resource group.

## Resource Locks


A  [resource lock](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources) prevents resources from being accidentally deleted or changed.

### What levels of locking are available?

You can apply locks to a subscription, a resource group, or an individual resource. You can set the lock level to  **CanNotDelete**  or  **ReadOnly**.

-   **CanNotDelete**  means authorized people can still read and modify a resource, but they can't delete the resource without first removing the lock.
-   **ReadOnly**  means authorized people can read a resource, but they can't delete or change the resource. Applying this lock is like restricting all authorized users to the permissions granted by the  **Reader**  role in Azure RBAC.

### How do I delete or change a locked resource?

- Remove the lock
- Do you want to do 

## [Tags](https://docs.microsoft.com/en-us/learn/modules/build-cloud-governance-strategy-azure/7-organize-resource-tags)
A way to mark its test environments so that it can easily identify and delete resources in these environments when they're no longer needed.
 
## [Azure Policy](https://docs.microsoft.com/en-us/learn/modules/build-cloud-governance-strategy-azure/8-control-audit-resources-azure-policy)
A service in Azure that enables you to create, assign, and manage policies that control or audit your resources

## [Azure Blueprints](https://docs.microsoft.com/en-us/learn/modules/build-cloud-governance-strategy-azure/10-govern-subscriptions-azure-blueprints)

Enables you to define a repeatable set of governance tools and standard Azure resources that your organization requires.

# Privacy and compliance resources

## Microsoft core tenets of Security, Privacy, and Compliance 

Think of a control as a known good standard that you can compare your solution against to ensure security. These controls address today's regulations and adapt as regulations evolve.

## [Microsoft Privacy Statement, Online Services Terms (OST) and Data Protection Amendment (DPA)](https://docs.microsoft.com/en-us/learn/modules/examine-privacy-compliance-data-protection-standards/3-access-microsoft-privacy-statement) 

### Microsoft Privacy Statement

The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement) explains what personal data Microsoft collects, how Microsoft uses it, and for what purposes.

### Online Services Terms (OST)

The [Online Services Terms](https://www.microsoft.com/licensing/terms/product/ForallOnlineServices) (OST) is a legal agreement between Microsoft and the customer.

### Data Protection Amendment (DPA) 

The Data Protection Addendum (DPA) further defines the data processing and security terms for online services. These terms include:

-   Compliance with laws.
-   Disclosure of processed data.
-   Data Security, which includes security practices and policies, data encryption, data access, customer responsibilities, and compliance with auditing.
-   Data transfer, retention, and deletion.

## Trust Center 

Trust Center includes detailed information about legal and regulatory standards and compliance on Azure.

The Trust Center provides:

-   In-depth information about security, privacy, compliance offerings, policies, features, and practices across Microsoft cloud products.
-   Additional resources for each topic.
-   Links to the security, privacy, and compliance blogs and upcoming events.

## Azure compliance documentation 

The [Azure compliance documentation](https://docs.microsoft.com/en-us/azure/compliance/) provides you with detailed documentation about legal and regulatory standards and compliance on Azure.

## Azure Sovereign Regions (Azure Government cloud services and Azure China cloud services)

[Azure Government](https://azure.microsoft.com/global-infrastructure/government) is a separate instance of the Microsoft Azure service. It addresses the security and compliance needs of US federal agencies, state and local governments, and their solution providers. Azure Government offers physical isolation from non-US government deployments and provides screened US personnel.

[Azure China 21Vianet](https://docs.microsoft.com/en-us/azure/china) is operated by 21Vianet. It's a physically separated instance of cloud services located in China.
