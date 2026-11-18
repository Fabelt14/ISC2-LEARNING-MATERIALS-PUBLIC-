## Data Handling  
Data goes through its own life cycle as users ***create, utilize, share, and modify*** it. Many different models of the life of a data item can be found, but they all have some basic operational steps in common.

*The Data Security Life Cycle defines the operational stages a data item traverses from its inception to its final disposal. This model aligns security controls with organizational roles and maps directly to the three core data states: **data at rest, data in use,** and **data in motion.***

Here is the technical breakdown of the six phases, mapped to a practical Nigerian banking sector scenario (such as a commercial bank operating in Victoria Island, Lagos):

### 1. Create
- **Technical Definition**: The initial generation of data or knowledge, which typically begins as tacit knowledge (ideas or information held by individuals) before being captured digitally.
- **Nigerian Operational Scenario**: A customer walks into a bank branch in Lagos to open a corporate account. The customer service officer captures raw onboarding details, signature cards, and initial identification metrics into the intake form.
### 2. Store
- **Technical Definition**: Recording or persisting data in a structured repository, transforming it into explicit knowledge. This state primarily represents **data at rest**, requiring controls like full-disk encryption and database access permissions.
- **Nigerian Operational Scenario**: The bank records the customer's BVN, NIN, and account details into its core banking application database (such as Finacle or Temenos), which is housed in an enterprise data center located in Lagos.
### 3. Use
- **Technical Definition**: Active processing, viewing, modifying, supplementing, or partial deletion of data by applications or users. This represents **data in use**, requiring endpoint protection and strict authorization checks.
- **Nigerian Operational Scenario**: The bank's risk and compliance officers query the core database to run anti-money laundering (AML) checks, verify the customer's identity against the Nigeria Inter-Bank Settlement System (NIBSS), and update account limits.
### 4. Share
- **Technical Definition**: Distributing data to authorized internal users or external entities, either by duplication or transfer. This often involves **data in motion**, requiring secure transmission protocols like TLS/HTTPS and encrypted tunnels.
- **Nigerian Operational Scenario**: The bank transmits transaction logs and payment settlement files securely over encrypted API channels to payment switches and the Central Bank of Nigeria (CBN) for clearing.
### 5. Archive
- **Technical Definition**: Moving data that is no longer actively needed for daily operations into a secure, long-term storage tier for historical preservation and regulatory compliance.
- **Nigerian Operational Scenario**: In compliance with regulatory mandates requiring financial transaction records to be kept for specific periods, the bank migrates historical logs of accounts inactive for over five years from primary high-performance storage arrays to cold backup tapes or secure secondary cloud archives.
### 6. Destroy
- **Technical Definition**: Permanently and irrecoverably purging data from storage media when it has exceeded its retention schedule or legal usefulness.
- **Nigerian Operational Scenario**: Once the legal data retention period expires for temporary digital document scans of rejected loan applicants, the bank executes secure data sanitization (using cryptographic erasure or physical degaussing of storage drives) to ensure zero recovery.

## Data Handling Practices
Data has intrinsic value and must be managed through structured operational controls from its creation to its final disposal. 
>***Why?***
>
>We implement data handling practices to ensure sensitive information remains protected against unauthorized access and complies with regulatory requirements throughout its lifecycle

Based on the ISC2 curriculum shown in the slide, data handling relies on four core pillars: Classification, Labeling, Handling, and Destruction.
### 1. Classification
- **Technical Definition**: The process of evaluating and categorizing data based on its sensitivity, criticality, and value to the organization. Classification determines the level of security controls, access permissions, and regulatory compliance requirements needed.
- **Key Components**:
    - Identifies the impact of unauthorized disclosure, modification, or destruction.
    - Typically structured into tiers such as Public, Internal, Confidential, and Restricted (or Secret).
    - Dictates all subsequent handling and storage policies.
- **Nigerian Operational Scenario**: A commercial bank headquartered in Victoria Island, Lagos, classifies its data assets. ***Public data*** includes published annual financial reports on the bank website. ***Internal data*** covers standard operating procedures shared across bank branches. ***Confidential data*** includes customer Bank Verification Numbers (BVN) and National Identification Numbers (NIN). ***Restricted data*** includes master encryption keys and board-level merger and acquisition documents.
### 2. Labeling
- **Technical Definition**: The physical or electronic marking of data assets to explicitly communicate their classification level to users, systems, and security tools.
- **Key Components**:
    - Ensures humans and automated Data Loss Prevention (DLP) systems can immediately identify data sensitivity.
    - Applied via metadata tags, document headers and footers, visual watermarks, or physical colored folders for paper records.
    - Must be maintained whenever data is copied, modified, or shared.
- **Nigerian Operational Scenario**: When a compliance officer in an Abuja branch drafts a Suspicious Transaction Report (STR) meant for the Nigerian Financial Intelligence Unit (NFIU), the document is programmatically tagged with a ***"RESTRICTED - COMPLIANCE ONLY"*** header and metadata watermark. This prevents employees from casually forwarding it via personal email channels or saving it to unencrypted local storage.

>- ***Highly restricted:*** Compromise of data with this sensitivity label could possibly put the organization’s future existence at risk. Compromise could lead to substantial loss of life, injury, or property damage, and litigation and claims would follow. 
>- ***Moderately restricted:*** Compromise of data with this sensitivity label could lead to loss of temporary competitive advantage, loss of revenue or disruption of planned investments or activities.
>- ***Low sensitivity (sometimes called “internal use only”):*** Compromise of data with this sensitivity label could cause minor disruptions, delays, or impacts.
>- ***Unrestricted public data:*** As this data is already published, no harm can come from further dissemination or disclosure.

### 3. Retention
Data retention governs how long an organization is required or permitted to keep information before it must be securely destroyed. Data retention operates under specific operational rules, responsibilities, and risk management principles.
#### Core Principles of Data Retention
- **Retention Duration**: Information and data must be kept only as long as it remains beneficial, meaning no more and no less.
- **Governing Drivers**: Retention periods are established by industry standards, laws, and regulations. When external mandates are absent, organizations must define and implement an internal data retention policy.
- **Scope**: Policies apply equally to both hard copies (physical paper records) and electronic data. No data should be kept beyond its required or useful life.
#### Responsibilities of Security Professionals
- **Enforcing Destruction**: Security professionals must ensure data destruction occurs precisely when an asset reaches its retention limit.
- **Accurate Asset Inventory**: Security requires maintaining a precise inventory detailing asset locations, specific retention periods, and required destruction methods.
- **Periodic Reviews**: Organizations must regularly review retained records to reduce storage volume and ensure only necessary information is preserved.
#### Policy Objectives and Guarantees
A well-structured records retention policy must guarantee that:
- Personnel across the organization understand the different retention requirements for various data types.
- The organization appropriately documents retention requirements for every category of information.
- Systems, processes, and individuals adhere strictly to the required retention schedule, retaining data for the mandated time, but no longer.
#### Nigerian Operational Scenario
For a commercial bank operating in Lagos, customer account records and transaction logs must be retained for a mandatory period (typically 5 to 6 years) under Central Bank of Nigeria (CBN) regulations and the Nigeria Data Protection Act (NDPA). If the bank mistakenly applies a permanent retention policy to temporary customer inquiries or general operational logs, it violates data minimization principles, clogs its databases, and risks financial penalties from the Nigeria Data Protection Commission (NDPC) for retaining personal data longer than necessary.
### 4. Destruction
- **Technical Definition**: The secure, permanent, and irrecoverable elimination of data and its storage media when it has reached the end of its legal retention schedule or operational usefulness.
- **Key Components**:
    - Prevents data remanence (recovering residual data after deletion).
    - Utilizes methods appropriate to media type, such as ***[^1]degaussing*** magnetic drives, cryptographic erasure (crypto-shredding), or physical destruction (shredding hard drives and paper documents).
    - Must comply with regulatory frameworks like the Nigeria Data Protection Act (NDPA).
- **Nigerian Operational Scenario**: Under CBN regulations, customer account opening documentation and transaction records must be retained for a mandatory period (typically 5 to 6 years). Once this statutory period lapses, physical paper files are subjected to industrial cross-cut shredding by a certified third-party vendor in Lagos, while digital storage arrays undergo cryptographic wiping or physical degaussing to ensure zero recovery before equipment is retired.
## Common Security Policies
Every security policy implemented within an enterprise must directly support and align with all regulatory mandates, legal obligations, and contractual requirements. Policies act as the foundational governance framework that ensures operational procedures comply with external laws and business agreements.
### Data Handling Policy
The data handling policy establishes the operational rules for managing data based on its assigned sensitivity label. It mandates that information categorized under the same sensitivity tier must be protected using identical security controls and handling strategies across the entire organization. This ensures consistent protection from creation to destruction.

### Password Policy
A password policy is a foundational security document that defines expectations and requirements for both system configurations and user behavior regarding authentication.
#### Key Elements of a Password Policy
- **Expectations of Systems and Users**: Establishes clear behavioral and technical rules for how passwords are created, used, and managed across all enterprise platforms.
- **Senior Leadership Commitment**: Explicitly states executive management's backing and commitment to maintaining secure access controls and protecting organizational data assets.
- **Formulation Standards**: Details the technical criteria selected by the organization for password creation, such as minimum length requirements, character complexity rules (uppercase, lowercase, numbers, symbols), expiration timelines, and restrictions on dictionary words or previously used passwords.
- **Enforcement and Validation**: Designates specific roles, teams, or automated tools responsible for enforcing compliance with the policy and validating that systems adhere to the required security baselines.
### Acceptable Use Policy (AUP)
The AUP defines the boundaries and rules governing how employees use company-owned hardware, software, and network resources.
***An effective AUP specifically governs:***
- **Data Access**: Who is permitted to view or modify specific datasets.
- **Application Use**: Authorized software allowed on corporate systems.  
- **Data Sharing**: Rules for transmitting information internally and externally.
- **Purchasing**: Protocol for acquiring IT assets and software licenses.
- **Physical Security**: Employee responsibilities for safeguarding physical work areas and equipment.
- **Internet Usage**: Permissible web browsing and traffic constraints.
- **Remote Software**: Guidelines for tools used outside the corporate perimeter.
### Bring Your Own Device (BYOD) Policy
A BYOD policy governs the security requirements when employees use personal smartphones, tablets, or laptops to access corporate networks and data.

It balances the operational convenience of mobile productivity with enterprise risk by enforcing technical controls such as Mobile Device Management (MDM), containerization (separating personal and corporate data), and remote wipe capabilities to protect company resources if a device is lost or compromised.
### Privacy Policy
The privacy policy communicates to customers and users how the organization collects, processes, stores, and protects personally identifiable information (PII).

It operationalizes compliance with privacy laws (such as the Nigeria Data Protection Act or GDPR) by detailing user consent mechanisms, data collection scope, transparency rights, and legal recourse for data subjects.
### Change Management Policy
The change management policy dictates how modifications to IT systems, network configurations, and software code are requested, evaluated, tested, approved, and documented.

It ensures that no unvoted or untested alterations are introduced into production environments, thereby preventing unexpected system outages, configuration drift, and security vulnerabilities.

>Imagine _PayBeta_ operating in Ikeja:
>
>1. Their entire policy framework is built to satisfy Central Bank of Nigeria regulations (**Overarching Rule**).
>
>2. Customer database records are encrypted following their **Data Handling Policy**.
>
>3. Employees follow the **AUP** when using office laptops: they have strict **data access** limits, use approved **application use** tools, secure their **data sharing**, go through IT for software **purchasing**, maintain office **physical security**, follow safe **internet usage** rules, and use corporate **remote software** safely.
>
>4. When customer support agents use their personal phones to check internal schedules, a **BYOD Policy** keeps company data separate and secure.
>
>5. Customers logging into the mobile app check the **Privacy Policy** to see how their personal information is legally guarded.
>
>6. When engineers want to update the live payment server, they follow the **Change Management Policy** to test the update first, preventing system downtime.


























[^1]: Degaussing is _a method of permanently erasing data_ from working and non-working hard drives, tape, and floppy disks.
	
	Degaussing is ==the process of reducing or eliminating a remnant magnetic field in an object or material==. It works by exposing the material to a fluctuating or alternating magnetic field that scrambles and randomizes its magnetic domains.
