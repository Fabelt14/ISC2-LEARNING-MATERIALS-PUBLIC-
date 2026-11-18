`Tags: #cybersecurity #cc #isc2 #control #privacy #Domain_Security`
## Security Controls?
Now, we are looking at the actual weapons and armor we use to fight those risks. When management says, "We want to Mitigate this risk," Security Controls are the exact tools you use to do it.
## What is a Security Control?
At its core, a **Security Control** is any safeguard or countermeasure designed to protect the **CIA Triad** (Confidentiality, Integrity, Availability) of an asset. The ultimate goal of any control is to reduce a risk down to a level that management is willing to accept.

**There are three main categories of controls. If you want to be a top-tier penetration tester, you need to know how to bypass all three.**
### 1. Physical Controls (The Tangible Walls)
These are tangible, real-world measures designed to protect IT infrastructure, data centers, and devices from unauthorized access, theft, or physical damage. They serve as the foundational first layer of security, ensuring no one can physically interact with your network or hardware.

This addresses security needs using physical Hardware devices, architectural features, and physical actions taken to control, direct, or prevent the physical movement of people and equipment. Basically anything you can touch with your hands or bump into with your body.

Examples: Concrete bollards outside a Victoria Island bank, security guards, perimeter fences, CCTV cameras, and turnstiles.

>Physical controls are often supported by Technical controls. 
>
>A physical ID badge is useless without the technical database verifying the identity behind the badge reader.

These controls are primarily categorized into three types based on their function:
#### 1. Preventive Controls
These are measures designed to stop physical threats or unauthorized entry before they happen. 
- **Physical barriers:** Fences, gates, and bollards.
- **Access control systems:** Keycards, biometric scanners (fingerprint, iris), and cryptographic smart locks.
- **Mantraps:** Small, secure entryways with two interlocking doors that prevent "tailgating" by only allowing one person in at a time.
- **Device locks:** Cable locks and secure hardware cabinets.
#### 2. Detective Controls
These are systems built to identify and record physical breaches or suspicious activity as or after they occur. 
- **Surveillance:** Closed-Circuit Television (CCTV) cameras and motion sensors.
- **Environmental monitoring:** Temperature, humidity, and water leak sensors in server rooms.
- **Alarms:** Intrusion detection systems that trigger alerts for unauthorized door openings or motion in restricted areas.
- **Access logs:** Digital or manual registries that track who enters specific rooms and when
#### 3. Deterrent Controls
These are visible measures designed to discourage or dissuade attackers from attempting a physical breach in the first place.
- **Signage:** Clear warnings about restricted areas, 24/7 video monitoring, or alarms.
- **Security personnel:** Visible presence of guards, patrols, or receptionists.
- **Lighting:** Adequate perimeter and facility illumination. 

>Why They Matter
>
>Even the strongest digital defenses, like firewalls and endpoint protection, can be bypassed if an attacker walks into your office and plugs a malicious USB into an unlocked server. Effective physical controls prevent the theft of hardware (which holds your data) and stop unauthorized individuals from tampering with your network infrastructure
### 2. Technical Controls (The Logical Walls)
**Technical controls** (often called **logical controls**) are the hardware, software, or firmware mechanisms implemented in an IT system to protect digital assets. They act as automated, digital safeguards like digital locks and alarms enforcing security policies and defending networks, devices, and data from unauthorized access or malicious threats.

They are automated protections implemented directly by computer systems, software, and networks to prevent unauthorized access or detect violations. _Note: The CC exam also calls these **Logical Controls**._ Basically the code and configurations that keep the bad guys out of the network.

Examples are: Firewalls, encryption algorithms, Access Control Lists (ACLs), and antivirus software. ***When you run an automated bash script to hunt for vulnerabilities, you are usually looking for systems where these Technical Controls are missing or misconfigured.*** These can be software (like a GUI setting) or hardware (like physical jumper switches on a motherboard).

These technology-based defenses are typically categorized into three distinct functions:
#### 1. Preventive Controls
These are designed to stop an attack or unauthorized access before it happens.
- **Firewalls:** Filter incoming and outgoing network traffic based on predefined security rules. 
- **Multi-Factor Authentication (MFA):** Requires multiple forms of verification (e.g., password plus a mobile code) to grant access to accounts.
- **Encryption:** Secures data (both in transit and at rest) so it remains unreadable to unauthorized parties. 
- **Access Controls (IAM):** Enforces rules (like Role-Based Access Control) to ensure users only have access to the data they need to perform their jobs.
#### 2. Detective Controls
These are designed to identify and alert security teams to an incident while it is happening or after it has occurred.
- **Intrusion Detection Systems (IDS):** Monitor network traffic for suspicious activity or policy violations.
- **Security Information and Event Management (SIEM):** Aggregate and analyze logs from various systems to flag potential security events.
- **Endpoint Detection and Response (EDR):** Continuously monitor devices (laptops, servers) for anomalous behavior or malware.
- **Vulnerability Scanners:** Run automated checks on systems to identify weaknesses before attackers do.
#### 3. Corrective Controls
These are implemented to mitigate the damage of an active attack, stop a threat from spreading, or restore systems to a normal state. 
- **Automated Patch Management:** Automatically updates software and firmware to fix known vulnerabilities.
- **Antivirus/Anti-malware:** Scans for and removes detected malicious software.
- **Automated Incident Response (SOAR):** Disconnects infected devices or revokes compromised credentials when triggered by an alert.

>Technical controls cannot operate in a vacuum; they rely on **administrative controls** (the rules and policies governing how technology is used) and **physical controls** (tangible barriers like locked server rooms) to form a robust, multi-layered cybersecurity strategy.

### 3. Administrative Controls (The Human Rules)
These are directives, guidelines, policies, and standards aimed at managing human behavior within the organization. _Note: The CC exam also calls these **Managerial Controls**._

They are the paperwork, rules, and training designed to stop employees from doing foolish things.

Examples are: Mandatory security awareness training, password length requirements written in a company handbook, and policies stating you cannot plug a random USB drive into your workstation.

>These controls shouldn't just sit in a CEO's desk. The best administrative controls are integrated into an employee's daily tasks, like a quick warning prompt before they send an email with an external attachment.
### The Cheat Sheet for Your Vault

|**Control Type**|**Alternate Name**|**What it secures**|**Example**|
|---|---|---|---|
|**Physical**|N/A|Tangible space and hardware.|A locked door to the server room.|
|**Technical**|Logical|Digital networks and data.|A firewall blocking unauthorized IP addresses.|
|**Administrative**|Managerial|Human behavior and processes.|A policy requiring annual security training.|
![[Pasted image 20260626170620.png]]
## Governance Elements
When leaders and management implement the systems and structures that the organization will use to achieve its goals, they are guided by laws and regulations created by governments to enact public policy. Laws and regulations guide the development of standards, which cultivate policies, which result in procedures.

![[Pasted image 20260626173911.png]]
### Regulations (Laws)
These are issued by governments and typically carry financial penalties for non-compliance. 

>The Nigerian government enforces the **Nigeria Data Protection Act (NDPA)**. The law explicitly states: _"Financial institutions must secure citizen financial data from unauthorized access."_ If the company ignores this and gets hacked, the government fines them ₦10,000,000.

Because regulations and laws can be imposed and enforced differently in different parts of the world, here are a few examples to connect the concepts to actual regulations:
- **HIPAA (Health Insurance Portability and Accountability Act of 1996):** This law governs the use of protected health information (PHI) in the United States. Violating HIPAA carries the possibility of fines and/or imprisonment for both individuals and companies.
- **GDPR (General Data Protection Regulation):** Enacted by the European Union (EU) to control the use of Personally Identifiable Information (PII). It includes provisions that apply financial penalties to companies worldwide handling EU data, giving this regulation an international reach even if the company has no physical presence in the EU.

>*Because organizations are often subject to regulations in more than one nation, region, or municipality, they need to ensure they are compliant with the most restrictive regulation.*
>
>If Lagos requires 128-bit encryption by law, but the EU GDPR standard you also have to follow demands 256-bit encryption, you must use 256-bit across the board. You always build to the strictest standard.
### Standards 
These are often used by ***governance teams*** to provide a framework to introduce policies and procedures in support of regulations.

It is the framework or "best practices" the company adopts to figure out _how_ to obey the law.
- **The Scenario:** The executives read the NDPA law, but the law doesn't tell them _which_ firewall to buy. So, they look at the **NIST (National Institute of Standards and Technology)** guidelines. NIST says, _"To secure data properly, you should use Multi-Factor Authentication (MFA) and 256-bit encryption."_
- **The Consequence:** Standards are usually voluntary recommendations (unless written into a contract). You don't go to jail for ignoring NIST, but following NIST proves to the government that you are trying to obey the law.

Standards cover a broad range of issues and ideas and may provide assurance that an organization is operating with policies and procedures that support regulations and widely accepted best practices.
- **ISO (International Organization for Standardization):** This organization develops international standards on technical subjects, including information security and encryption. Documents outlining ISO standards may be purchased online.
- **NIST (National Institute of Standards and Technology):** This is a United States government agency under the Department of Commerce. It publishes information security standards that are free to download and are considered recommended standards by industries worldwide.
Finally, think about how computers talk to other computers across the globe. People speak different languages and do not always understand each other. How are computers able to communicate? Through standards, of course! and they are:
- **IETF (Internet Engineering Task Force):** This body sets standards in communication protocols that ensure all computers can connect with each other across borders.
- **IEEE (Institute of Electrical and Electronics Engineers):** This institute sets standards for telecommunications and computer engineering.
### Policies
These are put in place by organizational governance, such as executive management, to provide guidance and set out strategic direction. They are broad, not detailed, and ensure the organization supports industry standards and regulations.

This is the internal rule written by the company's executives to enforce the Standard. It is broad and applies to everyone.
    
- **The Scenario:** The CEO and CISO write the "Enterprise Access Policy." It states: _"All employees must use MFA to access the internal network. Passwords must be at least 16 characters long."_
- **The Consequence:** You don't go to jail for breaking a company policy, but you **will get fired**.

Policy is informed by applicable law(s) and specifies which standards and guidelines the organization will follow. Policy is broad but not detailed; it establishes context and sets out strategic direction and priorities. Governance policies are used to moderate and control decision-making, to ensure compliance when necessary, and to guide the creation and implementation of other policies.
### Procedures
These define the explicit, repeatable activities and step-by-step instructions necessary to accomplish a specific task. They also establish the measurement criteria to determine whether a task has been successfully completed.

This is the actual, click-by-click manual on how the employee is supposed to follow the Policy.
    
- **The Scenario:** You get hired as a junior SOC analyst. On your first day, your manager hands you a wiki page titled "Procedure: VPN Login." It reads:
    
    - _Step 1: Open the Cisco AnyConnect application._
        
    - _Step 2: Type in your 16-character password._
        
    - _Step 3: Open the Microsoft Authenticator app on your phone._
        
    - _Step 4: Type the 6-digit code into the VPN prompt and click 'Connect'._
        
- **The Consequence:** If you mess up a procedure, a task simply fails or you get an error message. You go back to step 1 and try again.
## The Four Canons (The "What")
You need to know these four Canons by heart, but more importantly, **you need to know them in exact order.**

|**Canon Order**|**The Official Canon**|**The Plain-English Meaning**|
|---|---|---|
|**Canon 1**|Protect society, the common good, necessary public trust and confidence, and the infrastructure.|**Human Life & Society First.** You never do anything that puts human life, public safety, or national infrastructure at risk.|
|**Canon 2**|Act honorably, honestly, justly, responsibly, and legally.|**Don't Break the Law.** You don't lie on your reports, you don't steal data, and you don't do illegal things.|
|**Canon 3**|Provide diligent and competent service to principals.|**Do Your Job Well.** You give your boss or your client 100% effort. You keep their secrets (confidentiality) and you deliver high-quality work.|
|**Canon 4**|Advance and protect the profession.|**Don't Be a Gatekeeper.** You mentor juniors, you don't associate with black-hat hackers, and you protect the reputation of the cybersecurity industry.|

## The Ultimate CC Exam Secret: The Hierarchy of Canons

Here is the trick ISC2 uses to fail people on the ethics questions: **The Canons are written in order of absolute priority.** If two Canons conflict in the real world, the lower number _always_ wins.

- **Scenario A:** Your boss (Canon 3) orders you to illegally hack a competitor's database (Canon 2).
    
    - _The Result:_ Canon 2 > Canon 3. You must refuse the order. You cannot break the law just to serve your principal.
        
- **Scenario B:** You are doing a penetration test for a client (Canon 3). You sign an NDA saying you will keep everything secret. During the test, you find out they are actively dumping toxic waste into the Lagos water supply, putting thousands of lives at risk (Canon 1).
    
    - _The Result:_ Canon 1 > Canon 3. Human life and society override your client's NDA. You blow the whistle and report them to the authorities.
        
