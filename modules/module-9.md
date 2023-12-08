# 💡 Module 9

## Implementing Azure Active Directory

Now Azure Active Directory is known as Microsoft Entra ID

## What is Microsoft Entra ID?

Microsoft Entra ID is a cloud-based identity and access management service that enables your employees access external resources. Example resources include Microsoft 365, the Azure portal, and thousands of other SaaS applications.

## What are the Microsoft Entra ID licenses? <a href="#what-are-the-microsoft-entra-id-licenses" id="what-are-the-microsoft-entra-id-licenses"></a>

* **Microsoft Entra ID Free.** Provides user and group management, on-premises directory synchronization, basic reports, self-service password change for cloud users, and single sign-on across Azure, Microsoft 365, and many popular SaaS apps.
* **Microsoft Entra ID P1.** In addition to the Free features, P1 also lets your hybrid users access both on-premises and cloud resources. It also supports advanced administration, such as dynamic groups, self-service group management, Microsoft Identity Manager, and cloud write-back capabilities, which allow self-service password reset for your on-premises users.
* **Microsoft Entra ID P2.** In addition to the Free and P1 features, P2 also offers [Microsoft Entra ID Protection](https://learn.microsoft.com/en-us/entra/id-protection/overview-identity-protection) to help provide risk-based Conditional Access to your apps and critical company data and [Privileged Identity Management](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-getting-started) to help discover, restrict, and monitor administrators and their access to resources and to provide just-in-time access when needed.
* **"Pay as you go" feature licenses.** You can also get licenses for features such as, Microsoft Entra Business-to-Customer (B2C). B2C can help you provide identity and access management solutions for your customer-facing apps. For more information, see [Azure Active Directory B2C documentation](https://learn.microsoft.com/en-us/azure/active-directory-b2c/).

## Which features work in Microsoft Entra ID? <a href="#which-features-work-in-microsoft-entra-id" id="which-features-work-in-microsoft-entra-id"></a>

| Category                               | Description                                                                                                                                                                                                                                                                                                                                                                                                                             |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Application management                 | Manage your cloud and on-premises apps using Application Proxy, single sign-on, the My Apps portal, and Software as a Service (SaaS) apps. For more information, see [How to provide secure remote access to on-premises applications](https://learn.microsoft.com/en-us/entra/identity/app-proxy/application-proxy) and [Application Management documentation](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/).     |
| Authentication                         | Manage Microsoft Entra self-service password reset, Multi-Factor Authentication, custom banned password list, and smart lockout. For more information, see [Microsoft Entra authentication documentation](https://learn.microsoft.com/en-us/entra/identity/authentication/).                                                                                                                                                            |
| Microsoft Entra ID for developers      | Build apps that sign in all Microsoft identities, get tokens to call Microsoft Graph, other Microsoft APIs, or custom APIs. For more information, see [Microsoft identity platform (Microsoft Entra ID for developers)](https://learn.microsoft.com/en-us/entra/identity-platform/).                                                                                                                                                    |
| Business-to-Business (B2B)             | Manage your guest users and external partners, while maintaining control over your own corporate data. For more information, see [Microsoft Entra B2B documentation](https://learn.microsoft.com/en-us/entra/external-id/).                                                                                                                                                                                                             |
| Business-to-Customer (B2C)             | Customize and control how users sign up, sign in, and manage their profiles when using your apps. For more information, see [Azure Active Directory B2C documentation](https://learn.microsoft.com/en-us/azure/active-directory-b2c/).                                                                                                                                                                                                  |
| Conditional Access                     | Manage access to your cloud apps. For more information, see [Microsoft Entra Conditional Access documentation](https://learn.microsoft.com/en-us/entra/identity/conditional-access/).                                                                                                                                                                                                                                                   |
| Device Management                      | Manage how your cloud or on-premises devices access your corporate data. For more information, see [Microsoft Entra Device Management documentation](https://learn.microsoft.com/en-us/entra/identity/devices/).                                                                                                                                                                                                                        |
| Domain services                        | Join Azure virtual machines to a domain without using domain controllers. For more information, see [Microsoft Entra Domain Services documentation](https://learn.microsoft.com/en-us/entra/identity/domain-services/).                                                                                                                                                                                                                 |
| Enterprise users                       | Manage license assignments, access to apps, and set up delegates using groups and administrator roles. For more information, see [Microsoft Entra user management documentation](https://learn.microsoft.com/en-us/entra/identity/users/).                                                                                                                                                                                              |
| Hybrid identity                        | Use Microsoft Entra Connect and Connect Health to provide a single user identity for authentication and authorization to all resources, regardless of location (cloud or on-premises). For more information, see [Hybrid identity documentation](https://learn.microsoft.com/en-us/entra/identity/hybrid/).                                                                                                                             |
| Identity governance                    | Manage your organization's identity through employee, business partner, vendor, service, and app access controls. You can also perform access reviews. For more information, see [Microsoft Entra ID Governance documentation](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview) and [Microsoft Entra access reviews](https://learn.microsoft.com/en-us/entra/id-governance/access-reviews-overview). |
| Identity protection                    | Detect potential vulnerabilities affecting your organization's identities, configure policies to respond to suspicious actions, and then take appropriate action to resolve them. For more information, see [Microsoft Entra ID Protection](https://learn.microsoft.com/en-us/entra/id-protection/).                                                                                                                                    |
| Managed identities for Azure resources | Provide your Azure services with an automatically managed identity in Microsoft Entra ID that can authenticate any Microsoft Entra ID-supported authentication service, including Key Vault. For more information, see [What is managed identities for Azure resources?](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview).                                                                 |
| Privileged identity management (PIM)   | Manage, control, and monitor access within your organization. This feature includes access to resources in Microsoft Entra ID and Azure, and other Microsoft Online Services, like Microsoft 365 or Intune. For more information, see [Microsoft Entra Privileged Identity Management](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/).                                                          |
| Monitoring and health                  | Gain insights into the security and usage patterns in your environment. For more information, see [Microsoft Entra monitoring and health](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/).                                                                                                                                                                                                                         |
| Workload identities                    | Give an identity to your software workload (such as an application, service, script, or container) to authenticate and access other services and resources. For more information, see [workload identities faqs](https://learn.microsoft.com/en-us/entra/workload-id/workload-identities-faqs).                                                                                                                                         |

## Terminology

| Term or concept                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Identity                             | A thing that can get authenticated. An identity can be a user with a username and password. Identities also include applications or other servers that might require authentication through secret keys or certificates.                                                                                                                                                                                                                                                                           |
| Account                              | An identity that has data associated with it. You can’t have an account without an identity.                                                                                                                                                                                                                                                                                                                                                                                                       |
| Microsoft Entra account              | An identity created through Microsoft Entra ID or another Microsoft cloud service, such as Microsoft 365. Identities are stored in Microsoft Entra ID and accessible to your organization's cloud service subscriptions. This account is also sometimes called a Work or school account.                                                                                                                                                                                                           |
| Account Administrator                | This classic subscription administrator role is conceptually the billing owner of a subscription. This role enables you to manage all subscriptions in an account. For more information, see [Azure roles, Microsoft Entra roles, and classic subscription administrator roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles).                                                                                                                 |
| Service Administrator                | This classic subscription administrator role enables you to manage all Azure resources, including access. This role has the equivalent access of a user who is assigned the Owner role at the subscription scope. For more information, see [Azure roles, Microsoft Entra roles, and classic subscription administrator roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles).                                                                  |
| Owner                                | This role helps you manage all Azure resources, including access. This role is built on a newer authorization system called Azure role-based access control (Azure RBAC) that provides fine-grained access management to Azure resources. For more information, see [Azure roles, Microsoft Entra roles, and classic subscription administrator roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles).                                          |
| Microsoft Entra Global Administrator | This administrator role is automatically assigned to whomever created the Microsoft Entra tenant. You can have multiple Global Administrators, but only Global Administrators can assign administrator roles (including assigning other Global Administrators) to users. For more information about the various administrator roles, see [Administrator role permissions in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference). |
| Azure subscription                   | Used to pay for Azure cloud services. You can have many subscriptions and they're linked to a credit card.                                                                                                                                                                                                                                                                                                                                                                                         |
| Azure tenant                         | A dedicated and trusted instance of Microsoft Entra ID. The tenant is automatically created when your organization signs up for a Microsoft cloud service subscription. These subscriptions include Microsoft Azure, Microsoft Intune, or Microsoft 365. An Azure tenant represents a single organization.                                                                                                                                                                                         |
| Single tenant                        | Azure tenants that access other services in a dedicated environment are considered single tenant.                                                                                                                                                                                                                                                                                                                                                                                                  |
| Multi-tenant                         | Azure tenants that access other services in a shared environment, across multiple organizations, are considered multi-tenant.                                                                                                                                                                                                                                                                                                                                                                      |
| Microsoft Entra directory            | Each Azure tenant has a dedicated and trusted Microsoft Entra directory. The Microsoft Entra directory includes the tenant's users, groups, and apps and is used to perform identity and access management functions for tenant resources.                                                                                                                                                                                                                                                         |
| Custom domain                        | Every new Microsoft Entra directory comes with an initial domain name, for example `domainname.onmicrosoft.com`. In addition to that initial name, you can also add your organization's domain names. Your organization's domain names include the names you use to do business and your users use to access your organization's resources, to the list. Adding custom domain names helps you to create user names that are familiar to your users, such as alain@contoso.com.                     |
| Microsoft account (also called, MSA) | Personal accounts that provide access to your consumer-oriented Microsoft products and cloud services. These products and services include Outlook, OneDrive, Xbox LIVE, or Microsoft 365. Your Microsoft account is created and stored in the Microsoft consumer identity account system that's run by Microsoft.                                                                                                                                                                                 |

## Create a new tenant in Microsoft Entra ID

After you sign in to the [Azure portal](https://portal.azure.com/), you can create a new tenant for your organization. Your new tenant represents your organization and helps you to manage a specific instance of Microsoft cloud services for your internal and external users.

## Steps to create a new Tenant <a href="#to-create-a-new-tenant" id="to-create-a-new-tenant"></a>

1. Sign in to the [Azure portal](https://portal.azure.com/).
2. From the Azure portal menu, select **Microsoft Entra ID**.
3. On the overview page, select **Manage tenants**.
4. Select **Create**.&#x20;

<figure><img src="../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

1. On the Basics tab, select the type of tenant you want to create, either **Microsoft Entra ID** or **Microsoft Entra ID (B2C)**.
2. Select **Next: Configuration** to move to the Configuration tab.
3. On the Configuration tab, enter the following information:

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

1.
   * Type your desired Organization name (for example _Contoso Organization_) into the **Organization name** box.
   * Type your desired Initial domain name (for example _Contosoorg_) into the **Initial domain name** box.
   * Select your desired Country/Region or leave the _United States_ option in the **Country or region** box.
2. Select **Next: Review + Create**. Review the information you entered and if the information is correct, select **Create** in the lower left corner.

## Clean up resources <a href="#clean-up-resources" id="clean-up-resources"></a>

If you're not going to continue to use this application, you can delete the tenant using the following steps:

* Ensure that you're signed in to the directory that you want to delete through the **Directory + subscription** filter in the Azure portal. Switch to the target directory if needed.
*   Select **Microsoft Entra ID**, and then on the **Contoso - Overview** page, select **Delete directory**.

    The tenant and its associated information are deleted.

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Add your custom domain name to your tenant <a href="#add-your-custom-domain-name-to-your-tenant" id="add-your-custom-domain-name-to-your-tenant"></a>

Microsoft Entra tenants come with an initial domain name like, `domainname.onmicrosoft.com`. You can't change or delete the initial domain name, but you can add your organization's name to the initial domain. By adding your custom domain name, you can then add user names that are familiar to your users, such as `alain@contoso.com`.

### Before you begin <a href="#before-you-begin" id="before-you-begin"></a>

Before you can add a custom domain name, create your domain name with a domain registrar. For an accredited domain registrar, see [ICANN-Accredited Registrars](https://www.icann.org/registrar-reports/accredited-list.html).

Create your directory

After you get your domain name, you can create your first directory. Sign in to the [Azure portal](https://portal.azure.com/) for your directory, using an account with the [Owner](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#owner) role for the subscription.

Create your new directory by following the steps in [Create a new tenant for your organization](https://learn.microsoft.com/en-us/entra/fundamentals/create-new-tenant#create-a-new-tenant-for-your-organization).

## Add your custom domain name

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Domain Name Administrator](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#domain-name-administrator).
2. Browse to **Identity** > **Settings** > **Domain names** > **Add custom domain**.

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

In **Custom domain name**, enter your organization's domain, in this example, _contoso.com_. Select **Add domain**.

<figure><img src="../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

The unverified domain is added. The **contoso.com** page appears showing the DNS information needed to validate your domain ownership. Save this information.

<figure><img src="../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

Verify your custom domain name

After you register your custom domain name, make sure it's valid in Microsoft Entra. The propagation time can be instantaneous or it can take a few days, depending on your domain registrar.

To verify your custom domain name, follow these steps:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Domain Name Administrator](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#domain-name-administrator).
2. Browse to **Identity** > **Settings** > **Domain names**.
3. In **Custom domain names**, select the custom domain name. In this example, select **contoso.com**.

<figure><img src="../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

On the **contoso.com** page, select **Verify** to make sure your custom domain is properly registered and is valid.

<figure><img src="../.gitbook/assets/image (8) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Associate or add an Azure subscription to your Microsoft Entra tenant <a href="#associate-or-add-an-azure-subscription-to-your-microsoft-entra-tenant" id="associate-or-add-an-azure-subscription-to-your-microsoft-entra-tenant"></a>

All Azure subscriptions have a trust relationship with a Microsoft Entra tenant. Subscriptions rely on this tenant (directory) to authenticate and authorize security principals and devices. When a subscription expires, the trusted instance remains, but the security principals lose access to Azure resources. Subscriptions can only trust a single directory while one Microsoft Entra tenant may be trusted by multiple subscriptions.

When a user signs up for a Microsoft cloud service, a new Microsoft Entra tenant is created and the user is made a Global Administrator. However, when an owner of a subscription joins their subscription to an existing tenant, the owner isn't assigned to the Global Administrator role.

While users may only have a single authentication _home_ directory, users may participate as guests in multiple directories. You can see both the home and guest directories for each user in Microsoft Entra ID.

<figure><img src="../.gitbook/assets/image (9) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Associate a subscription to a directory <a href="#associate-a-subscription-to-a-directory" id="associate-a-subscription-to-a-directory"></a>

To associate an existing subscription with your Microsoft Entra ID, follow these steps:

1. Sign to the [Azure portal](https://portal.azure.com/) with the [Owner](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#owner) role assignment for the subscription.
2. Browse to **Subscriptions**.
3. Select the name of the subscription you want to use.
4.  Select **Change directory**.

    <figure><img src="../.gitbook/assets/image (10) (1) (1).png" alt=""><figcaption></figcaption></figure>

    Review any warnings that appear, and then select **Change**.



    <figure><img src="../.gitbook/assets/image (11) (1) (1).png" alt=""><figcaption></figcaption></figure>

    After the directory is changed for the subscription, you'll get a success message.

    Select Switch directories on the subscription page to go to your new directory.

<figure><img src="../.gitbook/assets/image (12) (1) (1).png" alt=""><figcaption></figcaption></figure>

## What is application management in Microsoft Entra ID? <a href="#what-is-application-management-in-microsoft-entra-id" id="what-is-application-management-in-microsoft-entra-id"></a>

Application management in Microsoft Entra ID is the process of creating, configuring, managing, and monitoring applications in the cloud. When an [application](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals) is registered in a Microsoft Entra tenant, users who have been assigned to it can securely access it. Many types of applications can be registered in Microsoft Entra ID. For more information, see [Application types for the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/v2-app-types).

In this article, you learn these important aspects of managing the lifecycle of an application:

* **Develop, add, or connect** – You take different paths depending on whether you're developing your own application, using a pre-integrated application, or connecting to an on-premises application.
* **Manage access** – Access can be managed by using single sign-on (SSO), assigning resources, defining the way access is granted and consented to, and using automated provisioning.
* **Configure properties** – Configure the requirements for signing into the application and how the application is represented in user portals.
* **Secure the application** – Manage configuration of permissions, multifactor authentication, Conditional Access, tokens, and certificates.
* **Govern and monitor** – Manage interaction and review activity using entitlement management and reporting and monitoring resources.
* **Clean up** – When your application is no longer needed, clean up your tenant by removing access to it and deleting it.

### Develop, add, or connect <a href="#develop-add-or-connect" id="develop-add-or-connect"></a>

There are several ways that you might manage applications in Microsoft Entra ID. The easiest way to start managing an application is to use a pre-integrated application from the Microsoft Entra gallery. Developing your own application and registering it in Microsoft Entra ID is an option, or you can continue to use an on-premises application.

The following image shows how these applications interact with Microsoft Entra ID.

<figure><img src="../.gitbook/assets/image (16) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Pre-integrated applications <a href="#pre-integrated-applications" id="pre-integrated-applications"></a>

Many applications are already pre-integrated (shown as “Cloud applications” in the image above) and can be set up with minimal effort. Each application in the Microsoft Entra gallery has an article available that shows you the steps required to [configure the application](https://learn.microsoft.com/en-us/entra/identity/saas-apps/tutorial-list). For a simple example of how an application can be added to your Microsoft Entra tenant from the gallery, see [Quickstart: Add an enterprise application](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/add-application-portal).

#### Your own applications <a href="#your-own-applications" id="your-own-applications"></a>

If you develop your own business application, you can register it with Microsoft Entra ID to take advantage of the security features that the tenant provides. You can register your application in **App Registrations**, or you can register it using the **Create your own application** link when adding a new application in **Enterprise applications**. Consider how [authentication](https://learn.microsoft.com/en-us/entra/identity-platform/authentication-flows-app-scenarios) is implemented in your application for integration with Microsoft Entra ID.

If you want to make your application available through the gallery, you can [submit a request to have it added](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/v2-howto-app-gallery-listing).

#### On-premises applications <a href="#on-premises-applications" id="on-premises-applications"></a>

If you want to continue using an on-premises application, but take advantage of what Microsoft Entra ID offers, connect it with Microsoft Entra ID using [Microsoft Entra application proxy](https://learn.microsoft.com/en-us/entra/identity/app-proxy/application-proxy). Application Proxy can be implemented when you want to publish on-premises applications externally. Remote users who need access to internal applications can then access them in a secure manner.

## Add an enterprise application

Prerequisites

* A Microsoft Entra user account. If you don't already have one, you can [Create an account for free](https://azure.microsoft.com/free/?WT.mc\_id=A261C142F).
* One of the following roles: Global Administrator, Cloud Application Administrator, or Application Administrator.

To add an enterprise application to your Microsoft Entra tenant, you need:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Cloud Application Administrator](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator).
2. Browse to **Identity** > **Applications** > **Enterprise applications** > **All applications**.
3. Select **New application**.
4. The **Browse Microsoft Entra Gallery** pane opens and displays tiles for cloud platforms, on-premises applications, and featured applications. Applications listed in the **Featured applications** section have icons indicating whether they support federated single sign-on (SSO) and provisioning. Search for and select the application. In this quickstart, \*_Azure AD SAML Toolkit_ is being used.

To add an enterprise application to your tenant:

\


<figure><img src="../.gitbook/assets/image (17) (1) (1).png" alt=""><figcaption></figcaption></figure>

1. Enter a name that you want to use to recognize the instance of the application. For example, `Azure AD SAML Toolkit 1`.
2. Select **Create**.

## What is single sign-on in Microsoft Entra ID? <a href="#what-is-single-sign-on-in-microsoft-entra-id" id="what-is-single-sign-on-in-microsoft-entra-id"></a>

Single sign-on is an authentication method that allows users to sign in using one set of credentials to multiple independent software systems. Using SSO means a user doesn't have to sign in to every application they use. With SSO, users can access all needed applications without being required to authenticate using different credentials.

## Plan a single sign-on deployment <a href="#plan-a-single-sign-on-deployment" id="plan-a-single-sign-on-deployment"></a>

This article provides information that you can use to plan your [single sign-on (SSO)](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/what-is-single-sign-on) deployment in Microsoft Entra ID. When you plan your SSO deployment with your applications in Microsoft Entra ID, you need to consider the following questions:

* What are the administrative roles required for managing the application?
* Does the Security Assertion Markup Language (SAML) application certificate need to be renewed?
* Who needs to be notified of changes related to the implementation of SSO?
* What licenses are needed to ensure effective management of the application?
* Are shared and guest user accounts used to access the application?
* Do I understand the options for SSO deployment?

### Administrative Roles <a href="#administrative-roles" id="administrative-roles"></a>

Always use the role with the fewest permissions available to accomplish the required task within Microsoft Entra ID. Review the different roles that are available and choose the right one to solve your needs for each persona for the application. Some roles may need to be applied temporarily and removed after the deployment has been completed.

| Persona                    | Roles                                                                    | Microsoft Entra role (if necessary) |
| -------------------------- | ------------------------------------------------------------------------ | ----------------------------------- |
| Help desk admin            | Tier 1 support view the sign-in logs to resolve issues.                  | None                                |
| Identity admin             | Configure and debug when issues involve Microsoft Entra ID               | Cloud Application Administrator     |
| Application admin          | User attestation in application, configuration on users with permissions | None                                |
| Infrastructure admins      | Certificate rollover owner                                               | Cloud Application Administrator     |
| Business owner/stakeholder | User attestation in application, configuration on users with permissions | None                                |

### Certificates <a href="#certificates" id="certificates"></a>

When you enable federation on SAML application, Microsoft Entra ID creates a certificate that is by default valid for three years. You can customize the expiration date for that certificate if needed. Ensure that you have processes in place to renew certificates prior to their expiration.

You change that certificate duration in the Microsoft Entra admin center. Make sure to document the expiration and know how you'll manage your certificate renewal. It’s important to identify the right roles and email distribution lists involved with managing the lifecycle of the signing certificate. The following roles are recommended:

* Owner for updating user properties in the application
* Owner On-Call for application troubleshooting support
* Closely monitored email distribution list for certificate-related change notifications

Set up a process for how you'll handle a certificate change between Microsoft Entra ID and your application. By having this process in place, you can help prevent or minimize an outage due to a certificate expiring or a forced certificate rollover.&#x20;

### Licensing <a href="#licensing" id="licensing"></a>

Ensure the application is covered by the following licensing requirements:

* **Microsoft Entra ID licensing** - SSO for pre-integrated enterprise applications is free. However, the number of objects in your directory and the features you wish to deploy may require more licenses. For a full list of license requirements, see [Microsoft Entra pricing](https://www.microsoft.com/security/business/identity-access-management/azure-ad-pricing).
* **Application licensing** - You'll need the appropriate licenses for your applications to meet your business needs. Work with the application owner to determine whether the users assigned to the application have the appropriate licenses for their roles within the application. If Microsoft Entra ID manages the automatic provisioning based on roles, the roles assigned in Microsoft Entra ID must align with the number of licenses owned within the application. Improper number of licenses owned in the application may lead to errors during the provisioning or updating of a user account.

### Single sign-on options <a href="#single-sign-on-options" id="single-sign-on-options"></a>

There are several ways you can configure an application for SSO. Choosing an SSO method depends on how the application is configured for authentication.

* Cloud applications can use OpenID Connect, OAuth, SAML, password-based, or linked for SSO. Single sign-on can also be disabled.
* On-premises applications can use password-based, Integrated Windows Authentication, header-based, or linked for SSO. The on-premises choices work when applications are configured for [Application Proxy](https://learn.microsoft.com/en-us/entra/identity/app-proxy/what-is-application-proxy).

This flowchart can help you decide which SSO method is best for your situation.

<figure><img src="../.gitbook/assets/image (18) (1) (1).png" alt=""><figcaption></figcaption></figure>

The following SSO protocols are available to use:

* **OpenID Connect and OAuth** - Choose OpenID Connect and OAuth 2.0 if the application you're connecting to supports it. For more information, see [OAuth 2.0 and OpenID Connect protocols on the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/v2-protocols). For steps to implement OpenID Connect SSO, see [Set up OIDC-based single sign-on for an application in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/add-application-portal-setup-oidc-sso).
* **SAML** - Choose SAML whenever possible for existing applications that don't use OpenID Connect or OAuth. For more information, see [single sign-on SAML protocol](https://learn.microsoft.com/en-us/entra/identity-platform/single-sign-on-saml-protocol).
*   **Password-based** - Choose password-based when the application has an HTML sign-in page. Password-based SSO is also known as password vaulting. Password-based SSO enables you to manage user access and passwords to web applications that don't support identity federation. It's also useful where several users need to share a single account, such as to your organization's social media app accounts.

    Password-based SSO supports applications that require multiple sign-in fields for applications that require more than just username and password fields to sign in. You can customize the labels of the username and password fields your users see on My Apps when they enter their credentials. For steps to implement password-based SSO, see [Password-based single sign-on](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-password-single-sign-on-non-gallery-applications).
*   **Linked** - Choose linked when the application is configured for SSO in another identity provider service. The linked option lets you configure the target location when a user selects the application in your organization's end user portals. You can add a link to a custom web application that currently uses federation, such as Active Directory Federation Services (AD FS).

    You can also add links to specific web pages that you want to appear on your user's access panels and to an app that doesn't require authentication. The Linked option doesn't provide sign-on functionality through Microsoft Entra credentials. For steps to implement linked SSO, see [Linked single sign-on](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-linked-sign-on).
* **Disabled** - Choose disabled SSO when the application isn't ready to be configured for SSO.
* **Integrated Windows Authentication (IWA)** - Choose IWA single sign-on for applications that use IWA, or for claims-aware applications. For more information, see [Kerberos Constrained Delegation for single sign-on to your applications with Application Proxy](https://learn.microsoft.com/en-us/entra/identity/app-proxy/application-proxy-configure-single-sign-on-with-kcd).
* **Header-based** - Choose header-based single sign-on when the application uses headers for authentication. For more information, see [Header-based SSO](https://learn.microsoft.com/en-us/entra/identity/app-proxy/application-proxy-configure-single-sign-on-with-headers).

\
Enable single sign-on for an enterprise application
---------------------------------------------------

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

To configure SSO, you need:

* A Microsoft Entra user account. If you don't already have one, you can [Create an account for free](https://azure.microsoft.com/free/?WT.mc\_id=A261C142F).
* One of the following roles: Global Administrator, Cloud Application Administrator, Application Administrator, or owner of the service principal.
* Completion of the steps in [Quickstart: Create and assign a user account](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/add-application-portal-assign-users).

### Enable single sign-on <a href="#enable-single-sign-on" id="enable-single-sign-on"></a>

&#x20;Tip

Steps in this article may vary slightly based on the portal you start from.

To enable SSO for an application:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Cloud Application Administrator](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator).
2. Browse to **Identity** > **Applications** > **Enterprise applications** > **All applications**.
3. Enter the name of the existing application in the search box, and then select the application from the search results. For example, **Microsoft Entra SAML Toolkit 1**.
4. In the **Manage** section of the left menu, select **Single sign-on** to open the **Single sign-on** pane for editing.
5. Select **SAML** to open the SSO configuration page. After the application is configured, users can sign in to it by using their credentials from the Microsoft Entra tenant.
6. The process of configuring an application to use Microsoft Entra ID for SAML-based SSO varies depending on the application.&#x20;

<figure><img src="../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

1. In the **Set up Microsoft Entra SAML Toolkit 1** section, record the values of the **Login URL**, **Microsoft Entra Identifier**, and **Logout URL** properties to be used later.

### Configure single sign-on in the tenant <a href="#configure-single-sign-on-in-the-tenant" id="configure-single-sign-on-in-the-tenant"></a>

You add sign-in and reply URL values, and you download a certificate to begin the configuration of SSO in Microsoft Entra ID.

To configure SSO in Microsoft Entra ID:

1. In the Microsoft Entra admin center, select **Edit** in the **Basic SAML Configuration** section on the **Set up Single Sign-On with SAML** pane.
2. For **Reply URL (Assertion Consumer Service URL)**, enter `https://samltoolkit.azurewebsites.net/SAML/Consume`.
3. For **Sign on URL**, enter `https://samltoolkit.azurewebsites.net/`.
4. Select **Save**.
5. In the **SAML Certificates** section, select **Download** for **Certificate (Raw)** to download the SAML signing certificate and save it to be used later.

### Configure single sign-on in the application <a href="#configure-single-sign-on-in-the-application" id="configure-single-sign-on-in-the-application"></a>

Using single sign-on in the application requires you to register the user account with the application and to add the SAML configuration values that you previously recorded.

#### Register the user account <a href="#register-the-user-account" id="register-the-user-account"></a>

To register a user account with the application:

1. Open a new browser window and browse to the sign-in URL for the application. For the **Microsoft Entra SAML Toolkit** application, the address is `https://samltoolkit.azurewebsites.net`.
2. Select **Register** in the upper right corner of the page.
3. For **Email**, enter the email address of the user that can access the application. Ensure that the user account is already assigned to the application.
4. Enter a **Password** and confirm it.
5.  Select **Register**.

    \


    <figure><img src="../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure SAML settings <a href="#configure-saml-settings" id="configure-saml-settings"></a>

To configure SAML settings for the application:

1. On the application's sign-in page, sign in with the credentials of the user account that you already assigned to the application, select **SAML Configuration** at the upper-left corner of the page.
2. Select **Create** in the middle of the page.
3. For **Login URL**, **Microsoft Entra Identifier**, and **Logout URL**, enter the values that you recorded earlier.
4. Select **Choose file** to upload the certificate that you previously downloaded.
5. Select **Create**.
6. Copy the values of the **SP Initiated Login URL** and the **Assertion Consumer Service (ACS) URL** to be used later.

## RBAC&#x20;

RBAC is known as Role Based Access control. Azure role-based access control (Azure RBAC) helps in authorization and user access management of resources in Azure. Management of identity using Azure RBAC helps in controlling what users can do and cannot do, depending on the role they have in the organization.

## Azure roles

Security principal

A security principal is an object that represents a security identity that can be authenticated and authorized to access resources. Security principals are used in Azure roles to grant or deny resource permissions. They can be authenticated as a user, a security group, or a process that runs in a computer’s account security context. A security principal or a security group can be identified in a computer’s operating system using a unique security identifier (SID).

\
