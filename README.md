- [Introduction](#introduction)
  * [Cloud Computing](#cloud-computing)
  * [What is Microsoft Azure](#what-is-microsoft-azure)
  * [Resource group](#resource-group)
  * [Resource Location](#resource-location)
- [Virtual Machines](#virtual-machines)
  * [Virtual Machine Series](#virtual-machine-series)
  * [Pricing](#pricing)
  * [Cost management](#cost-management)
  * [State of the virtual machine](#state-of-the-virtual-machine)
  * [Azure Marketplace](#azure-marketplace)
  * [Availability sets](#availability-sets)
  * [Availability Zones](#availability-zones)
- [Networking](#networking)
  * [Azure Virtual Network](#azure-virtual-network)
    + [Lab exercise](#lab-exercise)
  * [Network Security Group](#network-security-group)
  * [Site-site VPN](#site-site-vpn)
- [Azure Storage Services](#azure-storage-services)
  * [Azure Storage Accounts](#azure-storage-accounts)
  * [Azure Blob Storage](#azure-blob-storage)
    + [Storage account options](#storage-account-options)
    + [Blob Storage Service](#blob-storage-service)
    + [File Shares](#file-shares)
    + [Queue storage](#queue-storage)
    + [Table Storage](#table-storage)
  * [Azure SQL Database](#azure-sql-database)
    + [Purchase models](#purchase-models)
    + [Lab](#lab)
  * [Azure Synapse Analytics](#azure-synapse-analytics)
    + [Azure Cosmos DB](#azure-cosmos-db)
    + [Lab:](#lab-)
    + [Azure SQL Datawarehouse vs Cosmos DB](#azure-sql-datawarehouse-vs-cosmos-db)
- [Cloud Concepts](#cloud-concepts)
  * [High availability](#high-availability)
  * [Scalability (Performance)](#scalability--performance-)
  * [Disaster recovery](#disaster-recovery)
  * [Elasticity](#elasticity)
  * [Fault Tolerance](#fault-tolerance)
  * [Cloud Service Model](#cloud-service-model)
  * [Cloud Models](#cloud-models)
  * [Economies of scale](#economies-of-scale)
- [Azure Core Services](#azure-core-services)
  * [Azure Web App](#azure-web-app)
  * [App Service Plan](#app-service-plan)
    + [Lab](#lab-1)
  * [Virtual Machine Scale Sets](#virtual-machine-scale-sets)
    + [Lab](#lab-2)
  * [Azure Load Balancer](#azure-load-balancer)
    + [Lab](#lab-3)
  * [ARM Templates](#arm-templates)
    + [Lab:](#lab--1)
  * [Azure Traffic Manager](#azure-traffic-manager)
    + [Lab](#lab-4)
  * [Azure PowerShell (Command line tool)](#azure-powershell--command-line-tool-)
  * [Azure CLI (Command line tool)](#azure-cli--command-line-tool-)
  * [Azure Cloud shell](#azure-cloud-shell)
  * [Azure Functions](#azure-functions)
    + [Lab](#lab-5)
  * [Azure Logic Apps](#azure-logic-apps)
    + [Lab](#lab-6)
- [Security, privacy, compliance and trust](#security--privacy--compliance-and-trust)
  * [Azure Active Directory (Azure AD)](#azure-active-directory--azure-ad-)
  * [Multi-factor Authentication (MFA)](#multi-factor-authentication--mfa-)
  * [Role based access control (RBAC)](#role-based-access-control--rbac-)
  * [Azure Key Vault](#azure-key-vault)
  * [Azure Policies](#azure-policies)
  * [Locking Resources](#locking-resources)
  * [Azure Security Center](#azure-security-center)
  * [Azure AD Identity protection](#azure-ad-identity-protection)
  * [Azure AD privileged identity management](#azure-ad-privileged-identity-management)
  * [Azure Blueprints](#azure-blueprints)
  * [Azure Firewall](#azure-firewall)
  * [Azure DDoS protection](#azure-ddos-protection)
  * [Azure Information Protection](#azure-information-protection)
  * [Other security standards](#other-security-standards)
    + [GDPR (General Data Protection Regulation)](#gdpr--general-data-protection-regulation-)
    + [NIST (National Institute of Standards and Technology)](#nist--national-institute-of-standards-and-technology-)
    + [Service Trust Portal](#service-trust-portal)
    + [Azure Government](#azure-government)
- [Azure pricing and support](#azure-pricing-and-support)
  * [Azure Updates](#azure-updates)
  * [Help + Support options in Azure](#help---support-options-in-azure)
  * [Factors that affect the cost](#factors-that-affect-the-cost)
  * [Service Level Agreement (SLA)](#service-level-agreement--sla-)
  * [Total cost of ownership (TCO) calculator](#total-cost-of-ownership--tco--calculator)
  * [Creating Budgets](#creating-budgets)
  * [Resource tags](#resource-tags)
  
# Introduction

Cloud services include servers, storage, databases which are delivered over the internet.

You pay only for what you use.

Traditional data centers

![][1]

## Cloud Computing

-   You don\'t need to manage data centers, no need to buy physical hardware

-   You can create resources on cloud

-   You pay for what to use.

## What is Microsoft Azure

Microsoft Azure has lot of services that keep expanding.

<https://azure.microsoft.com/en-us/>

## Resource group

A resource group is a logical container of resources.

Management of permissions becomes easy with resource groups.

## Resource Location

-   Microsoft data centers are located around the world.

![][2]

-   You would ideally create resource in a region that is closest to your users.

-   Pricing differs from region to region

-   Some resources may not be available in some regions.

# Virtual Machines

-   You don\'t need to manage the underlying physical server.

-   You only pay for what you use.

-   You can deploy both Windows and Linux based servers.

## Virtual Machine Series

-   A Series are entry level VMs, good for test and dev environments

-   D Series are good for production workloads

-   As you move up the series, the price will be higher

## Pricing

Azure provides pricing calculator to estimate the cost of services

<https://azure.microsoft.com/en-us/pricing/calculator/>

You can reduce the price of services by reserving them for longer term like 1 year or 2 years.

## Cost management

You can monitor the on-going costs and the forecasted costs in Azure cost management and billing.

You can also set the budget limit and get alerts if the cost exceeds the budget limit.

## State of the virtual machine

When you shut down the Virtual machine from the portal, the VM will be deallocated, and the IP address might change.

If you don\'t want to have the IP address changed, shut down the VM from within the OS.

(Or)

You can assign a static IP if you don\'t want to change the state of your virtual machine.

## Azure Marketplace

Azure Marketplace contains lot of pre-configured services that you can choose from.

## Availability sets

Without availability sets, due to power failures or other maintenance issues, the VM can become unavailable.

![][3]

With availability sets, you can deploy VMs to different fault domains, so that if one VM fails, the other VM is still available for use.

Apart from fault domains, update domains help to reboot VM one at a time, so that at least one VM is available when updates are happening.

With availability sets, you can achieve an Service Level Agreement (SLA) of 99.95%.

## Availability Zones

With availability zones, services are replicated across different data centers in a region. So, if one data center fails, your application is still available and accessible from other data center.

![][4]

# Networking

## Azure Virtual Network

Azure Virtual Networking is home of VMs.

![][5]

![][6]

Virtual Networking consists range of IP addresses. The VMs you launch in the virtual networking will get IP addresses within that range.

Each Virtual Newtork contains subnets. Subnet is a logical subset within Virtual Network.

Each subnet contains range of IP addresses. You can create VM within a subnet.

The IP addresses are private addresses, communication within the virtual networking happens using private IP addresses.

### Lab exercise

-   Create Virtual Newtork with 2 subnets

-   Create 2 VMs in each in a different subnet

## Network Security Group

Network security group controls the flow of traffic into and outside of virtual machines.

Network security group attaches to either the network interface of the VM or to the entire subnet.

Some default rules e.g., traffic within a virtual network cannot be modified or removed.

In order to add a network security rule, you need to define

1.  Priority

2.  Port

3.  Protocol -- TCP/UDP

4.  Source and Destination

## Site-site VPN

Site to site VPN allows users on your corporate network to a virtual network in Azure.

![][7]

To create site-to-site VPN, you need

-   Gateway subnet

-   Virtual private gateway

-   Local gateway

All the traffic is encrypted using IPSec

# Azure Storage Services

## Azure Storage Accounts

Azure storage is used to store objects to decouple from main applications.

**Blob storage**: Supports storing objects such as images, videos, Virtual hard disk (VHD) files.

**Table Service**: Can store table like data such as user information.

**File Shares**: File shares stores information that can be shared by different users or VMs.

**Queue**: Can be used to queue messages.

-   **Type**: It is recommended to use the latest General-purpose V2.

-   **Performance tier:** "Standard" supports blob, file, table and queue

    -   Premium tier supports only Virtual Hard Disks (VHD).

-   **Access tier**: Hot access tiers are optimized for frequent access. Access costs are optimal, but the storage costs are higher

    -   Cool tier: Use for large amounts of data that are infrequently accessed. Storage costs are lower than Hot access tiers, but access costs are higher than the hot access tier.

    -   Archive tier: This is when you want to archive objects. Here the storage costs are much lower.

-   Replication techniques

    -   Locally Redundant Storage: Data is replicated 3 times within the primary region.

    -   Zone redundant storage: Data is replicated synchronously across 3 Azure availability zones in the primary region.

    -   Geo-redundant storage: Data is replicated 3 times in the primary region, then replicated asynchronously to the second region.

    -   Read access Geo-redundant storage: Data is replicated 3 times synchronously in the region, then replicated asynchronously to the secondar region. Data in secondary region is also available for read-only purposes.

## Azure Blob Storage

Blobs are object files that can be stored within a container.

-   Block blobs -- store text and binary data

-   Append Blobs -- Good for log files

-   Page blobs -- used to store virtual hard disk files

### Storage account options

-   General Purpose (v2): Latest features for Blob, files, queues and tables.

    -   You can also choose between hot and cool tier.

-   General Purpose (v1)

    -   Earlier version of storage accounts.

-   Blob storage accounts

    -   Only supports block blobs

### Blob Storage Service

Lab:

-   Create a container

-   upload a text file with private access

-   Access the URL of the blob file

-   change the access from private to blob

-   change the blob access tier from hot to cool

### File Shares

![][8]Earlier, file shares are created in physical servers.

Equivalent of that service is File Share in Azure.

File shares are used for the files that are commonly used by many VMs or users.

Can be accessed via the Server Message Block.

### Queue storage

-   Exchange messages across applications

### Table Storage

-   Used for storing NoSQL data

-   There is no specific schema

![][9]

-   Use table storage if you don\'t need to do complex joins, foreign keys and stored procedures.

## Azure SQL Database

-   Can be created either as **Infrastructure-as-a-Service** (IaaS) or **Platform-as-a-Service** (PaaS).

    -   You don\'t have to worry about managing, updating and patching SQLDB with PaaS.

```{=html}
<!-- -->
```
-   There are 3 options available

    -   Single database

        -   Simple and single database

    -   Managed instance

        -   Better option to lift and shift on-premise SQL server

    -   Elastic pool

        -   Combine SQL Databases into Elastic pool. All the databases share the underlying resources.

### Purchase models

**DTU** (Database Transaction Unit)

-   Blended measure of CPU, Memory and read-write rates

![][10]

**VCore**-based

-   You can independently scale the compute and storage

-   You can also make use of Azure Hybrid benefit

**Managed Instance** offer

-   New deployment model that allows for easy migration of existing on-premise sql server databases.

### Lab

-   Create SQL Database

-   Use Basic DTU tier

-   Enable sample database

-   Set the server firewall

## Azure Synapse Analytics

![][11]

Data Warehouses are used to do analysis on large amounts of data which is coming in constantly from wide variety of source systems.

Lab

-   Create Azure Synapse Analytics

-   Create Data Factory

-   Create Storage account

-   Copy data from SQL Database to Azure Synapse Analytics via Storage Account

### Azure Cosmos DB

Cosmos DB is a multi-model database. It supports different APIs such as (Core) SQL, Table, MongoDB, Cassandra, Gremlin.

Cosmos DB supports single digit millisecond latency.

Cosmos DB supports global distribution.

-   Supports multiple APIs

-   Provides 99.999% high availability

-   Guarantees less than 10-ms latencies for both reads (indexed) and writes

-   You are charged based on the number of request units and storage consumed

    -   A request unit is a blend of % memory, % cpu, % iops

-   Request unit assigned determines the throughput. It can be assigned either at database level or container level.

### Lab:

![][12]

-   Create Azure Cosmos DB account

-   Create databases

-   Create container

-   Create items

### Azure SQL Datawarehouse vs Cosmos DB

If your application needs No-SQL (json like) data, and needs very low latency, consider Cosmos DB.

If your application has lot of tables, and use complex queries and joins, then consider using Azure SQL Datawarehouse.

# Cloud Concepts

## High availability

High availability is achieved by replication of your data or services.

![][13]

E.g. in case of Storage account, you can improve the high availability using replication options such as Local redundant storage, Geo redundant storage.

## Scalability (Performance)

If the load on the application increases, then cloud supports scalable options to handle the increased workload.

![][14]

## Disaster recovery

Cloud supports automatic disaster recovery by using replication techniques.

![][15]

## Elasticity

You can resize resources to scale up to the demand.

![][16]

## Fault Tolerance

Fault tolerance helps your application recover from faults.

![][17]

## Cloud Service Model

![][18]

**Infrastructure as a Service (IaaS) (e.g. Farming, cooking, eating)**

-   Example is Azure virtual machine service

-   You don\'t need to manage the underlying infrastructure.

-   Physical servers and storage is managed for you.

**Platform as a Service (PaaS) (e.g. Food market, cooking, eating)**

-   Example is Azure SQL database or Azure Web ap.

-   You don\'t need to manage the infrastructure or even the underlying OS and platform.

-   You can simply start hosting your data or your web application.

**Software as a service (SaaS) (e.g. Restaurant food)**

-   E.g Microsoft Office 365

```{=html}
<!-- -->
```
-   You don\'t need to manage the infra or underlying OS or even software.

-   You just directly start using the software.

## Cloud Models

![][19]

**Private Cloud**

-   Cloud accessible only within the users within organization.

-   Data will not go outside of your private cloud.

-   Underlying servers are managed by your organization.

**Public Cloud**

-   Services offered over public internet

-   All the services and storage is managed by the cloud provider.

**Hybrid cloud**

-   Connection is established between private cloud and public cloud.

## Economies of scale

-   Cloud providers can actually buy hardware at a larger discount.

-   They pass the costs to customers.

-   If the number of customers increase, then cloud provider may reduce the costs to customers.

Capital Expenditure

-   Spending money on physical infrastructure upfront.

Operational expenditure

-   Ongoing money spent for services and products.

-   Electricity, cooling.

# Azure Core Services

## Azure Web App

Azure Web App is a PaaS which is used to host web applications.

Azure Web App supports having multiple slots for maintaining staging and production sites.

## App Service Plan

While creating Web App, you should also create App Service Plan. Different app service plans offer different features.

<https://azure.microsoft.com/en-us/pricing/details/app-service/windows/>

![][20]

App service plans determine the disk space, high availability, instances, deployment slots, auto-scaling etc.

### Lab

-   Create Web App

-   Choose Windows OS and ASP.NET as runtime stack.

-   Choose Basic App Service Plan

-   Create ASP.net application -- Web forms

## Virtual Machine Scale Sets

VM scale sets automatic scaling of the VM instances based on the workload (e.g CPU, memory, IO)

![][21]

### Lab

-   Create Virtual Machine Sale set

-   Use Ubuntu Server 18.04 LTS image

-   Enable auto-scale

    -   Choose 3 as max VMs

    -   scale-out when CPU threshold \> 50%

    -   scale-in when CPU threshold \< 30%

    -   Choose none for load balancing

    -   Give public IP

    -   Allow SSH port

    -   Stress test

        -   Sudo apt-get update

        -   Sudo apt-get install stress

        -   Stress --cpu 100

## Azure Load Balancer

Load balancer distributes the traffic to your Virtual machines.

![][22]

Load balancer requires configuring

-   **Backend pool** (Associate backend virtual machines to Load balancer)

-   **Frontend IP** is a public IP of load balancer

-   **Health probe** is used by load balancer to identify if backend virtual machines are healthy (up & running) or not.

-   **Load balancing rules** defines the traffic rules based on certain criteria e.g. VM listening port.

### Lab

-   Create 2 Virtual machine in the same VNET

    -   B2ms Windows server 2016 data center

    -   Choose Standard IP address SKU

-   Create IIS on both virtual machines

    -   Create Home.html under C:/inetpub/wwwroot

-   Create and configure standard load balancer

    -   Create Standard SKU, and make it zone redundant

    -   Add backend pools of 2 VMs.

    -   Create health probe on port 80

    -   Create load balancing rule

## ARM Templates

ARM templates help to deploy your underlying infrastructure using infrastructure a code.

ARM templates contain

-   Parameters: You can define parameters that accept dynamic values

-   Variables: Reusable values

-   User-defined functions: Your own custom functions

-   Resources: Specify resources that are going to be deployed

-   Outputs: Values returned from the deployed resources.

### Lab:

-   Go to Template Deployment

-   Use custom template

-   Use storage account template

## Azure Traffic Manager

-   Route traffic to different endpoints

![][23]

-   Routes

    -   Priority: Route traffic to another if primary fails

    -   Weighted: Route traffic based on weight

    -   Performance: Route end users based on closes endpoint

    -   Geographic- based on geography location

### Lab

-   Create 2 Web apps -- one in east US and the other in West US

    -   ASP.net

    -   Standard plan

-   Create a traffic manager profile with priority routing

    -   Choose Azure endpoint app service

-   Stop one web app and notice what happens.

## Azure PowerShell (Command line tool)

Command line tool to interact with Azure services.

-   *Install-Module --Name Az --AllowClobber*

-   *Get-AzStorageAccount --ResourceGroupName "azuredemo"*

## Azure CLI (Command line tool)

Another command line tool to interact with Azure services.

-   *az storage account create \--location \"Central US\" \--name yourstorageaccountname \--resource-group yourresourcegroupname \--sku \"Standard_LRS\"*

## Azure Cloud shell

You can run commands (PowerShell or Azure CLI) directly from the shell in Azure Portal.

![][24]

## Azure Functions

Azure functions are serverless service

-   Allows you to run small pieces of code as functions

-   You get billed for the amount of time the code runs

-   Azure functions can be developed using C#, Java, JavaScript, PowerShell and Python.

Azure functions can be invoked using

-   HTTP trigger, Timer trigger, Blob storage trigger, Queue storage trigger and Event Hubs

Pricing plans

-   Consumption plan: Pay for the time the code runs

-   App service plans -- Dedicated app service plan

### Lab

-   Create function app using consumption plan

-   Use in portal option

    -   Simple HTTP trigger

-   Call the function via POSTMAN tool

## Azure Logic Apps

Logic Apps provide serverless GUI workflows that consume a range Connectors and perform actions such as sending automated alerts etc.

### Lab

-   Create blob storage triggered logic app

-   Receive an automated email

![][25]

# Security, privacy, compliance and trust

## Azure Active Directory (Azure AD)

![][26]

Azure AD contains users and groups of an organizations.

## Multi-factor Authentication (MFA)

Multi-factor authentication sets extra authentication (e.g., SMS or phone call or email) on top of basic login.

## Role based access control (RBAC)

RBAC provides fine-grained access control on the resources in Azure platform.

You can apply roles either at the Subscription level or the resource group or at individual resource level.

There are several built-in roles available in Azure. The commonly used ones are

-   Owner: Manage everything including access

-   Contributor: Manage everything excluding access

-   Reader: View the resources, but cannot modify

## Azure Key Vault

-   Helps you perform secret management. You can securely store your tokens, passwords and other secrets.

## Azure Policies

-   Use the in-built rules or create your own rule is to enforce governance for resources

    -   e.g., When a VM is created, it needs to be of a certain SKU size.

    -   e.g., Enforce mandatory tags while creating Azure resources.

## Locking Resources

-   Locking resources can help ensure users don\'t accidently delete or modify resources.

-   2 types of locks

    -   ReadOnly -- users can only read, but cannot modify or delete

    -   Delete -- users can read and modify, but cannot delete

## Azure Security Center

-   You can use this tool to improve the security of your Azure based resources.

-   Azure security center has in-built support for services such as Azure VM, Function apps, Azure SQL Server databases.

## Azure AD Identity protection

-   This is a service that can help detect suspicious actions related to user identities.

-   Sign-ins from anonymous IP addresses, unfamiliar locations.

## Azure AD privileged identity management 

-   You can provide time-bound access to resources using start and end dates.

## Azure Blueprints

-   This is a service that allows you to define repeatable set of Azure resources.

-   Some differences between Azure blueprints and resource manager templates

    -   You can use blueprints to upgrade several subscriptions.

## Azure Firewall

![][27]

-   This is a managed, cloud based network security servie that can be used to protect your network resources.

-   It has features such as Threat intelligence, this can filter incoming requests and alert or deny traffic from/to malicious IP addresses and domains.

-   Firewall itself has built-in high availability, and can scale automatically based on network traffic flows.

## Azure DDoS protection

-   This service help protect against Distributed denial of service attacks.

-   This is probably the biggest security concern from companies when they expose their applications to public internet.

-   You have 2 plans for Azure

    -   Basic: Is automatically enabled.

    -   Standard: Has more benefits such as real time attack metrics and diagnostics logs.

## Azure Information Protection

-   This is a solution that can help an organization classify and protect its documents and email by applying labels such as Confidentials, Internal, Public etc.

## Other security standards

### GDPR (General Data Protection Regulation)

-   This is a set of rules that help EU citizens have more control over their personal data.

-   Under this schema, organizations have to ensure that personal data is gathered legally and under strict conditions.

### NIST (National Institute of Standards and Technology)

-   This is an organization with looks at U.S innovation.

### Service Trust Portal

-   You can see if services conform to certain standards such as ISO 27001, NIST etc

### Azure Government

-   This is specially reserved by US government agencies and customers.

# Azure pricing and support

## Azure Updates

Page that displays important Azure product updates, roadmap and announcements. You can subscribe to notifications and stay informed.

<https://azure.microsoft.com/en-us/updates/>

![][28]

There is no guarantee of SLA on the preview services.

## Help + Support options in Azure

You can create support request from Azure portal. The response time depends on your support plan.

![][29]

-   **Basic plan** is available for all Azure accounts. Technical support is not available with Basic plan.

-   **Developer plan** provides business hour access to support engineers via email.

-   **Standard plan** comes with faster response times based on the severity.

-   **Professional Direct** has faster responses and also architecture guidance.

-   **Premier support** has designated technical account manager, less than 15-minute responses.

You can also see the **Service Issues, Planned maintenance** under Help + Support.

You can also create **health alerts**.

## Factors that affect the cost

-   Each service has factors that affect the cost

-   For e.g., for storage account

    -   Volume of data, quantity of operations, data redundancy

-   Data transfer costs

    -   Uploading or downloading data from storage

    -   All Azure inbound transfers are free.

    -   Outbound data transfers have cost

## Service Level Agreement (SLA)

<https://azure.microsoft.com/en-us/support/legal/sla/summary/>

Microsoft provides SLA guarantees for services based on the plans and tiers and replications.

Microsoft will provide service credits if SLAs are not guaranteed.

![][30]

## Total cost of ownership (TCO) calculator

Estimate the cost savings you can realize by migrating your workloads to Azure.

![][31]

## Creating Budgets

![][32]

You can create budgets to set the limits and get automated alerts when budget exceeds certain threshold.

## Resource tags

-   Tags can be used to logically organize resources

-   You can generate billing reports based on tags.

-   

  [1]: images/f33305ba8e7d5f27f193195031b29d5bd48d4cbd.png {width="5.0in" height="2.5in"}
  [2]: images/ae1349794ea06155121fddf963478a296c26b00c.png {width="5.770833333333333in" height="2.8613713910761156in"}
  [3]: images/4ce6a125a4b772be812c203c2cf6afe2533ee775.png {width="3.3109219160104986in" height="2.1727930883639544in"}
  [4]: images/8553211f890922323ccc0b7855653d19d14c89e0.png {width="4.4690660542432195in" height="2.6628182414698163in"}
  [5]: images/44164e6ca812e81daf2e745beb2489429006fbd0.png {width="3.15625in" height="2.0844400699912513in"}
  [6]: images/6a73e2eb463d945f17738f0f53e689933c2c2125.png {width="4.34375in" height="2.4071620734908135in"}
  [7]: images/2c5e0c09ed49a989915a91d043985152f696db62.png {width="4.820627734033246in" height="2.2395833333333335in"}
  [8]: images/63dbf4a59a847679d2a575c7e3a8906fe8b6d3e6.png {width="1.2291666666666667in" height="1.2291666666666667in"}
  [9]: images/a891af890badf2e73aa1c7e2383f2fb0ab6d34ef.png {width="5.0in" height="1.2604166666666667in"}
  [10]: images/4b4319e7555ff9a77b00bee027cc5bb672e93822.png {width="5.0in" height="3.5in"}
  [11]: images/b519ea28bb5f5539283beca43b9e7b6a434e8aa7.png {width="5.0in" height="3.78125in"}
  [12]: images/cb4a55952618d07784eab5d32bbe98556ec7f795.png {width="3.3229166666666665in" height="2.464496937882765in"}
  [13]: images/bce8e76f348b00547d2b07093a59ecacef6700d6.png {width="3.03125in" height="1.9829429133858267in"}
  [14]: images/0921ccf565a898570e1b5a3985feefb9ce11fe31.png {width="2.8645833333333335in" height="1.826172353455818in"}
  [15]: images/dfbdf4361585fd5e56a0dbcdbb1da96f321b4dbf.png {width="2.8754965004374453in" height="1.5096358267716536in"}
  [16]: images/9aefd1cfd0f8d0b7758f6149cee8a341199be8d5.png {width="5.0in" height="3.1041666666666665in"}
  [17]: images/97f18f064440ac48d15d5d5d492c59b39a25f9e3.png {width="3.75in" height="2.1796872265966756in"}
  [18]: images/287d3cf27ea87fef8f33673e6ee6367af47e7229.png {width="3.8854166666666665in" height="2.5336154855643045in"}
  [19]: images/36e1dc7a801cf9abc833ee54a29ff2a9b08f54b8.png {width="3.2093657042869643in" height="2.4270833333333335in"}
  [20]: images/533f6230d791672a82779eca765759d4872c76f7.png {width="5.50209208223972in" height="2.7395833333333335in"}
  [21]: images/91ec914152d307dd62a01c5670f26edb52d0510f.png {width="3.2083333333333335in" height="2.232465004374453in"}
  [22]: images/9b39038aba0775298140559877ac36a0217fccd7.png {width="3.40625in" height="1.8734372265966754in"}
  [23]: images/599ec677b375022c32c719a8f279698f813dcde5.png {width="3.097014435695538in" height="2.59375in"}
  [24]: images/eb85b1791d4725eed28fd2775b62c2905f797824.png {width="5.0in" height="4.875in"}
  [25]: images/49d60c7a1bcd8e5e394bf46ea9df2c706237f1ab.png {width="5.0in" height="1.75in"}
  [26]: images/d7c398c472161c8fd696d5e62b549cd5a9155412.png {width="5.0in" height="2.2604166666666665in"}
  [27]: images/70555b5f69e9fa2d1d95ae2b685c90287c62eae2.png {width="5.0in" height="2.8125in"}
  [28]: images/ed27452d43f207a19d51ae6bda6c00339b247e52.png {width="5.0in" height="2.96875in"}
  [29]: images/9ca595abc424fa35d11e8af95b4797876b7a2c0b.png {width="6.145833333333333in" height="2.4455293088363956in"}
  [30]: images/7e5ed3abd59cd86306644fd89e27b5f512555195.png {width="5.0in" height="1.4166666666666667in"}
  [31]: images/637f1be11356c10b2677ba3e4aaea5d30459c245.png {width="5.0in" height="3.3229166666666665in"}
  [32]: images/58c5560b20f2e28c71b0b7f60301922263fa7662.png {width="5.0in" height="2.2083333333333335in"}
