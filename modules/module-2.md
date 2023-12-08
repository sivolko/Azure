# 💡 Module 2

## Azure Fundamentals

Azure is a public cloud provider, but it also offers private, hybrid, and multi-cloud solutions to users. Cloud services in Azure are designed to help users build innovative cloud solutions that help solve our challenges.

It allows us to build, develop, manage, and run resources like servers, databases, storage, or applications in multiple cloud environments. You can use it for different use cases in the cloud using the tools, programming languages, and frameworks that you prefer to use.

Azure offers over 200 services (as of time of writing) in various categories, including computing, networking, storage, databases, analytics, machine learning and AI, the Internet of Things (IoT), cloud-native, containers, and security. However, Microsoft continues to introduce new features and services to Azure regularly, so the number of services may increase over time.

## Benefits of a Cloud Provider



| Benefits              | Descriptions                                                                                                                                                                              |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| High availability     | Microsoft Azure provides high availability and redundancy across all of its worldwide data canters offering a service-level agreement that ensures 99.99% availability.                   |
| Geo-distribution      | Azure helps global enterprises by providing geo-distribution features. Geography-specific endpoints enables international enterprises to comply with regional compliance and regulations. |
| Scalability on-demand | When demand for complexity, traffic, and data expands, there is a flexible and quick way to handle such needs                                                                             |
| Reliability           | The system or application hosted functions correctly even in the face of adversity (hardware or software faults, and even human error)                                                    |
| Elasticity            | A capability to automatically scale cloud resources based on configuration or demand.                                                                                                     |
| Disaster recovery     | When your applications, data, and systems are hosted in Azure, you can be assured of secured end-to-end backup and disaster recovery solutions.                                           |
| Cost management tools | Tools available for cost management in Azure allow users to set budget alerts for their resource groups and resources.                                                                    |
| OpEx vs. CapEx        | Hosting to cloud means an organization can save money from capital expenditures (CapEx) and only pay for operational expenditures (OpEx).                                                 |

## Azure Portal&#x20;

The self-managed portal of Microsoft’s cloud platform is called the _Azure Portal_; it can be accessed by Azure users on their web browsers or via the _Azure mobile app_. It is a web-based administration website for all types of Azure users, where you can manage the Azure cloud services for your organization. It is a powerful portal of cloud administration tools and resources.

[Link: ](https://portal.azure.com)

Features of Azure Portal

* Create, build, manage, and monitor Azure services and cloud resources all in one place anytime and anywhere at your own convenience
* Use command-line tools and the cloud shell for quick creation and deployments
* Manage and organize Azure subscriptions and create management groups that helps in structuring and governing Azure resources
* Use Microsoft Entra ID to manage identity, access, and permissions to resources in Azure
* Configure and manage privacy, data, security, policies, and compliance vital to the organization’s governance
* Customize the portal’s dashboards to get a quick overview of the status of resources right after you log in
* Take control of monthly costs by monitoring resources through spending limits and budget alerts using Azure Cost Management in the Azure Portal

## Microsoft Azure Services

| Category                                             | Function                                                                                   | Azure Services                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Artificial Intelligence (AI) + Machine Learning (ML) | Build modern cloud apps with ML and cognitive integration                                  | Azure Boot Service, Azure Cognitive Services, Azure Machine Learning, Azure AI Anomaly Detector, Azure DataBricks, Azure Open Datasets, Computer Vision, Face API, Azure AI Immersive Reader, Azure AI Document Intelligence, Kinect DK, Microsoft Genomics, Azure Health Boot, Azure Applied AI Services, Azure Percept, Speech Services, etc.                                                                            |
| Analytics                                            | Gather and visualize any type of data regardless of its volume or velocity                 | Azure Analysis Services, Azure Data Explorer, Azure Data Lake Storage, Azure Data Share, Azure Databricks, Azure Stream Analytics, HDInsight, PowerBI Embedded, Azure Synapse Analytics, Data Factory, Event Hubs, R Server for HDInsight, Microsoft Graph Data Connect, Azure Purview, etc.                                                                                                                               |
| Compute                                              | Build robust applications with high-level cloud compute capacity and scalability features  | API Apps, App Service, Azure Cycle Cloud, Azure Functions, Azure Kubernetes Service (AKS), Azure Quantum Preview, Azure Spot Virtual Machines, Azure Spring Cloud, Azure VMware Solution, Azure Batch, Cloud Services, Linux Virtual Machines, Azure Container Instances, Azure Static Web Apps, VM Scale Sets, Azure Virtual Machines, Azure Virtual Desktop, Web Apps, Azure Dedicated Host, Azure VM Image Builder, etc |
| Containers                                           | Create, build, develop and manage containerized applications with modern integration tools | Azure Kubernetes Services (AKS), Azure Container Instances, Azure Container Registry, Azure Service Fabric, Web App for Containers                                                                                                                                                                                                                                                                                         |
| Databases                                            | Fully managed and secure cloud database services                                           | Azure SQL Database, Azure Cosmos DB, Azure Cache for Redis, Azure Database for PostgresSQL, Azure Database for MySQL, Apache Cassandra MI, SQL Server on Virtual Machines, Azure Database Migration Service, Table Storage, Azure API for FHIR, Azure SQL Database Edge, etc.                                                                                                                                              |
| Integration                                          | Services on Azure for different types of integration within Azure, hybrid or multi-cloud   | Azure API Management (APIM), Azure Event Grid, Azure Service Bus, Azure Logic Apps, Azure Web PubSub Preview, Azure Healthcare APIs Preview                                                                                                                                                                                                                                                                                |
| Networking                                           | Connect cloud and on-premises infrastructure and resources using networking services       | Application Gateway, Azure Bastion, Azure DNS, Azure Express Route, Azure Content Delivery Network, Load Balancer, Azure Front Door, Azure Firewall, Internet Analyzer, Azure Orbital, Private Link, VPN Gateway, Virtual WAN, Virtual Network, Traffic Manager                                                                                                                                                            |
| Identity + Security                                  | Protect resources, data and identity on the cloud                                          | Microsoft Entra ID, Microsoft Defender for Cloud, Azure Security Center, Azure Key Vault, Azure Sentinel, Information Protection, DDoS Protection, etc.                                                                                                                                                                                                                                                                    |

## Compute Services in Azure&#x20;

Compute is the term used for computing resources. Compute services hosted in Azure provide computing resources like operating systems, networking, disks, processors, and memory. These compute resources are available quickly and on-demand for users. Every application is unique. An application can have many workloads that need more than one compute service.

<figure><img src="../.gitbook/assets/image (8) (1) (1) (1).png" alt=""><figcaption><p>Compute Service </p></figcaption></figure>



| Azure Compute Service            | What is used for ?                                                                                                     |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Azure App Service                | Build and develop web and mobile apps in a fully managed cloud environment                                             |
| Azure Static Web Apps            | Develop modern full stack web application quickly with Azure from a code repository                                    |
| Azure Virtual Machines           | Quick and manageable provisioning of virtual machines (Azure VMs) in different operating systems like Windows or Linux |
| Azure Virtual Machine Scale Sets | Create and provision multiple virtual machines (Azure VMs) with high availability advantage                            |
| Azure Functions                  | Develop serverless, event-driven applications, and stateful workflows                                                  |
| Azure Container Apps             | Build and deploy fully managed modern apps and microservices using serverless containers                               |
| Azure Kubernetes Service(AKS)    | Build managed Kubernetes containers on the cloud                                                                       |

## Networking Services in Azure

Networking services help secure both private and public cloud infrastructure. Users can customize their cloud networking setup and manage their network resources on demand.



| Azure Networking      | What is it for?                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------ |
| Azure Virtual Network | Connect virtual machines using VPN connections                                                   |
| Azure Bastion         | Secure and easy access to your virtual machines using private RDF and SSH that are fully managed |
| Azure Private Link    | Access cloud Azure-hosted services with privacy                                                  |
| Azure Firewall        | Protect your resources in the cloud with high availability and low maintenance firewall          |
| Azure Load Balancer   | Load balance your application connections and requests, both inbound and outbound                |
| Azure ExpressRoute    | Create private network connections between Azure data centers and on-premises infrastructure     |
| Azure Traffic Manager | Route your network traffic for better performance                                                |
| Azure VPN Gateway     | Create secure private network connections in the cloud VPN                                       |

## Core Azure Storage Services

The storage services in Azure offer great storage for any type of data objects, Azure Virtual Machine disk storage, reliable messaging storage, and other modern data types. They provide the benefits of high availability, durability, security, accessibility, and manageability.

<figure><img src="../.gitbook/assets/image (9) (1) (1) (1).png" alt=""><figcaption><p>Azure Storage A/c</p></figcaption></figure>

## Core Azure Database Services

| Azure Database service                            | What is it for?                                                                                    |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Azure SQL Database                                | Cloud-hosted SQL databases that are fully managed, intelligent, and secure                         |
| Azure Cosmos DB                                   | Create and migrate NoSQL workloads to the cloud like Cassandra, MongoDB, and other NoSQL databases |
| Azure Cache for Redis DB                          | Build fast and scalable applications with Redis in-memory data store                               |
| Azure Database for PostgreSQL, MySQL, and MariaDB | Create fully managed and scalable databases for PostgresSQL, MySQL, and MariaDB                    |
| Azure SQL Edge                                    | Build IoT edge-optimized SQL database engine with built-in AI                                      |

## Identity Management and Security Services

| Azure Identity or Security service | What is it for?                                                                                                                                               |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Entra ID                 | Secure users’ identities and protect users of the entire organization using SSO and multi-factor authentication                                               |
| Azure Information Protection       | Protect your sensitive information on the cloud                                                                                                               |
| Azure Key Vault                    | Allows you to control, manage, and secure your keys, connection strings, and secrets                                                                          |
| Microsoft Defender for Cloud       | Protect and detect threats for your workloads in Azure, on premises, and even in other cloud providers                                                        |
| Microsoft Sentinel                 | Gather intelligent security information and event management (SIEM)  and security orchestration automated response (SOAR) solutions to protect your resources |
| Azure DDoS Protection              | Protect applications in Azure from distributed denial of service (DDoS) attacks                                                                               |
|                                    |                                                                                                                                                               |

## Developer Tools, Monitoring, and DevOps Services

| <p><br>Azure developer tools</p> | What is it for?                                                                                                                                     |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Azure DevOps                     | All-in-one tool with great DevOps services for teams to collaborate, share code, track work, and deliver software projects                          |
| Azure DevTestLabs                | Quickly create environments using reusable templates and artifacts                                                                                  |
| App Configuration                | Store your application’s configuration using scalable parameters                                                                                    |
| Visual Studio                    | Develop, debug, deploy, manage, and diagnose cloud-scale applications on Azure, using a full-featured IDE                                           |
| Visual Studio Code               | Write and debug code with a lightweight, fast code editor that runs on operating systems like Windows, Linux, and other supported operating systems |

## Monitoring&#x20;

| Azure monitoring tools | What is it for?                                                                                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Azure Monitor          | A great tool for maximizing application performance by collecting, analyzing, visualizing, and automating telemetry data in Azure and on-premises environments                        |
| Application Insights   | Provides features useful for application performance management (APM) such as live monitoring and automatic detection of performance issues                                           |
| Azure Advisor          | Innovative cloud assistance in Azure that helps you improve your deployments by recommending useful and actionable solutions to secure resources, save costs, and improve performance |
| Log Analytics          | Allows you to edit, run log queries, and analyze the data collected by [Azure Monitor Logs](https://oreil.ly/wafvf)                                                                   |

&#x20;Resource Management Concepts in Microsoft Azure\
\
Azure Management Groups
-----------------------

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

Azure management groups are the top level of the core structure for managing your cloud resources in Azure. The management groups are where Azure administrators manage everything about user access, compliance, and policies for subscriptions. The subscriptions within a management group automatically inherit the settings, conditions, and restrictions added in the group.

Azure role-based access control (RBAC) for all resources and role definitions is supported in the root management groups.

## Azure Subscriptions

Subscriptions in Azure are like a big container for all user accounts and resources they have accessed or used within the subscription. Every subscription has a limit of resources that a certain user can create and use. As an organization, you can use subscriptions to control the monthly bill and resource costs in your organization or your own Azure account. Using Azure subscriptions, the organization can also control what resources the users create, update, or delete.

## Azure Resource Groups

Azure users can group their services or resources using Azure resource groups. A resource group in Microsoft Azure acts as a logical container where resources like servers, web applications, databases, storage, monitoring, etc., are deployed, managed, and stored. Do not confuse a resource group with an availability set in Azure. The availability set is the logical group for virtual machines (VMs).

## Azure Resources

The databases, servers, virtual machines, or web applications you create on the Azure platform are considered Azure resources. All resources or services you create must be added to a resource group. which acts as the logical container. In a resource group, you can have web apps, servers, monitoring, compute services, etc., in one place.

\


<figure><img src="../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Azure Resource Manager

Azure Resource Manager (ARM) is also an important element in managing resources in Azure. ARM is the management and deployment service that provides users the capability to add, edit, and delete resources in Azure. By using ARM, the organization can manage user access control and organize resources securely even after deployment.

ARM templates are commonly used to automate deployments and to implement infrastructure as code (IaC). Azure provides native support for IaC using the ARM templates and also Azure Bicep in the Azure Resource Manager.

Terraform is also supported on Azure. IaC creates a great advantage, and it enables deployment automation of the infrastructure in the cloud. Using infrastructure as code, you can automate your deployment by generating templates for the same environment every time. The IaC process minimizes the problems of environment drift during development releases.

## Azure Geographies

Microsoft Azure has secured physical data centers worldwide in 140 countries. The global infrastructure of Azure, which also includes the infrastructure of Microsoft’s cloud platform, is important in providing reliable, secure, and innovative smart cloud solutions.

## Azure Regions

Azure regions play a vital role in cloud computing for adaptability because each country or region has unique restrictions, policies, compliance, and rules.\
\


<figure><img src="../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Azure Availability Zones

An availability zone is composed of one or multiple data centers with independent facilities for power, networking, cooling, and support. The purpose of this isolation is to make sure that in case one of the zones stops working properly, the other zone continues to operate. These availability zones are connected and equipped with secure high-speed networks, which is important in running mission-critical resources for your computing, networking, storage, and data.
