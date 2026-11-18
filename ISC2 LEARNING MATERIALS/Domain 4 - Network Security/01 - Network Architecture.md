## What is Networking
A network is simply two or more computers linked together to share data, information or resources.
## Types of Networks
There are two basic types of networks:
- ***Local area network (LAN):*** A local area network (LAN) is a network typically spanning a single floor or building. This is commonly a limited geographical area.
- ***Wide area network (WAN):*** Wide area network (WAN) is the term usually assigned to the long-distance connections between geographically remote networks.
## Network Devices
- ***Hubs:*** Hubs are used to connect multiple devices in a network. They're less likely to be seen in business or corporate networks than in home networks. Hubs are wired devices and are not as smart as switches or routers. _A hub is a basic wired device that connects multiple computers, but it lacks intelligence and retransmits traffic to all devices._
- ***Switch:*** Rather than using a hub, you might consider using a switch, or what is also known as an **intelligent hub**. Switches are wired devices that know the addresses of the devices connected to them and route traffic to that port/device rather than retransmitting to all devices. Offering greater efficiency for traffic delivery and improving the overall throughput of data, switches are smarter than hubs, but not as smart as routers. *Switches can also create separate broadcast domains when used to create VLANs.*
- ***Firewall:*** Firewalls are essential tools in managing and controlling network traffic and protecting the network. A firewall is a network device used to filter traffic. It is typically deployed between a private network and the internet, but it can also be deployed between **departments (segmented networks)** within an organization (overall network). _Firewalls filter traffic based on a defined set of rules, also called filters or access control lists._
- ***Server:*** A server is a computer that provides information to other computers on a network. Some common servers are **web servers, email servers, print servers, database servers, and file servers.** All of these are, by design, networked and accessed in some way by a client computer. _Servers are usually secured differently than workstations to protect the information they contain._
- ***Router:*** Routers are used to control traffic flow on networks and are often used to connect similar networks and control traffic flow between them. Routers can be wired or wireless and can connect multiple switches. Smarter than hubs and switches, routers determine the most efficient "route" for the traffic to flow across the network.
- ***Endpoint:*** Endpoints are the ends of a network communication link. One end is often at a server where a resource resides, and the other end is often a client making a request to use a network resource. An endpoint can be another server, desktop workstation, laptop, tablet, mobile phone, or any other end user device.
## Other Networking Terms
- ***Ethernet:*** Ethernet (IEEE 802.3) is a standard that defines wired connections of networked devices. This standard defines the way data is formatted over the wire to ensure disparate devices can communicate over the same cables.
### Device Address
- ***Media Access Control (MAC) Address:*** Every network device is assigned a Media Access Control (MAC) address. An example is *00-13-02-1F-58-F5*. **The first 3 bytes (24 bits) of the address denote the vendor or manufacturer of the physical network interface.** No two devices can have the same MAC address in the same local network; otherwise an address conflict occurs. 
- ***Internet Protocol (IP) Address:*** While MAC addresses are generally assigned in the firmware of the interface, IP hosts associate that address with a unique logical address. This logical IP address represents the network interface within the network and can be useful to maintain communications when a physical device is swapped with new hardware. Examples are *192.168.1.1* and *2001:db8::ffff:0:1.*
## Summary
At its core, ***networking*** is simply linking two or more computers to share data and resources. The scale of this connection determines the network type. A ***Local Area Network (LAN)*** connects devices within a limited geographical area, such as a single floor or building. When you need to connect geographically remote networks across long distances, you use a ***Wide Area Network (WAN).***

To make these networks function, we rely on specific hardware. Communication typically starts and ends at ***endpoints***, which can be anything from a desktop workstation to a mobile phone. Often, these endpoints request resources from a server. A ***server*** is a specialized, secured computer designed to provide information, like web pages or files, to other computers on the network.

To connect these endpoints together, you have a few options. A ***hub*** is a basic wired device that connects multiple computers, but it lacks intelligence and retransmits traffic to all devices. A ***switch***, sometimes called an intelligent hub, is much more efficient because it knows the physical addresses of connected devices and routes traffic only to the specific intended port. If you need to connect entirely different networks together and determine the most efficient path for traffic to flow across them, you would use a ***router***. Finally, to protect all this traffic, a ***firewall*** is deployed to filter data based on defined rules or access control lists, often sitting between a private network and the public internet.

Devices also need standard rules and addresses to communicate. ***Ethernet*** is the IEEE standard that defines how data is formatted over wired connections. To identify devices on these wires, two types of addresses are used. The ***Media Access Control (MAC)*** address is the physical address assigned to the network interface by the manufacturer, and no two devices on a local network can share one. However, to maintain communication even if hardware is swapped, systems use an ***Internet Protocol (IP)*** address. The IP acts as a logical address that represents the interface on the broader network.

>A switch connects individual devices within the _same local network_, while a router is generally used to connect completely _different_ networks together (like connecting your office LAN to the internet).

>- 📥 **Ingress Traffic:** Data flowing **into** your private network from the outside (inbound).
>- 📤 **Egress Traffic:** Data flowing **out** of your private network to the outside (outbound).

## Networking at a Glance
### A Small Business Network
This diagram represents a small business network. The lines depict wired connections. Notice how all devices behind the firewall connect via the network switch, and the firewall lies between the network switch and the internet

![[Pasted image 20260830231945.png]]

### A Typical Home Network
The network diagram below represents a typical home network. Notice the primary difference between the home network and the business network is that the router, firewall, and network switch are often combined into one device supplied by your internet provider and shown here as the wireless access point.

![[Pasted image 20260830232330.png]]

## WI-FI
Wireless networking is a popular method of connecting corporate and home systems because of the ease of deployment and relatively low cost.

It has made networking more versatile than ever before. Workstations and portable systems are no longer tied to a cable but can roam freely within the signal range of the deployed wireless access points. 

However, with this freedom comes additional vulnerabilities. Wi-Fi range is generally wide enough for most homes or small offices, and range extenders may be placed strategically to extend the signal for larger campuses or homes. Over time the Wi-Fi standard has evolved, with each updated version faster than the last.

In a LAN, threat actors need to enter the physical space or immediate vicinity of the physical media itself. For wired networks, this can be done by placing sniffer taps onto cables, plugging in USB devices, or using other tools that require physical access to the network. ***By contrast, wireless media intrusions can happen at a distance.***

>While range extenders and higher-power WAPs expand coverage for legitimate employees, they simultaneously enlarge the physical area where an attacker can interact with the network.

## Network Design  
The objective of network design is to *satisfy data communication requirements* and achieve the result of *efficient overall performance*.

Network design is the strategic planning and structural layout of an organization’s communication infrastructure. It dictates how hardware devices, data paths, routing protocols, and security controls interact to ensure data moves reliably, efficiently, and securely.

### Network Segmentation
Network segmentation involves controlling traffic among networked devices. Complete or physical network segmentation occurs when a network is isolated from all outside communications, so transactions can only occur between devices within the segmented network.

Network segmentation is the practice of dividing a computer network into smaller, isolated sections called ***subnets*** or ***zones***. In a traditional flat network, every computer, printer, and server is connected to the same open digital space. If an attacker breaches one weak endpoint, such as an employee's infected laptop, they can freely wander across the entire network to find sensitive databases. *Network segmentation builds internal walls and checkpoint gates so that traffic between different sections is strictly restricted.*

To make this practical, picture a growing fintech company operating in Yaba, Lagos, that runs a mobile banking app and customer support portal. 

In a non-segmented network, if a hacker compromises an office guest Wi-Fi router used by visitors, they could slide straight into the backend database containing customer account balances and verification data.

By implementing network segmentation, the company divides its infrastructure into distinct security zones using tools like *Virtual Local Area Networks* and *internal firewalls*:
- ***Employee Workstation Zone:*** Used by staff for daily administrative and operational tasks.
- ***Guest Wi-Fi Zone:*** Isolated strictly for visitors and personal devices, completely blocked from accessing internal company systems.
- ***Production Database Zone:*** Houses high-value financial records and customer data, locked down tightly so that only authorized application servers can access it.

*Important concepts and topics you should know regarding network segmentation include:*
- **Lateral Movement:** This is the technique attackers use to move step-by-step from an initial entry point to high-value targets. Effective segmentation stops lateral movement by creating [^1]default-deny barriers between zones.
- **Blast Radius:** This refers to the scope of damage or compromise during a security incident. When a network is segmented, a breach in one zone remains trapped there, minimizing the overall impact on the rest of the business.
- **VLANs and Subnets:** VLANs use software tagging on managed switches to create logical broadcast domains without needing separate physical hardware for every department. Subnets divide IP address ranges at Layer 3. Together, they form the foundation of logical separation.
- **Access Control Lists and Internal Firewalls:** Because segmentation alone only draws the boundary lines, firewalls and access control lists act as the security guards at the gates. They inspect packets and enforce explicit rules stating which specific traffic is allowed to cross into another zone.
![[Pasted image 20261015001349.png]]

### Demilitarized Zone (DMZ)
A DMZ is a network area that is designed to be accessed by outside visitors but is still isolated from the private network of the organization. The DMZ is often the host of public web, email, file and other resource servers.

A Demilitarized Zone, commonly known as a DMZ, is a separate subnetwork that sits between an organization's secure internal network and an untrusted external network like the internet. Think of it as a physical or logical buffer zone where you place services that need to be accessed by the public, while keeping your core internal databases and sensitive files completely hidden and safe behind an internal firewall.

>To make this practical, imagine a commercial bank in Victoria Island, Lagos, running a mobile banking web portal for customers across Nigeria. The bank must allow outside users on the internet to access the web portal so customers can check balances and transfer funds. However, the bank cannot expose its main customer account database directly to the internet because hackers could easily steal sensitive financial records.

To solve this, the bank sets up a DMZ architecture using the following structure:

- **Public-Facing Web Server:** This server is placed inside the DMZ. External users from the internet can access this server to use the banking application, but the server itself has no direct connection to internal corporate assets.
- **Internal Network:** This area contains the sensitive core banking database, customer financial records, and employee workstations. This zone is locked down tightly behind an internal firewall.
- **Firewalls as Security Gates:** Firewalls control the traffic flow. An external firewall checks traffic coming from the internet before it enters the DMZ, and an internal firewall strictly blocks traffic from moving directly from the DMZ into the secure internal network.

If an attacker manages to exploit a vulnerability and compromise the public web server in the DMZ, they remain trapped inside that buffer zone. They cannot jump straight into the core database because the internal firewall blocks their path. This containment strategy limits the ***blast radius*** of the attack and gives the security operations team time to detect and stop the intrusion before sensitive data is exposed.

>The web server in the DMZ does not hold the permanent database records, but it acts as an authorized bridge between the customer and the secure internal network.
>
>To see how this works, let us trace a request using a mobile banking app in Lagos.
>
>When a customer opens the app and requests their account balance, the process flows through specific steps:
>
>1. The customer sends a request from their phone over the internet. This request hits the ***external firewall***, passes through, and reaches the public facing web server sitting inside the DMZ.
>2. The web server receives the request. It checks if the customer is logged in, but it realizes it does not have the actual account balance stored locally.
>3. The web server needs to fetch that data, so it sends a specific database query toward the core database.
>4. This is where the internal firewall comes in. The internal firewall is not a complete dead end for all traffic. Instead, it is configured with strict rules. It recognizes that the request is coming from the trusted IP address of the authorized web server in the DMZ, and it permits that specific database query to pass through to the core database.
>5. The core database processes the query, finds the balance, and sends the response back to the web server in the DMZ.
>6. Finally, the web server formats that data into a clean page and sends the response back through the external firewall to the customer's phone.
>   
>*The web server never permanently stores the sensitive data, and the core database never directly talks to the public internet.*

*A Demilitarized Zone (DMZ) and a Web Application Firewall (WAF) are not the same, and neither has replaced the other. They operate at entirely different layers of network design and security.*
- **DMZ (Network Architecture 🌐):** This is a structural network design pattern. It creates an isolated buffer subnetwork between the untrusted public internet and your trusted internal network, ensuring public-facing services are kept separate from core assets.
- **WAF (Security Control 🛡️):** This is a specialized, application-layer defense tool. It specifically filters, monitors, and blocks HTTP/HTTPS traffic to protect web applications against Layer 7 threats like SQL injection and cross-site scripting (XSS).
Rather than competing, they work together: a WAF is frequently deployed as part of the security stack to protect web servers that reside within a DMZ.

![[Pasted image 20261015003850.png]]

## Virtual Local Area Network (VLAN)
VLANs are created by switches to logically segment a network without altering its physical topology.

A Virtual Local Area Network, or VLAN, is a logical subdivision of a computer network. In a traditional physical network, all computers plugged into the same network switch share a single broadcast domain and can talk to each other directly. A VLAN uses software configuration on managed switches to divide that physical network into multiple isolated virtual networks. *Devices on different VLANs cannot communicate with each other unless traffic is deliberately routed through a router or firewall, even if the devices are plugged into the exact same physical switch.*

>To make this practical, picture a growing logistics company office in Kano. The administrative staff, the delivery drivers using office tablets, and the finance department all connect to network ports on the same physical switches in the server room. Without VLANs, everyone shares the same open network space. By setting up VLANs, the finance department is placed on VLAN 20, completely hidden from the tablet network used by the delivery drivers on VLAN 30, which saves the company from buying separate physical networking hardware for every department.

***IEEE 802.1Q is the official networking standard used for VLAN tagging.***

To clear up the naming confusion, you are completely right about the others. IEEE 802.3 is the standard for wired Ethernet, and 802.11 is the standard for wireless Wi-Fi. In that same family, IEEE 802.1Q is the universal rulebook for how network switches stamp and identify VLAN traffic when it travels between different switches.
### How VLANs Work and the Tools You Use
To answer your question about Cisco Packet Tracer and command line interfaces, yes, you configure VLANs directly on the switch console.

When you open Cisco Packet Tracer, you log into the switch command line interface and use specific configuration commands to create VLANs and assign physical switch ports to them. For example, you tell the switch that ports one through ten belong to the finance VLAN, while ports eleven through twenty belong to the guest Wi-Fi VLAN.

### 1. IEEE 802.1Q Tagging and Trunk Ports
Imagine an enterprise office in Abuja with two floors, and each floor has a network switch. You have employees in the HR department on both floors who need to be on the same VLAN 10, and finance employees on both floors who need to be on VLAN 20.

You need a single physical cable connecting the switch on the first floor to the switch on the second floor. That single physical cable has to carry data for both VLAN 10 and VLAN 20 simultaneously.

This is where IEEE 802.1Q comes in. When a switch sends a data frame across that shared cable (called a trunk link), it injects a small 4-byte tag right into the middle of the standard Ethernet frame. This tag acts like a colored shipping label that says "this package belongs to VLAN 10". When the switch on the other end receives the frame, it reads the 802.1Q tag, strips it off, and forwards the data only to ports assigned to VLAN 10.

>The IEEE 802.1Q tagging mechanism operates strictly at **Layer 2 (the Data Link Layer)** of the OSI model.
>
>To clear up a quick detail about your note on addresses: **MAC addresses** belong to Layer 2 (Data Link Layer), while **IP addresses** belong to Layer 3 (Network Layer). Because 802.1Q inserts its 4-byte tag directly into the ***Ethernet frame header***—right between the source MAC address and the EtherType field—it lives entirely at Layer 2.
>
>***Where and When the Tag is Stripped***
>
>The switch handles the adding and stripping of this tag depending on the type of port the traffic is moving through:
>1. **On Trunk Links (Switch-to-Switch)**: When frames travel between two switches across a trunk link, they carry the 4-byte 802.1Q tag so both switches know which VLAN the traffic belongs to.
>2. **On Access Ports (Switch-to-Device)**: When a switch receives a tagged frame and prepares to send it out to an ordinary end device (such as a laptop, IP phone, or printer) connected to an access port, the switch **strips the 4-byte tag completely off**.
>  
>End devices operate at Layer 2 and expect standard, untagged Ethernet frames. They have no concept of 802.1Q tags. The switch strips the tag at the final egress port so the receiving device can process the standard Ethernet frame normally.
### 2. Inter-VLAN Routing
By design, devices on VLAN 10 cannot talk to devices on VLAN 20. They are isolated into separate logical broadcast domains for security and performance.

However, what happens when an HR employee on VLAN 10 genuinely needs to access a shared file server sitting on VLAN 20? Because they are on different VLANs, a normal switch cannot pass traffic directly between them.

To allow this communication safely, you need a router or a Layer 3 switch. This device acts as a traffic officer between the two VLANs. When traffic wants to move from VLAN 10 to VLAN 20, it must leave the switch, go through the router or Layer 3 firewall, and get explicitly inspected before it is allowed onto the destination VLAN. This allows administrators to place security rules at the routing level so only authorized traffic crosses the boundary.
### 3. VLAN Security Risks and VLAN Hopping
Because VLANs rely entirely on software tags and switch configurations, misconfigurations can lead to security vulnerabilities known as VLAN hopping.

An attacker tries VLAN hopping to jump from a low-security network segment (such as a guest Wi-Fi VLAN) into a restricted internal network segment (such as a server VLAN) without passing through a firewall or router.

The two main types of VLAN hopping attacks are:
- ***Switch Spoofing:*** An attacker configures their malicious computer to pretend to be a network switch, tricking a legitimate switch into forming an unauthorized trunk link. Once a trunk link is established, the attacker can see traffic from all VLANs.
- ***Double Tagging:*** An attacker crafts a packet with two 802.1Q tags. When the first switch processes and removes the outer tag, it forwards the packet across a trunk link, revealing the hidden inner tag that dumps the packet straight onto a restricted target VLAN.

*To prevent these attacks, network engineers follow hardening best practices:*

- Disable unused switch ports so unauthorized devices cannot plug into them.
- Turn off dynamic trunking protocols (DTP) on ports that connect to regular user workstations so switches do not automatically form trunk links with untrusted devices.
- Explicitly set ports as either access ports or static trunk ports rather than leaving them in default plug-and-play modes.

## Defense in Depth
Defense in depth is an information security strategy that uses ***multiple layers*** of security controls across a system. Instead of relying on a single security barrier, defense in depth builds overlapping lines of defense. If an attacker breaches one control, subsequent layers are still there to block them, detect the intrusion, or limit the damage.

>To make this practical, picture securing a modern corporate office building in Ikeja, Lagos. You do not rely solely on locking the front door of your individual office. Instead, you secure the property through multiple layers:

- The external perimeter has a high fence and a security gate where guards check visitor IDs.
- The building entrance requires an electronic key card and a metal detector. 
- Individual office doors have strong mechanical deadbolts.
- The server room inside the office requires biometric fingerprint access.

If a trespasser manages to slip past the main gate, they are still stopped at the building entrance. If they somehow get inside the building, they still cannot access the server room because of the biometric lock. That is how defense in depth works in digital security.
### The Core Layers of Defense in Depth
In an enterprise information technology environment, security professionals apply defense in depth across distinct layers. If an attacker bypasses one layer, the next layer catches them:
- **Physical Security**: Protecting the actual hardware, data centers, and server rooms using fences, security guards, biometric locks, and surveillance cameras.
- **Perimeter Security**: Protecting the network boundary where it meets the outside world using external firewalls and Demilitarized Zones (DMZs) to block malicious traffic before it reaches internal systems.
- **Network Security**: Controlling internal traffic flow using network segmentation, Virtual Local Area Networks (VLANs), and internal firewalls to stop lateral movement if an endpoint is compromised.
- **Host or Endpoint Security**: Securing individual devices like employee laptops and servers by installing antivirus software, keeping operating systems patched, and enforcing endpoint detection tools.
- **Application Security**: Writing secure software code, validating user inputs to prevent malicious uploads, and requiring proper authentication before letting users interact with data.
- **Data Security**: Protecting the actual information at rest and in transit using encryption, strict access permissions, and secure backup systems.
### Why Defense in Depth Matters
No single security control is one hundred percent effective. A firewall can have a misconfiguration, an employee can fall for a phishing email, or software can have an unknown vulnerability.

By combining physical, technical, and administrative controls, an organization ensures that an attacker cannot compromise the entire network with a single exploit. It forces an attacker to break through multiple independent barriers, which increases the time and effort required and gives the security operations team valuable time to detect and stop the threat.


>While people often use the terms interchangeably, there is a subtle difference in how security controls are planned and implemented:
>
>- **Layered Security** focuses on stacking multiple security controls linearly. For example, you place a firewall at the network edge, install antivirus software on an endpoint, and encrypt data at rest. If one layer fails, another independent layer is there, but the layers may use similar technologies or lack centralized coordination.
>- **Defense in Depth** is a comprehensive, strategic approach inspired by military defense. It deliberately uses diverse, independent, and redundant layers across different domains such as physical, technical, and administrative controls. The goal is not just stacking tools, but ensuring that controls complement each other so an attacker must bypass completely different types of barriers, such as biometric locks, network segmentation, and behavioral monitoring, to reach the target.

![[Pasted image 20261015205406.png]]

## Zero Trust
Zero Trust is an information security framework built on a single core principle: ***never trust, always verify.*** 

In traditional network security, organizations operated on a castle and moat model. Once a user, device, or application proved their identity at the outer perimeter or connected via a Virtual Private Network, they were largely trusted to move freely inside the network. Zero Trust rejects this assumption entirely. *It operates on the premise that threats already exist inside and outside the network, so every access request must be authenticated, authorized, and encrypted before access is granted.*

>To make this practical, picture a digital bank operating out of Victoria Island, Lagos, with employees working remotely from home, traveling across Nigeria, and accessing systems from various devices. In a traditional model, if an employee logs into the corporate VPN, their laptop is implicitly trusted. If an attacker steals that employee credentials, they can move laterally across the entire internal network. Under a Zero Trust architecture, simply being on the VPN grants zero access. Every single request requires continuous verification.

***Three foundational pillars drive a Zero Trust architecture:***

1. ***Verify explicitly:*** Always authenticate and authorize based on all available data points, including user identity, location, device health, service or workload, data classification, and anomalies. Nothing is trusted by default based solely on its network location.
2. ***Use least privilege access:*** Limit user access with *Just-In-Time* and *Just-Enough-Access models*, risk-based adaptive policies, and data protection. Users and devices only receive the minimum permissions necessary to perform their specific tasks, and those permissions expire when the task is complete.
3. ***Assume breach:*** Minimize blast radius by segmenting access by user, location, and device. Encrypt all sessions end to end, use analytics to gain visibility, drive threat detection, and continuously improve defenses. If an account or endpoint is compromised, the attacker cannot automatically pivot to other systems.

Zero Trust transforms security from a static perimeter defense into an adaptive, identity-centric strategy where trust is never permanent and must be earned with every transaction.


![[Zero Trust.png]]

The diagram is essentially a "Before and After" view. The easiest way to understand it is to look at how a user requests access under each model.
### 1. The Right Side: A True Zero Trust Architecture
This large, right-hand section details the "New Way" of securing systems. This is the implementation of the "***Verify Explicitly***" principle we discussed.
- **The Policy Engine (The Gatekeeper):** The big central block labeled "***ZERO TRUST POLICY ENGINE / ENFORCEMENT POINT***" is the brain of the whole operation. It trusts nothing by default. Everything must pass through here.
- **Contextual Inputs (The 'Check'):** Look at the multi-colored arrows on the left pointing _into_ the Policy Engine. The diagram shows that to grant access, the engine considers diverse factors simultaneously, not just an IP address:
    - **User Identity (MFA):** "Is this actually the employee?"
    - **Device Health:** "Is this laptop secure, patched, and managed?"
    - **Context/Location (Lagos, Remote IP):** "Where are they connecting from?" (This is where the Nigeria context comes in).
    - **Behavioral Analytics:** "Is this access request typical for this user?"
- **Micro-Segmented Access (Least Privilege):** Now, look at the connections pointing _out of_ the Policy Engine on the far right. Look at the isolated columns (A-D) labeled "Segments."
    - Notice that after the user is verified, the engine does not just "let them in." Instead, it assigns them _specific_, encrypted access _only_ to the resource they need at that moment, such as the "Database (Strict Authorization only)" in Segment C, rather than access to the entire network. This is Least Privilege access in action.
- **Visualizing "Assume Breach":** The small graphic in the center showing a connection between a local "Workstation" and an "Internal Database" marked with a red 'X' and labeled "***LATERAL MOVEMENT BLOCKED***" is a direct visualization of the "Assume Breach" principle. Even if an attacker compromises a single workstation, they cannot easily pivot to the database because those resources are micro-segmented and isolated from each other. Every connection, internal or external, requires verification from the policy engine.
### 2. The Left Side: A Traditional Model (Castle-and-Moat)
This smaller section is included to show the historical approach, which helps highlight why Zero Trust is different.
- **Castle Metaphor:** It uses a literal castle diagram with "Implicit Trust Zones." This represents an "all-or-nothing" security model.
- **Once Inside, You are Trusted:** Notice that if a threat passes through the main firewall (over the moat and into the castle), it has full access to the "User Workstations," "Internal Servers," and "DB." There are no internal barriers. This contrast makes the micro-segmentation shown on the Zero Trust side clearly visible.
### 3. Nigerian Contextual Reference
The inclusion of the maps and specific locations like Lagos and Abuja acts as a practical anchor. It provides context for how a regional fintech company might implement Zero Trust to secure remote workers logging in from different cities (the "context" arrow), contrasting this dynamic trust against the old method of "implicit trust on location." The "VS" comparison graphic below directly highlights this shift using map graphics, showing "Implicit Trust on Location" (Old) vs "Dynamic Trust on Context" (New).

In a nutshell, the image depicts a comprehensive framework that transforms network security from a single static perimeter (left) to an adaptive, continuous authentication and authorization engine that micro-segments access to individual resources (right), using diverse contextual data points (the colored input arrows).

>***When it comes to how this is implemented in the real world:***
>
>- 🏢 **Not a Single Physical Box:** Unlike traditional hardware firewalls, a Zero Trust Policy Engine is typically a software-driven ecosystem, cloud service, or identity platform (such as Microsoft Entra ID, Okta, or Palo Alto Prisma) rather than a single appliance you plug into a server rack.
>- 💻 **Configuration over Custom Code:** Organizations rarely write a policy engine from scratch using raw code. Instead, they leverage existing enterprise platforms and write custom _access policies_ and _conditional access rules_ that reflect their specific workflows.
>- ⚙️ **Customization:** Every organization does indeed have a different set of rules because policies are tailored to their specific applications, risk tolerance, and regulatory requirements (such as data protection or central bank guidelines).

## Network Access Control (NAC)
An organization’s network is perhaps one of its most critical assets. As such, it is vital that you both know and control access to it, both from insiders (e.g., employees, contractors) and outsiders (e.g., customers, corporate partners, vendors). You must see who and what is attempting to make a network connection.

Network Access Control (NAC) is a security solution that enforces compliance and security policies on all devices attempting to connect to a corporate network. Instead of trusting a device simply because it has a valid network cable or Wi-Fi password, NAC examines the device's security posture such as checking if the operating system is updated, if antivirus software is active, and whether it belongs to an authorized user before granting access.

Let's dive deeper into the technical mechanics of Network Access Control (NAC) and how each component operates in an enterprise environment.
### 1. Posture Assessment and Compliance
Before any device is permitted onto the network, the NAC system runs agent-based or agentless checks to evaluate its security posture. Key checks include:
- **Operating System & Patch Level:** Verifying that critical OS updates and security patches are installed to prevent exploitation of known vulnerabilities.
- **Endpoint Protection:** Ensuring commercial antivirus or EDR (Endpoint Detection and Response) software is installed, active, and running up-to-date signature definitions.
- **Disk Encryption:** Checking if full-disk encryption (such as BitLocker or FileVault) is enabled to protect data if the device is physically stolen.
### 2. Pre-Admission vs. Post-Admission Control
NAC operates across two distinct phases of a device's network lifecycle:
- **Pre-Admission Control:** The initial gatekeeping phase. The device is held in a restricted state while authentication and health checks take place. Access is either granted, denied, or sent to quarantine before the device touches any core infrastructure.
- **Post-Admission Control:** Continuous monitoring _after_ the device joins the network. If a compliant laptop is later infected with malware or starts scanning other internal subnets, post-admission policies (integrated with firewalls or SIEM tools) can instantly revoke its access or re-isolate it.
### 3. Enforcement and Quarantine Mechanisms
When a device fails compliance checks, the NAC system routes it using automated enforcement techniques:
- **Quarantine VLAN / Remediation Network:** The device is moved to an isolated network segment with restricted internet access, specifically limited to patch servers or IT helpdesk portals so the user can fix the issue.
- **Captive Portal:** The user is redirected to a web page explaining why access was denied (e.g., "Your antivirus definitions are out of date") with instructions on how to remediate.
- **802.1X Port-Based Authentication:** Switches and wireless controllers dynamically apply port security policies to block unauthorized traffic at the physical or link layer.
### 4. Deployment Use Cases
***NAC is deployed across several critical scenarios:***
- **BYOD (Bring Your Own Device):** Enforces corporate policies on personal smartphones and laptops without giving them full, unmonitored access to internal resources.
- **Guest Access:** Automatically provisions isolated Wi-Fi access for visitors, restricting them to the internet while blocking any visibility into internal corporate subnets.
- **IoT (Internet of Things) Onboarding:** Uses device profiling (identifying MAC OUI headers, DHCP fingerprints, and traffic patterns) to recognize headless devices like smart printers or IP cameras and place them into a locked-down VLAN.

![[Network Access Control.png]]

## Segmentation for Embedded Systems and IoT
### Embedded Systems
*An embedded system is a computer implemented as part of a larger system. The  embedded system is typically designed around a limited set of specific functions in relation to the larger product of which it is a component.*  

Examples of embedded systems include network-attached printers, smart TVs, HVAC controls, smart appliances, smart thermostats and medical devices. 

Network-enabled devices are any type of portable or non-portable device that has native network capabilities. This generally assumes the network in question is a wireless type of network, typically provided by a mobile telecommunications company. Network-enabled devices include smartphones, mobile phones, tablets, smart TVs or streaming media players (e.g., Roku Player, Amazon Fire TV, Google Android TV/Chromecast), network-attached printers, game systems, and more.

### Internet of Things (IOT)
*The Internet of Things (IoT) is the collection of devices that can communicate over the internet with one another or with a control console to affect and monitor the real world.* IoT devices might be labeled as smart devices or smart-home equipment. Many of the ideas of industrial environmental control found in office buildings are finding their way into more consumer-available solutions for small offices or personal homes.

Embedded systems and network-enabled devices that communicate with the internet are considered IoT devices and need special attention to ensure that communication is not used in a malicious manner.

Because an embedded system is often in control of a mechanism in the physical world, a security breach could cause harm to people and property. Since many of these devices have multiple access routes, such as ethernet, wireless, or Bluetooth, special care should be taken to isolate them from other devices on the network. You can impose logical network segmentation with switches using VLANs, or through other traffic-control means, including MAC addresses, IP addresses, physical ports, protocols, or application filtering, routing, and access control management. Network segmentation can be used to isolate IoT environments.

![[Pasted image 20261018165154.png]]

## MicroSegmentation
- **VLANs (Virtual Local Area Networks)**: operate at Layer 2 of the OSI model, logically grouping devices into distinct broadcast domains using 802.1Q tags. However, once devices are on the same VLAN, they can typically communicate freely with each other (East-West traffic) unless a router or firewall intervenes at Layer 3.
    
- **Microsegmentation**: is a software-defined security technique often associated with Zero Trust architectures that isolates workloads down to the individual server, container, or virtual machine level. It enforces strict, granular policies between individual nodes, preventing lateral movement even if the devices share the exact same VLAN or subnet.
    
In short, VLANs provide broad network-level segmentation, while microsegmentation provides fine-grained, workload-level isolation.

To explore this further, it helps to look at the type of traffic being controlled:

- **North-South Traffic ↕️**: Movement of data entering or leaving the network (such as a user accessing a web app from the internet).
- **East-West Traffic ↔️**: Movement of data between devices, servers, or workloads _inside_ the network.

Traditional firewalls are typically designed to secure North-South traffic at the perimeter. Microsegmentation, however, places distributed enforcement points directly around individual virtual machines or containers. This means even if an attacker breaches a web server, the software-defined firewall blocks any unauthorized East-West communication to neighboring databases or internal systems, regardless of whether they share the same subnet.

## Virtual Private Network (VPN)
*A virtual private network (VPN) is not necessarily an encrypted tunnel. It is simply a point-to-point connection between two hosts that allows them to communicate.*

Secure communications can, of course, be provided by the VPN, but only if the security protocols have been selected and correctly configured to provide a trusted path over an untrusted network, such as the internet.

Remote users employ VPNs to access their organization’s network, and depending on the VPN’s implementation, they may have most of the same resources available to them as if they were physically at the office. As an alternative to expensive dedicated point-to-point connections, organizations use gateway-to-gateway VPNs to securely transmit information over the internet between sites or even with business partners.













[^1]: **Default deny** is ==a security stance where **all traffic between network segments is blocked by default**==, and communication is only allowed if an explicit rule permits it.
	
	Instead of deciding what to _block_, a default deny approach forces administrators to decide exactly what is _allowed_. Anything not explicitly authorized is automatically dropped.
	
	How It Works
	
	Think of network segments under a default deny policy like rooms in a secure building:
	
	- **The Baseline:** All doors are locked by default. No one can move between rooms.
	- **The Exception:** A rule is written to create a specific pathway. For example, _"Allow the Web Server segment to talk to the Database Server segment only on Port 3306."_
	- **The Result:** The web server can talk to the database, but it is completely blocked from talking to employee laptops, backup servers, or any other segment.
	
	**The Opposite:** *Default Allow*
	
	In a **default allow** setup, all network segments can talk to each other freely until an administrator manually writes a rule to block a specific path. This is highly risky, as forgetting a single block rule leaves a door wide open for attackers to roam the entire network.
