## Internet Protocol (IPv4 and IPv6)
IP hosts/devices associate an address with a unique logical address. An IPv4 address is expressed as four octets separated by a dot (.), for example, 216.12.146.140.

Each octet may have a value between ***0 and 255***. However, *0 is the network itself (not a device on that network)*, and 2*55 is generally reserved for broadcast purposes.* Each address is subdivided into two parts: the **network number** and **the host**. 

- The network number assigned by an external organization, such as the Internet Corporation for Assigned Names and Numbers (ICANN), represents the organization's network.
- The host represents the network interface within the network.

![[Pasted image 20260926234924.png]]

To ease network administration, networks are typically divided into ***subnets***. Because subnets cannot be distinguished with the addressing scheme discussed so far, a separate mechanism, the ***subnet mask***, is used to define the part of the address used for the subnet. The mask is usually converted to decimal notation like 255.255.255.0.

>An IP address (like `192.168.1.50`) contains two distinct pieces of information in a single string: which network the device belongs to, and which specific device it is. A **subnet mask** is the mechanism that draws the precise line between those two parts.
>
>Think of an IP address like a standard postal address. The subnet mask tells the router where the city or street name ends and where the specific building number begins. Without a subnet mask, network hardware cannot tell whether another device is sitting on the local network segment or if traffic needs to be sent through a gateway router.
>
>When you see a standard subnet mask like `255.255.255.0`, the `255` octets block out the network portion, while the `0` octet highlights the host portion:
>
>- **Network ID** 🌐: The `255.255.255` portion identifies `192.168.1` as the shared sub-network address for every system in that group.
>- **Host ID** 💻: The `.0` portion leaves the final number (`.50`) to identify that unique workstation or server within the sub-network.
>  
>  By dividing a large corporate network into these smaller subnets, administrators can control traffic flow, reduce unnecessary broadcast noise, and apply distinct security boundaries between departments.

Because IPv4 uses a 32-bit format, it can only produce about ***4.3 billion*** unique addresses worldwide, far too few for every modern connected devices. To prevent running out of addresses, specific IP ranges were set aside strictly for internal local area networks (LANs):

- `10.0.0.0` – `10.255.255.255`
- `172.16.0.0` – `172.31.255.255`
- `192.168.0.0` – `192.168.255.255`

Here is how this mechanism works in practice:

- **Internal Address Reuse**: Millions of independent home and small office networks can simultaneously use the exact same internal address (like `192.168.2.100`) without conflicting with one another.
    
- **Routing Isolation**: Public internet routers are explicitly configured to drop traffic containing private IP addresses. They cannot be routed directly across the public internet.
    
- **Security Boundary**: Because private addresses are isolated inside the local network, an external attacker on the internet cannot directly address or intercept traffic sent to a `192.168.2.xxx` host from the outside.

### IPv6
IPv6 is a modernization of IPv4, which addressed a number of weaknesses in the IPv4 environment:
- **A much larger address field:** IPv6 addresses are ***128-bits***, which supports 2128 or 340,282,366,920,938,463,463,374,607,431,768,211,456 hosts. This ensures that we will not run out of addresses.
- **Improved security:** IPsec is an optional part of IPv4 networks, but a mandatory component of IPv6 networks. This will help ensure the integrity and confidentiality of IP packets and allow communicating partners to authenticate each other.
- **Improved quality of service (QoS):** This will help services obtain an appropriate share of a network's bandwidth.

An IPv6 address is shown as **eight groups of four digits**. Instead of numeric (0-9) digits   like IPv4, IPv6 addresses use the hexadecimal range ***(0000-ffff)*** and are separated by ***colons (:)*** rather than periods (.).  

An example IPv6 address is ***2001:0db8:0000:0000:0000:ffff:0000:0001***. To make it easier for humans to read and type, *it can be shortened by removing the leading zeros at the beginning of each field and substituting two colons (::) for the longest consecutive zero fields.* All fields must retain at least one digit. After shortening, the example address above is rendered as ***2001:db8::ffff:0:1,*** which is much easier to type.

1️⃣ **Omit Leading Zeros:** You can remove any zeros sitting at the beginning of a 4-digit group.
- `0db8` becomes `db8`
- `0000` becomes `0`
- `0001` becomes `1`
2️⃣ **Use the Double Colon (`::`):** You can replace a contiguous sequence of all-zero groups with a double colon `::`.
- In the example address, the three consecutive `0000:0000:0000` blocks are replaced by `::`, collapsing `2001:db8:0:0:0:ffff:0:1` down to `2001:db8::ffff:0:1`.
- ⚠️ **Crucial Rule:** You can only use `::` **once** in an address. If you used it twice, there would be no way to tell how many zero blocks were removed from each `::`.

Just like IPv4 set aside special address ranges (such as private `192.168.x.x` addresses), IPv6 reserves specific address blocks for system testing, documentation, and internal enterprise security.

Here is what each reserved block handles:
- 🔄 **Loopback Address (`::1`)**: This allows a system to send network traffic to itself. It is used for testing local software services and verifying that the local TCP/IP stack is working properly without sending any data out onto a physical wire.
- 📚 **Documentation Range (`2001:db8::/32`)**: Reserved specifically for textbooks, technical documentation, and exam scenarios. It ensures instructors and writers can use realistic addresses without accidentally using a live address assigned to a real company.
- 🏠 **Unique Local Addresses (`fc00::/7` through `fdff:...`)**: This is IPv6's counterpart to IPv4 private addresses. Organizations use this range for internal network traffic. Public internet routers are pre-configured to ignore and drop these addresses.
## Types of Threats
- **Spoofing:** This is an attack with the goal of gaining access to a target system through the use of a falsified identity. Spoofing can be used against IP addresses, MAC address, usernames, system names, wireless network SSIDs, email addresses, and many other types of logical identification.
- **Phishing:** An attack that attempts to misdirect legitimate users to malicious websites through the abuse of URLs or hyperlinks in emails could be considered phishing.
- **DOS/DDOS:** A denial-of-service (DoS) attack is a network resource consumption attack that has the primary goal of preventing legitimate activity on a victimized system. Attacks involving numerous unsuspecting secondary victim systems are known as distributed denial-of-service (DDoS) attacks. 
>**Single machine** (one IP address) sending attack traffic. Easy to block, A firewall can simply drop traffic from the single attacking IP address. ***(DOS)***
>**Multiple machines** called botnets (hundreds or thousands of IP addresses) attacking simultaneously. **Harder to block**: Traffic arrives from many global locations, making it difficult to separate malicious traffic from legitimate users. ***(DDOS)***
- **Virus:** The computer virus is perhaps the earliest form of malicious code to plague security administrators. As with biological viruses, computer viruses have two main functions-propagation and destruction. A virus is a self-replicating piece of code that spreads without the consent of a user, but frequently with their assistance-for example, a user must click on a link or open a file. *Attaches itself to a legitimate file, document, or executable program. and Spreads only when a user executes the infected file or program.*
- **Worm:** Worms pose a significant risk to network security. They contain the same destructive potential as other malicious code objects with an added twist-they propagate themselves without requiring any human intervention. *Operates independently as its own file/program without attaching to host files. and Spreads automatically across network connections without human intervention.*
- **Trojan:** Named after the ancient story of the Trojan horse, the Trojan is a software program that appears benevolent but carries a malicious, behind-the-scenes payload that has the potential to wreak havoc on a system or network. For example, ransomware often uses a Trojan to infect a target machine and then uses encryption technology to encrypt documents, spreadsheets, and other files stored on the system with a key known only to the malware creator. *A Trojan horse is malicious software disguised as a legitimate or desirable program to trick a user into downloading and executing it.*
- **On-path Attack:** In an on-path attack, attackers place themselves between two devices, often between a web browser and a web server, to intercept or modify information that is intended for one or both of the endpoints. On-path attacks are also known as *man-in-the-middle (MITM) attacks.*
- **Side-channel:** A side-channel attack is a passive, noninvasive attack to observe the operation of a device. Methods include power monitoring, timing and fault analysis attacks.
- **Advanced Persistent Threat (APT):** Advanced persistent threat (APT) refers to threats that demonstrate an unusually high level of technical and operational sophistication spanning months or even years. APT attacks are often conducted by highly organized groups of attackers.
- **Insider Threat:** Insider threats are threats that arise from individuals who are trusted by the organization. These could be disgruntled employees or employees involved in espionage. Insider threats are not always willing participants. A trusted user who falls victim to a scam could be an unwilling insider threat.
- **Malware:** A program that is inserted into a system, usually covertly, with the intent of compromising the confidentiality, integrity or availability of the victim's data, applications or operating system or otherwise annoying or disrupting the victim.
- **Ransomware:** Malware used for the purpose of facilitating a ransom attack. Ransomware attacks often use cryptography to “lock” the files on an affected computer and require the payment of a ransom fee in return for the “unlock” code.

## On-Premises Data Centers
When it comes to data centers, there are two primary options: organizations can outsource the data center or own the data center. If the data center is owned, it will likely be built on premises. A place, like a building for the data center, is needed, along with power, HVAC, fire suppression, and redundancy.
![[Pasted image 20261006183038.png]]
### 1. Data Centers & Wiring Closets
- **Physical Layer Protection**: Focuses on securing physical access to network cabling, switches, servers, and ISP equipment to prevent unauthorized tampering or accidental disconnections.
- **Demarcation Security**: Ensures incoming telecommunication lines and provider equipment are stored in locked, monitored spaces.
### 2. Heating, Ventilation, and Air Conditioning (HVAC) & Environmental Controls
- **Temperature Standards**: The recommended operational temperature range is **64°F to 81°F (18°C to 27°C)**. Racks should use **3 temperature sensors** (top, middle, bottom) for accurate monitoring.
- **Air Quality**: Filters out dust and fumes that cause hardware overheating or component degradation.
- **Environmental Monitoring**: Integrates sensors for water/gas leaks, sewer backups, and HVAC failures with automated alarm systems to trigger contingency responses.
### 3. Power Delivery & Redundancy
- **Power Quality**: Voltage fluctuations (sags, spikes) degrade hardware lifespans, while outages stop operations completely.
- **Uninterruptible Power Supply (UPS / Batteries)**: Provides immediate, temporary power to bridge the gap during an outage.
- **Backup Generators**: Supply long-term power. **Key Exam Point**: Generators must be sized to support both the **critical load** (servers) AND the **supporting infrastructure** (HVAC cooling). Failover systems must be tested regularly.
### 4. Fire Suppression
- **Water Systems**: Effective for general building fires, but causes severe damage to electrical equipment.
- **Gas-Based (Clean Agent) Systems**: Protects sensitive electronics without leaving residue, but introduces **toxicity and asphyxiation risks** to human occupants. Requires proper evacuation signaling.
## Redundancy
The concept of redundancy is to design systems with duplicate components so that if a failure were to occur, there would be a backup. This can apply to the data center as well. Risk assessments pertaining to the data center should identify when multiple separate utility service entrances are necessary for redundant communication channels and/or mechanisms.

If the organization requires full redundancy, devices should have two power supplies connected to diverse power sources. Those power sources would be backed up by batteries and generators. In a high-availability environment, even generators would be redundant and fed by different fuel types.

![[ISC2 Redundancy.png]]

>***The diagram shows a fully redundant power architecture divided into two completely mirrored feeds (top path and bottom path):***
>
>- **Dual Power Feeds (Servers)**: The green server racks in the middle connect to both the top and bottom circuits simultaneously. If one entire side fails, the servers' dual power supplies keep running off the remaining side without interruption.
>  
>- **Diverse Utility Entrances**: The system uses two separate "Utility Power" feeds. This ensures that a localized power grid failure or cut cable on one line won't drop the entire facility.
>  
>- **Transfer Switches**: These constantly monitor grid health. If utility power cuts out, the transfer switch automatically toggles the source feed over to the generator.
>
>- **UPS (Uninterruptible Power Supply)**: Sits in-line before the servers to immediately feed continuous battery power to the load.
>  
>- **Redundant Generators & Fuel Storage**: Each path features its own independent engine generator and dedicated fuel storage tank to sustain long-term operations during extended grid outages
