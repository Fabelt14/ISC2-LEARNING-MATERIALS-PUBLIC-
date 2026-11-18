## Transmission Control Protocol/Internet Protocol (TCP/IP)
The OSI model wasn't the first or only attempt to streamline networking protocols or establish a common communications standard. In fact, the most widely used protocol today, TCP/IP, was developed in the early ***1970s***. The OSI model was not developed until the late 1970s. The TCP/IP protocol stack *focuses on the core functions of networking.*
![[Pasted image 20260920141401.png]]

The most widely used protocol suite is TCP/IP, but it is not just a single protocol but a protocol stack comprising dozens of individual protocols. TCP/IP is a platform-independent protocol based on open standards. 

***However, this is both a benefit and a drawback. TCP/IP can be found in just about every available operating system, but it consumes a significant amount of resources and is relatively easy to hack into because it was designed for ease of use rather than for security.***  

>Back in the 1970s, the developers of TCP/IP were closed groups of researchers who completely trusted one another. Their primary goal was to ensure computers could successfully establish connections and share data, even if parts of the network crashed. Because they prioritized ease of connection and resilience, the original TCP/IP protocols do not inherently verify who is sending the data, nor do they encrypt the data by default.
>
>Since the entire internet runs on this TCP/IP architecture that was originally built without "locks on the doors," modern security requires us to layer protective measures on top of these older protocols.
>
>The specific protocol we layer on top of it to encrypt and secure that data before it travels down the TCP/IP stack is knows as **TLS** **(Transport Layer Security)**. It is indeed a full-fledged cryptographic protocol.
>
>*Here is how TLS and other encryption options fit into our network security toolkit:*
>- **TLS (Transport Layer Security)**: Operates right between the Application Layer and the Transport Layer. It encrypts the payload before passing it down to TCP.
>- **HTTPS (HTTP Secure)**: This isn't a separate protocol from scratch, but simply standard HTTP traffic wrapped inside a TLS encryption tunnel.
>- **IPsec (Internet Protocol Security)**: If we want to encrypt _everything_ moving between two networks rather than just web traffic, IPsec operates further down at the Internet Layer. This is commonly used in Virtual Private Networks (VPNs).
>- **SSH (Secure Shell)**: Operates at the Application Layer to provide an encrypted channel for remote command-line administration, replacing unencrypted legacy protocols like Telnet.

At the ***Application Layer***, TCP/IP protocols include *Telnet, File Transfer Protocol (FTP), Simple Mail Transport Protocol (SMTP), and Domain Name Service (DNS)*.

The two primary ***Transport layer protocols*** of TCP/IP are *TCP and UDP*. 
- *TCP is a full-duplex connection-oriented protocol*
- *UDP is a simplex connectionless protocol.* 

>**Simplex** is strictly one-way communication. One device acts solely as the sender, while the other acts solely as the receiver. A practical example is a CCTV security camera continuously transmitting footage to a storage recorder; the camera only sends data and does not receive data back over that video feed.
>
>**Duplex** broadly describes any system capable of two-way communication, which is further categorized into half-duplex and full-duplex.
>
>In **Half-Duplex**, data can move in both directions, but only one direction at a time. Endpoints must take turns transmitting. This is similar to a walkie-talkie system or legacy Ethernet hubs. If two endpoints attempt to send data simultaneously over a half-duplex channel, their signals collide and corrupt the data. This is called **data collision**
>
>In **Full-Duplex**, data moves in both directions simultaneously. Both endpoints can transmit and receive at the exact same time without interference, much like a phone conversation. Modern network switches operate in full-duplex mode by providing separate physical or logical paths for sending and receiving data.
>
>**Multiplexing** (often referred to in transmission context as multiple data streams) is the technique of combining multiple independent data signals into a single complex signal over a shared physical channel. For instance, a corporation uses multiplexing to send dozens of individual employee phone calls and web sessions over a single fiber-optic backbone cable simultaneously.

In the ***internet layer***, *Internet Control Message Protocol (ICMP)* is used to determine the health of a network or a specific link. ICMP is utilized by *ping, traceroute, and other network management tools.* 
The ping utility employs ICMP echo packets and bounces them off remote systems. Thus, you can use *ping to determine whether the remote system is online, whether the remote system is responding promptly, whether the intermediary systems are supporting communications, and the level of performance efficiency at which the intermediary systems are communicating.*

![[Pasted image 20260920141552.png]]

## Security of the Network
TCP/IP's vulnerabilities are numerous. *Improperly implemented* TCP/IP stacks in various operating systems are vulnerable to various DoS/DDoS attacks, fragment attacks, oversized packet attacks, spoofing attacks, and man-in-the-middle attacks. **(Active Attacks)**

TCP/IP (as well as most protocols) is also subject to passive attacks via monitoring or sniffing. Network monitoring, or sniffing, is the act of monitoring traffic patterns to obtain information about a network. **(Passive Attacks)**

## Ports and Protocols (Applications/Services)
There are physical ports that you connect wires to and logical ports that determine where the data/traffic goes.

### Physical Ports
Physical ports are the ports on the routers, switches, servers, computers, etc., to which that you connect the wires (e.g., fiber-optic cables, Cat5 cables) to create a network.

### Logical Ports
An IP address identifies a specific device on a network, while **logical ports** identify the specific application or service on that device meant to receive the incoming data.

Here is how ports function within the network stack:
- **Street Address vs. Apartment Numbers**: If an IP address is like the street address of a large apartment building, a logical port is the specific apartment number. Data arrives at the building (the host IP) and is delivered directly to the right door (the port number).
- **Multiplexing**: Ports allow a single computer with one IP address to handle multiple connections simultaneously. You can browse a website, stream music, and check email at the same time without the data streams mixing together.
- **Sockets**: A socket is the precise combination of an IP address and a port number (for example, ***192.168.1.50:443***). It defines a unique, end-to-end communication channel between two systems.
- **Secure vs. Unsecure Pairs**: Protocols often come in functional pairs, one legacy unencrypted version and one modern encrypted version:
    - **Port 80 (HTTP)** vs. **Port 443 (HTTPS)**
    - **Port 23 (Telnet)** vs. **Port 22 (SSH)**
        
When in doubt, systems should be implemented using the most secure version of a protocol and its services.

- **Well-Known Ports (0–1023)**: Assigned to core network services and standard protocols like HTTP (80), HTTPS (443), and SSH (22).
- **Registered Ports (1024–49151)**: Assigned to vendor-specific applications or database services, such as Microsoft SQL Server (1433) or RADIUS (1812).
- **Dynamic / Private Ports (49152–65535)**: Temporary ports assigned on the fly to client systems when ***initiating connections***, which are released as soon as the session closes.

## Secure Ports
**Cleartext protocols send data without encryption**, allowing anyone performing network sniffing to read sensitive data like passwords and files. **Secure alternatives use encryption (usually TLS)** to make intercepted data unreadable.

| **Protocol / Ports**                              | **What it Does (Function) 📝**                                                                                 | **Security Difference**                                                                                                |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **FTP (21)** $\rightarrow$ **SFTP (22)**          | **File Transfer**: Moves files between a client and a server.                                                  | FTP transmits logins and files in cleartext. SFTP encrypts all data using SSH.                                         |
| **Telnet (23)** $\rightarrow$ **SSH (22)**        | **Remote Access**: Provides text-based command-line interface to remote systems.                               | Telnet sends commands and passwords unencrypted. SSH encrypts the entire command session.                              |
| **SMTP (25)** $\rightarrow$ **SMTP w/ TLS (587)** | **Email Sending**: Delivers outgoing email messages between servers or clients.                                | Port 25 sends email content unencrypted. Port 587 uses TLS to encrypt outgoing mail.                                   |
| **Time (37)** $\rightarrow$ **NTP (123)**         | **Time Sync**: Keeps system clocks synchronized across a network.                                              | Port 37 is a legacy protocol with poor error handling. NTP on port 123 provides robust time sync.                      |
| **DNS (53)** $\rightarrow$ **DoT (853)**          | **Domain Lookup**: Converts human-friendly domain names (like google.com) to IP addresses.                     | Port 53 DNS queries are unencrypted and vulnerable to spoofing. DoT encrypts queries using TLS.                        |
| **HTTP (80)** $\rightarrow$ **HTTPS (443)**       | **Web Browsing**: Transmits web page content between web servers and browsers.                                 | HTTP sends web data in cleartext. HTTPS uses TLS encryption to protect traffic.                                        |
| **IMAP (143)** $\rightarrow$ **IMAPS (993)**      | **Email Retrieval**: Allows email clients to access and manage inbox messages on a server.                     | Port 143 sends email credentials and message content unencrypted. Port 993 encrypts connection via SSL/TLS.            |
| **SNMP (161/162)** $\rightarrow$ **SNMPv3**       | **Network Management**: Monitors and manages routers, switches, and other hardware devices.                    | SNMPv1/v2 transmit sensitive device data in cleartext. SNMPv3 adds built-in encryption using the same ports (161/162). |
| **SMB (445)** $\rightarrow$ **NFS (2049)**        | **File Sharing**: Allows users to access shared folders and files across a LAN.                                | SMB on 445 is inherently unencrypted and target for exploits. Both SMB & NFS should be blocked at network firewalls.   |
| **LDAP (389)** $\rightarrow$ **LDAPS (636)**      | **Directory Services**: Queries central directory databases for user logins, group policies, or address books. | LDAP on 389 transmits credential lookups in cleartext. LDAPS on 636 encrypts directory traffic using SSL/TLS.          |
- **SSL vs. TLS**: Older protocols mention SSL, but SSL is now insecure. Modern systems use **TLS 1.3+**.
- **The SNMP Exception**: SNMP is unique because version 3 adds encryption while keeping the **same port numbers (161/162)**.
- **Firewall Boundaries**: Protocols like SMB (445) and NFS (2049) should **never** be allowed through perimeter firewalls.
## Intrusion Detection System (IDS)
An intrusion occurs when an attacker is able to bypass or thwart security mechanisms and gain access to an organization’s resources.

An IDS continuously inspects real-time events and log files to identify unauthorized access or abnormal activity.
- **Defense-in-Depth**: An IDS does **not** replace a firewall. A firewall acts as a guard at the door (blocking/allowing traffic), while an IDS acts as a security camera inside (watching for suspicious behavior).
- **Alerting Function**: When an IDS detects an attack (like an incoming port scan or an internal worm), its primary role is to raise an alarm for security analysts to respond.
    
### HIDS vs. NIDS Comparison

| **Feature 🛠️**        | **Host-Based IDS (HIDS) 💻**                                                         | **Network-Based IDS (NIDS) 🌐**                                                          |
| ---------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| **Scope**              | Monitors a **single device** (host server or workstation).                           | Monitors **entire network segments** using sensors/tap ports.                            |
| **Data Inspected** 🔍  | System logs, process calls, local file modifications, local registry changes.        | Network packet headers and overall traffic flow patterns.                                |
| **Encrypted Traffic**  | **Can inspect**: Evaluates data after the host decrypts it.                          | **Blind to payloads**: Cannot view the contents of encrypted packets (e.g., HTTPS).      |
| **Visibility Context** | Knows **exact details** (e.g., which specific file was altered or process launched). | Knows an attack was launched, but **cannot confirm** if it succeeded on the target host. |
| **Management Cost**    | **Higher**: Requires agent management and configuration on every individual host.    | **Lower**: Centralized sensors monitor hundreds of devices simultaneously.               |

### Security Information & Event Management (SIEM)
While HIDS and NIDS generate alerts within their own specific scopes, a **SIEM** acts as the central brain of security operations. pronounced “SIM”
- **Centralized Aggregation**: Collects logs from firewalls, routers, switches, NIDS, HIDS, and servers across the entire organization.
- **Correlation**: Cross-references event logs from different sources to spot complex, multi-stage attacks that an individual system might miss on its own.

>- **Wazuh**: Functions as **both** a HIDS and a SIEM. It has its own dedicated endpoint agent installed on hosts to perform active HIDS tasks (like File Integrity Monitoring, rootkit detection, and local vulnerability scanning), and its manager aggregates those events like a SIEM.
>- **Splunk**: Functions primarily as a **SIEM** (log aggregation and analytics platform). On its own, Splunk does not include a native HIDS agent that actively performs file integrity checks or rootkit scans on an endpoint.
>  
>  To give Splunk HIDS-like visibility on endpoints, security teams must install endpoint monitoring utilities (such as **Microsoft Sysmon** or **Auditd**) alongside a Splunk log forwarder. Those host tools generate the security events, and Splunk analyzes them centrally.

#### Popular NIDS Examples
Network Intrusion Detection Systems sit on network segments to monitor passing packet traffic. Here are the most widely recognized NIDS tools:
1. **Snort**: The most famous, industry-standard open-source NIDS (maintained by Cisco). It uses signature-based rules to inspect real-time network traffic for known attack patterns.
2. **Suricata**: A modern, high-performance open-source NIDS/NIPS that processes traffic using multi-threading, making it ideal for very high-speed networks.
3. **Zeek** _(formerly Bro)_: An open-source network security monitoring tool that analyzes raw network traffic, decodes protocols, and generates detailed behavioral logs.
## Preventing Threats
While there is no single step you can take to protect against all threats, there are some basic steps you can take that help reduce the risk of many types of threat:

- **Keep systems and applications up to date:** Vendors regularly release patches to correct bugs and security flaws, but these only help when they are applied. Patch management ensures that systems and applications are kept up to date with relevant patches.
- **Remove or disable unneeded services and protocols:** If a system doesn't need a service or protocol, it should not be running. Attackers cannot exploit a vulnerability in a service or protocol that isn't running on a system. As an extreme contrast, imagine a web server is running every available service and protocol. It is vulnerable to potential attacks on any of these services and protocols.
- **Use intrusion detection and prevention systems:** Intrusion detection and prevention systems observe activity, attempt to detect threats, and provide alerts. They can often block or stop attacks.
- **Use up-to-date anti-malware software:** A primary countermeasure is anti-malware software.
- **Use firewalls:** Firewalls can prevent many different types of threats. Network-based firewalls protect entire networks, and host-based firewalls protect individual systems.
### Antivirus
The use of antivirus products is strongly encouraged as a security best practice and is a requirement for compliance with the Payment Card Industry Data Security Standard (PCI DSS).

There are several antivirus products available, and many can be deployed as part of an enterprise solution that integrates with several other security products.

Antivirus systems try to identify malware based on the signature of known malware or by detecting abnormal activity on a system. This identification is done with various types of scanners, pattern recognition, and advanced machine learning algorithms. Anti-malware now goes beyond just virus protection as modern solutions try to provide a more holistic approach detecting rootkits, ransomware, and spyware. Many endpoint solutions also include software firewalls and IDS or IPS systems.

### Scans
Regular vulnerability and port scans are a good way to evaluate the effectiveness of security controls used within an organization.

They may reveal areas where patches or security settings are insufficient, where new vulnerabilities have developed or become exposed, and where security policies are either ineffective or not being followed. Attackers can exploit any of these vulnerabilities.

Here is an example scan from Zenmap showing open ports on a host.
```python
Scanning 6 hosts
Discovered open port 143/tcp on 172.20.1.131
Discovered open port 80/tcp on 172.20.1.129
Discovered open port 22/tcp on 172.20.1.132
Discovered open port 22/tcp on 172.20.1.129
```
### Firewall
In building construction or vehicle design, a firewall is a specially built physical barrier that prevents the spread of fire from one area of the structure to another or from one compartment of a vehicle to another.

Early computer security engineers borrowed that name for the devices and services that isolate network segments from each other, as a security measure. As a result, firewalling refers to the process of designing, using, or operating different processes in ways that isolate high-risk activities from lower-risk ones.

***Firewalls enforce policies by filtering network traffic based on a set of rules.*** While a firewall should always be placed at internet gateways, other internal network considerations and conditions determine where a firewall would be employed, such as network zoning or segregation of different levels of sensitivity.

Firewalls have rapidly evolved over time to provide enhanced security capabilities. This growth in capabilities can be seen in the graphic below, which contrasts an oversimplified view of traditional and next-generation firewalls.

![[Pasted image 20260927180605.png]]

It integrates a variety of threat management capabilities into a single framework, including proxy services, intrusion prevention services (IPS) and tight integration with the identity and access management (IAM) environment to ensure only authorized users are permitted to pass traffic across the infrastructure. While firewalls can manage traffic at Layers 2 (MAC addresses), 3 (IP ranges) and 7 (application programming interface (API) and application firewalls), the traditional implementation has been to control traffic at Layer 4.

### Intrusion Prevention System (IPS)
An intrusion prevention system (IPS) is a special type of active IDS that automatically attempts to detect and block attacks before they reach target systems.

A distinguishing difference between an IDS and an IPS is that the IPS is placed in line with the traffic.

In other words, all traffic must pass through the IPS and the IPS can choose what traffic to forward and what traffic to block after analyzing it. This allows the IPS to prevent an attack from reaching a target. Since IPS systems are most effective at preventing network-based attacks, it is common to see the IPS function integrated into firewalls. Just like IDS, there are Network based IPS (NIPS) and Host-based IPS (HIPS).
