## Event Logging Best Practices
### Ingress Monitoring
This involves the surveillance and assessment of all ***inbound*** communications traffic and access attempts. To capture logs and detect threats entering the network, organizations rely on tools such as *firewalls, gateways, remote authentication servers, intrusion detection/prevention systems (IDS/IPS), SIEM solutions, and anti-malware solutions.*
### Egress Monitoring
This is used to regulate ***data leaving*** the organization's IT environment. It is closely tied to Data Loss Prevention (DLP) solutions, which are deployed to inspect all forms of outgoing data. Key channels monitored include emails (content and attachments), copies to portable media, File Transfer Protocol (FTP) transfers, web page postings, and application programming interfaces (APIs).
## Security Awareness Training
The primary purpose of security awareness training is to ensure that every individual within an organization *understands what is expected of them based on their specific responsibilities and accountabilities.* Furthermore, it is designed to identify and address any human vulnerabilities such as *carelessness or complacency* that could introduce security risks to the organization.
### The Three Types of Learning Activities
To achieve effective security culture, organizations utilize three distinct learning activities, each serving a different purpose:
- **Education**: The overarching goal of education is to help learners *improve their conceptual understanding of security ideas, enhance their ability to relate those concepts to their own experiences, and apply that knowledge in practical, useful ways.*
- **Training**: Training focuses strictly on *building proficiency* in a specific set of skills or actions. This includes sharpening the perception and judgment required to decide which skill to use, when to apply it, and how to execute it. Training can range from low-level individual skills to entire tasks or complex workflows comprising multiple steps.
- **Awareness**: These are targeted activities designed to attract and engage a learner's attention by acquainting them with aspects of a security issue, concern, problem, or operational need.
### Formality and Audience Characteristics
An important distinction in these security programs is that none of these learning activities inherently require an expressed or implied degree of formality, a specific physical or virtual location, or a strictly defined target audience. They can be formal or informal, delivered anywhere, and tailored to any group.
### Real-World Application Scenario
Consider a newly hired senior executive joining a commercial bank in Lagos with little to no prior exposure to the specific regulatory and compliance requirements facing the organization. Before expecting them to master complex compliance frameworks, an organization must first use awareness activities to grab their attention and make them aware of why those security needs exist. Once awareness is established, formal education and skill-based training can follow.
## Security Awareness Training Example
### Fire Safety in the Workplace Example
Organizations can apply the concepts of education, training, and awareness to physical security needs, such as improving workplace fire safety:
- **Education**: Helps workers in a secure server room understand how various components interact, including fire and smoke detectors, suppression systems, alarms, electrical power, lighting, and ventilation systems.
- **Training**: Provides workers with task-specific, detailed instructions on the proper actions to take during an emergency, such as an alarm activation, an accidental suppression system discharge, or a ventilation failure. This builds directly upon the foundational knowledge gained through education.
- **Awareness**: Utilizes ongoing environmental cues such as signage, floor decals, and doorway markings to help workers quickly detect anomalies, respond to alarms, and execute proper safety protocols as a constant reminder.
### Translating the Framework to an Anti-Phishing Campaign
The same three-part strategy is applied to cyber security operations, such as defending against social engineering:
- **Education**: Helps selected groups of users understand how social engineering attacks are conducted, engaging them directly in creating and testing their own defensive strategies.
- **Training**: Increases user proficiency in recognizing potential phishing attempts and practicing correct responses. This includes practical exercises like sending simulated phishing emails across the network to test and measure user identification skills.
- **Awareness**: Focuses on raising *broad* user awareness regarding threats like phishing, vishing, SMS phishing ("smishing"), and other social engineering tactics, while alerting users to novel or emerging attack techniques.
## Password Protection
Password protection focuses on how individuals and organizations securely manage access credentials while avoiding common human and technical vulnerabilities.
- **Password Managers and Their Risks**: Many users rely on password managers to store multiple credentials so they do not have to memorize them all. However, the primary risk is the potential *compromise of the password manager itself*. If a user protects their password manager with a weak master password or passphrase, attackers can easily breach it and gain access to all stored private and corporate accounts.
- **Organizational Responsibilities**: Enterprises should actively encourage users to use unique, different passwords for different systems. Furthermore, organizations should provide a vetted, recommended password management solution to ensure secure handling across the board.
- **Poor Password Protection Practices to Avoid**:
    1. **Password Reuse**: Using the same password across multiple systems, particularly mixing business and personal accounts.
    2. **Physical Exposure**: Writing down passwords and leaving them in unsecured areas (such as on sticky notes attached to monitors).
    3. **Credential Sharing**: Sharing passwords with co-workers or technical support staff.
### Real-World Operational Scenario
Consider an employee at a fintech firm in Lagos who uses the same weak password for their personal email, social media accounts, and corporate database login. If their personal email is breached in a credential-stuffing attack on a third-party website, malicious actors can use those exact credentials to log into the corporate network, bypassing initial perimeter defenses.
## Phishing
Phishing attacks that attempt to trick highly placed officials or private individuals with sizable assets into authorizing large fund wire transfers to previously unknown entities are known as ***whaling attacks.***
## Social Engineering
Social engineering exploits ***human psychology*** rather than technical flaws, making it one of the most effective and inexpensive attack vectors for malicious actors.
### Core Concepts of Social Engineering
- **Definition and Purpose**: Social engineering involves manipulating individuals into performing actions or divulging confidential information. Attackers rely on human tendencies such as *trust, helpfulness, fear, or curiosity* because exploiting people is often easier than bypassing hardened technical security controls.
- **High ROI for Attackers**: It represents an inexpensive investment with a high payoff, allowing attackers to extract valuable insider knowledge over time.
- **Fieldcraft Origins**: Many social engineering techniques are traditional espionage methods rooted in investigative and intelligence-gathering tactics.
### Common Tactics Explored in the Material
- **Phone Phishing (Vishing)**: Attackers use rogue Interactive Voice Response (IVR) systems or phishing emails to trick victims into calling a fake support number. The victim is prompted to enter sensitive details like account numbers, PINs, or security answers, sometimes getting transferred to a human agent for further extraction.
- **Quid Pro Quo**: An attacker offers a benefit such as a *monetary reward, a gift, or access to a service* in exchange for *login credentials or passwords*. The governing principle is that if an offer sounds too good to be true, it usually is.
- **Pretexting**: The human equivalent of phishing, where an attacker impersonates a trusted authority figure (such as an IT support technician, law enforcement officer, or corporate auditor) to build a false sense of security and gain unauthorized access to credentials or physical spaces.
- **Tailgating**: The *physical practice of following an authorized person into a restricted area*. A physical example includes someone asking an employee to hold a door open because they forgot their ID badge. A more sophisticated digital version involves a stranger asking to borrow a phone or laptop under the guise of an emergency while secretly installing malicious software.
### Defense Strategies
Because social engineering targets human behavior, technical controls alone cannot stop it. Mitigation relies heavily on comprehensive *education, training, and awareness* programs to ensure every individual recognizes that they share accountability for organizational security.
