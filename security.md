### Cloud Security

Typically within the particular organization, people with different roles uses cloud services for different puposes. There could be following roles in the organization. 

1. Administators
2. Developers
3. Testers
4. Client

> Security is shared responibility of customer and cloud provider.

As security is shared resonsibility so customer is responsible of access managements of resources. Customers need to stretgies how to delegate cloud resources or services
to thier people. Delegate limites access and grant only access that is needed and make sure all changes are logged.

### Security levels

1. Network level security
2. OS level security
3. Resource groups level security
4. Service level security

Microsft intoduced a layered approach to security. If one layer is broken other subsequent layer is already in place to protect your data.

![Image of security layers](https://docs.microsoft.com/en-us/learn/modules/intro-to-security-in-azure/media/defense_in_depth_layers_small.png)

Let's take a look at each of the layers.
- Data
- Application
- Compute
- Networking
- Perimeter
- Identitiy and Access

### Security Challanges
- DDos Attacks
- Data breaches
- Access management
- Misconfiguration
- Credentials and key management
- Account Hijacking
- Insider threat
- Insecure APIs

There are different services that azure provide for better security.
1. Azure security
2. RBAC
3. Azure AD

#### Azure AD
> Azure Active Directory (Azure AD) is Microsoft’s cloud-based identity and access management service, which helps your employees sign in and access resources.
There are following types of indentities available in Azure AD.
- User Identity + Roles => User Principal
- Service Identity + Roles => Service Principal
- Managed Identity

### RBAC
> Role-based access control (RBAC) is an authorization system built on Azure Resource Manager that provides fine-grained access management of resources in Azure.

You control access to resources using RBAC by creating role assignments, which control how permissions are enforced. To create a role assignment, you need three elements: a security principal, a role definition, and a scope. You can think of these elements as "who", "what", and "where".

1. Security principal (who)
2. Role definition (what you can do)
3. Scope (where)

Azure provides four level of resource management. 
1. Management Group
2. Subscription
3. Resource Groups
4. Resources

All resources within parent scope automatically inherit the conditions applied to the parent group. 

![Role Assignment](https://docs.microsoft.com/en-us/learn/modules/secure-azure-resources-with-rbac/media/2-rbac-overview.png)
