## Networking Models
Networking models standardize how diverse software and hardware systems communicate across networks. By dividing complex communication tasks into isolated layers, networks become scalable, resilient, and vendor-agnostic.

![[Pasted image 20260830234740.png]]

The classic seven-layer OSI model breaks these tasks into two main groupings: ***the Lower Layer*** and ***the Upper Layer***.

- ***The Lower Layer (Data Transport) consists of Layers 1 through 4:*** *(Physical, Data Link, Network, and Transport.)* This layer handles the physical transmission and delivery mechanics. It receives raw bits from physical hardware, groups them into structured frames, and attaches destination addressing to convert those frames into packets. A good analogy is placing loose goods into standardized shipping boxes and slapping destination labels on them so network devices know where to route them.
- ***The Upper Layer (Application / Host) consists of Layers 5 through 7:*** *Session, Presentation, and Application.* Once data reaches its destination, this layer handles session establishment, maintenance, and termination between hosts. It also translates raw incoming data into a standardized format that any application can understand and verifies if a remote system is ready to communicate.

To see how these concepts apply, consider a real-world scenario:

An employee sends an encrypted document using a web browser. Before any data hits the network cable, system processes must establish the communication session, encrypt the document, and translate it into a format the recipient's web browser can display.

## Open Systems Interconnection (OSI) Model  
The OSI Model was developed to establish a common way to describe the communication structure for interconnected computer systems.

The OSI model divides networking tasks into **seven** distinct layers. Each layer is responsible for performing specific tasks or operations with the goal of supporting data exchange (in other words, network communication) between two computers. The layers are interchangeably referenced by name or layer number.

For example, ***Layer 3*** is also known as the *network layer*. The layers are ordered specifically to indicate how information flows through the various levels of communication. Each layer communicates directly with the layer above and the layer below it. For example, ***layer 3*** communicates with both the ***data link (2)*** and ***transport (4) layers.***

The ***application, presentation, and session layers (5-7)*** are commonly referred to simply as ***data***. However, each layer has the potential to perform encapsulation. ***Encapsulation*** is the addition of header and possibly footer (trailer) data by a protocol used at that layer of the OSI model. Encapsulation is particularly important when discussing transport, network and data link layers (2-4), which all generally include some form of header.

At the ***physical layer (1)***, the data unit is converted into *binary*, for example, *01010111*, and sent across *physical wires such as an ethernet cable*.

It's worth mapping some common networking terminology to the OSI Model so you can see the value in the conceptual model.

Consider the following examples:
- When someone references an Image file like a JPEG or PNG, we are talking about the ***presentation layer (6)***.
- When discussing routers that are sending packets, we are discussing the ***network layer (3)***.
- When discussing logical ports such as NetBIOS, we are discussing the ***session layer (5).***
- When discussing switches, bridges, or WAPs sending frames, we are discussing the ***data link layer (2).***
- When discussing TCP/UDP, we are discussing the ***transport layer (4).***

Encapsulation occurs as the data moves down the OSI model from application to physical. As data is encapsulated at each descending layer, the previous layer's header, payload and footer are all treated as the next layer's payload. The data unit size increases as we move down the conceptual model and the contents continue to encapsulate.

The inverse action occurs as data moves up the OSI model layers from physical to application. This process is known as ***de-encapsulation (or decapsulation)***. The header and footer are used to properly interpret the data payload and are then discarded. As we move up the OSI model, the data unit becomes smaller. The encapsulation/de-encapsulation process is best depicted visually below:

![[OSI Model.png]]

## Memorandum of Understanding (MOU) and Memorandum of Agreement (MOA)
Some organizations seeking to minimize downtime and enhance ***BC (Business Continuity)*** and ***DR (Disaster Recovery)*** capabilities will create agreements with other, similar organizations. They agree that if one of the parties experiences an emergency and cannot operate within their own facility, the other party will share its resources and let them operate within theirs to maintain critical functions. These agreements often include competitors, because their facilities and resources meet the needs of their particular industry.

For example, Hospital A and Hospital B are competitors in the same city. The hospitals create an agreement with each other: if something bad happens to Hospital A (e.g., a fire, flood, bomb threat, loss of power), that hospital can temporarily send personnel and systems to work inside Hospital B to stay in business during the interruption, and Hospital B can relocate to Hospital A, if Hospital B has a similar problem. The hospitals have decided that they are not going to compete based on safety and security—they are going to compete on service, price, and customer loyalty. This way, they protect themselves and the healthcare industry as a whole.
### 1. Mutual Aid & Resource-Sharing Agreements 🤝
- **Purpose**: Organizations create high-level agreements to share facilities and computing resources during an emergency (like a fire, flood, power outage, or cyber incident) to minimize downtime.
- **Competitor Collaboration**: These agreements often involve direct competitors in the same geographic region because their facilities and specialized infrastructure are identical.
- **Cooperation Philosophy**: Organizations agree not to compete on physical safety and security, choosing instead to compete on service, pricing, and customer satisfaction.
- **Drivers**: These arrangements can be voluntary, mandated by **regulatory requirements**, or established as **administrative safeguards** required by industry standards.
### 2. MOU / MOA vs. Service-Level Agreement (SLA) 📜 vs ⏱️

| **Agreement Type 🛠️**            | **Focus & Scope 🎯**                                                                                        | **Example Scenario 💡**                                                                                                              |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **MOU / MOA / JOA**               | High-level understanding of **what can be done** with systems, data, and shared facilities during a crisis. | Hospital A agrees to host Hospital B’s staff and systems if Hospital B suffers a facility disaster.                                  |
| **Service-Level Agreement (SLA)** | **Granular, technical performance metrics** and strict operational requirements.                            | A third-party IT contract requiring 2 full-time technicians on-site Mon–Fri, or guaranteed cloud data restoration within 10 minutes. |

### 3. Cloud Outsourcing & Legal Cautions ☁️
- **Scope Ambiguity**: Vague terms in an SLA can create a false sense of security. For example, a clause promising "100% access" might mean their web portal is online during business hours—not that your specific data is immediately accessible to you in real time.
- **Legal Review**: Security teams must collaborate with **legal counsel** to review, clarify, and approve all SLA conditions before signing to ensure recovery time objectives (RTOs) are legally enforceable.

## Cloud Computing
Cloud computing is usually associated with an internet-based set of computing resources, and typically sold as a **service** provided by a **cloud service provider (CSP)**.

Cloud computing is similar to the electrical or power grid. It is provisioned in a geographic location and is sourced using an electrical means that is not necessarily obvious to the consumer. However, when you want electricity, it's available via a common standard interface an you pay only for what you use. 

Cloud computing is scalable, elastic, and easy-to-use for the provisioning and deployment of Information Technology (IT) services. 

There are various definitions of what cloud computing means per leading standards, including NISTs.

This NIST definition is commonly used around the globe, cited by professionals to clarify what the term “cloud” means:

*“A model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (such as networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction.”*
— NIST SP 800-145

---
The NIST SP 800-145 Cloud Computing framework from **Characteristics**, **Service Models**, and **Deployment Models** and explore how they apply in practice.
### 1. The Power Grid Analogy
Just like plugging an appliance into a wall outlet without worrying about where the electric company built its power plant, **cloud computing** provides on-demand access to computing resources over the internet, charged on a pay-as-you-go basis.
### 2. The 5 Essential Characteristics
These five features define what makes a system a true "cloud" service:
- **On-demand Self-Service**: Users can automatically provision server time, storage, or network resources without needing manual intervention from the provider.
- **Broad Network Access**: Services are accessible over the network through standard platforms (laptops, mobile phones, workstations).
- **Resource Pooling**: The Cloud Service Provider (CSP) pools physical resources to serve multiple customers (**multi-tenancy**), dynamically assigning virtual resources as needed.
- **Rapid Elasticity**: Resources can instantly expand (scale up/out) or shrink (scale down/in) to handle spikes or drops in workload.
- **Measured Service**: Systems automatically track and meter resource usage (CPU time, storage consumed, bandwidth) for transparent billing.
### 3. The 3 Cloud Service Models
These models define **who controls what** in the shared responsibility model:
- **Infrastructure as a Service (IaaS)**: Provides raw building blocks like virtual machines, networks, and storage. You manage the operating system, middleware, and applications. _(Example: AWS EC2, Azure VMs)_
- **Platform as a Service (PaaS)**: Provides a pre-configured execution environment/runtime for developers. The CSP manages the underlying OS and hardware, while you only manage the application code and data. _(Example: AWS Elastic Beanstalk, Google App Engine)_
- **Software as a Service (SaaS)**: Delivers a complete, fully managed application to end-users over a web browser. You only manage your own data and basic settings. _(Example: Microsoft 365, Gmail, Salesforce)_
### 4. The 4 Cloud Deployment Models
These define **where** the infrastructure resides and **who** has access:
- **Public Cloud**: Owned by a third-party CSP and shared across multiple independent organizations.
- **Private Cloud**: Dedicated exclusively to a single organization (can be hosted on-premises or off-premises).
- **Community Cloud**: Shared by a specific group of organizations with common security, compliance, or regulatory requirements.
- **Hybrid Cloud**: Combines two or more distinct deployment models (e.g., Private + Public), connected by technology that allows data and applications to be shared.
## Managed Service Provider (MSP)
A managed service provider (MSP) is a company that manages information technology assets for another company. Small and medium-sized businesses commonly outsource part or all of their information technology functions to an MSP to manage day-to-day operations or to provide expertise in areas the company does not have. Organizations may also use an MSP to provide network and security monitoring and patching services.

Today, many MSPs offer cloud-based services augmenting SaaS solutions with active incident investigation and response activities. One such example is a managed detection and response (MDR) service, where a vendor monitors firewall and other security tools to provide expertise in triaging events.
#### Some other common MSP implementations are:
- Augment In-house staff for projects
- Utilize expertise for Implementation of a product or service
- Provide payroll services
- Provide Help Desk service management
- Monitor and respond to security incidents
- Manage all In-house IT Infrastructure

>- **Cloud Service Provider (CSP)**: A vendor (such as AWS or Microsoft Azure) that supplies scalable infrastructure, platforms, or software tools on a subscription basis. The client organization is typically responsible for configuring and managing security controls within that environment.
>  
>- **Managed Service Provider (MSP)**: A third-party partner that takes over operational responsibilities, such as 24/7 security monitoring, patching, help desk support, and IT administration.
>
>In short, a CSP provides the technical foundation and tools, while an MSP provides the hands-on operational management and expertise.

## Service Level Agreement (SLA)
A cloud service-level agreement (SLA) functions as a binding contract and rulebook between a Cloud Service Provider (CSP) and a customer, defining exact performance standards, security baselines, and legal remedies for non-compliance.

**Scenario**: An e-commerce company relies on a cloud database. Their SLA guarantees **99.99% uptime** and a strict **15-minute data recovery time** after an outage. If the CSP experiences extended downtime that breaches this threshold, the SLA dictates financial penalties or service credits. It also mandates where data is physically stored (**data location**) and how it will be returned if the contract is terminated (**exit strategy**).

***Other important SLA points to consider include the following:***
- Cloud system Infrastructure details and security standards
- Customer right to audit legal and regulatory compliance by the CSP
- Rights and costs associated with continuing and discontinuing service use
- Service availability
- Service performance
- Data security and privacy 
- Disaster recovery processes
- Data location
- Data access
- Data portability
- Problem identification and resolution expectations 
- Change management processes
- Dispute mediation processes
- Exit strategy
