`Tags: #CC #isc2`
## 1. What is a Security Control?
In the simplest terms: **A control is any mechanism put in place to protect the CIA Triad.**

If an attacker wants to steal data (Confidentiality), alter a log file (Integrity), or crash a server (Availability), the control is the roadblock standing in their way.

Controls can be physical (a biometric lock on a data center door), technical (a firewall blocking traffic), or administrative (a company policy forbidding shared passwords).
## 2. Subjects vs. Objects (The ISC2 Trap)
Your text mentions: _"limiting what objects can be available to what subjects."_

You must memorize the strict difference between these two terms, as the CC exam will try to trick you by swapping them.

|**Term**|**The Definition**|**The Offensive Translation**|
|---|---|---|
|**Subject**|The **active** entity that requests access.|The user logging in, the Python script running a scan, or the malware trying to execute.|
|**Object**|The **passive** entity that contains the information.|The SQL database, the `/etc/shadow` file, or the network share.|

**The Rule:** Subjects manipulate Objects. Objects do not manipulate Subjects.

>This is the classic ISC2 trap. Most people memorize "Subject = Person" and "Object = File." But in the real world—and on the exam—that is a massive oversimplification.
>
>When you build automated pipelines to map attack surfaces, you aren't manually typing every command; you have code doing the work for you. ISC2 knows this, and they will test if you understand how automation fits into the Subject/Object model.
## 3. The Firewall (Ingress & Egress)
Your notes use a firewall as the primary example of a technical control. From a defensive standpoint, it sits at the perimeter. From an offensive standpoint, it is the first thing that drops your Nmap packets.

You need to know the two directions a firewall filters traffic:

- **Ingress Filtering (Outside-In):** This is the firewall blocking malicious traffic from entering the environment. When you run an external port scan against a target IP, the firewall's ingress rules determine what ports appear as "filtered" versus "open."
    
- **Egress Filtering (Inside-Out):** This is the firewall preventing unauthorized data from leaving the environment. If you successfully compromise a web server and try to spawn a reverse shell back to your own machine, a properly configured firewall will block that outbound connection, trapping you inside.
## Control Overview
### The Goal of Access Control

![[Pasted image 20260707175906.png]]

The text points out a massive misconception: people think Access Control is only about _blocking_.

In reality, the primary job of Access Control is to **allow** the right people to do their jobs safely. If you deploy a firewall that blocks 100% of traffic, you have perfect security, but you also just bankrupted the company. Access control is the delicate balance of letting the business operate while keeping unauthorized users out.

### The Engine: How Rules Work
The Subject cannot just walk up to the Object and touch it. The text notes that "objects do not contain their own access control logic." A file cannot protect itself.

Instead, the Subject must submit a request, and that request is intercepted by the **Rule** (often managed by an Access Control List, or ACL). Think of the Rule as the bouncer at the door of a club.

When your automated reconnaissance script (Subject) tries to pull a configuration file (Object), the Rule evaluates several things before making a decision:
- **Identity:** Who is asking? (Is this the root user or a guest?)
- **Clearance:** Does this user have the right security level?
- **Permissions:** What exactly are they trying to do? (Read, Write, Execute?)
- **Time:** Are they allowed to do this right now? (Time-based access).
### The Implicit Deny
The text gives the example of a firewall: _"By default, firewalls deny access from any address to any address, on any port."_

This is the most critical concept in security rule-building, known as **Implicit Deny** (or Default Deny). It means that unless there is a specific, explicitly written rule that says "Allow this Subject to touch this Object," the default answer is always no.

When you are hunting for misconfigurations during an engagement, you are usually looking for an environment where an administrator got lazy and changed the default rule from "Deny All" to "Allow All," just to make things work faster.
### The Key Takeaway for the Exam
Access Control is a three-way interaction: The **Subject** initiates the request, the **Rule** evaluates the attributes to determine if it is safe, and the **Object** passively receives the authorized action.

## Least Privilege
- **The Principle of Least Privilege:** This is a fundamental security rule stating that users, processes, and systems must be granted _only_ the absolute minimum level of access (permissions/rights) required to perform their official job duties, and nothing more. It directly protects **Confidentiality** and **Integrity**.
- **Need-to-Know:** A concept closely related to Least Privilege but distinct. While Least Privilege focuses on _privileges/actions_ (e.g., read, write, execute), **Need-to-Know** focuses on _data authorization_. It means a user should only have access to specific information if it is necessary to perform their current task, even if their general security clearance level is high enough to see it.
- **Privileged Access Management (PAM):** A suite of technologies and processes used to secure, control, monitor, and audit elevated accounts (like "Admin" or "Root" accounts) that have bypass capabilities.
- **Role-Based Access Control (RBAC):** An access control model where permissions are assigned to specific _roles_ (e.g., "Billing Clerk," "Doctor") rather than to individual users. Users are then assigned to those roles.
- **Temporal/Just-In-Time (JIT) Access:** Restricting access by time constraints (e.g., only allowing server access during a scheduled maintenance window or normal Nigerian business hours of 8:00 AM to 5:00 PM).
### The Nigerian / African Context Scenario
Imagine a major health-tech and telemedicine startup based in **Yaba, Lagos**, called _NaijaCare_. They have a digital platform where patients consult with doctors and order prescription drugs.

Let's look at how they apply **Least Privilege** and **Need-to-Know**:

- **The Pharmacy Dispatch Rider:** They need to deliver a package to a customer in Surulere.
    - _Least Privilege Applied:_ The rider's mobile app only displays the customer's name, phone number, and delivery address. The app completely blocks them from viewing the patient's actual medical diagnosis or medical history. They don't _need to know_ why the customer ordered the drugs to deliver them.
- **The Telemedicine Doctor:**
    - _Need-to-Know Applied:_ A doctor logged into the system can view the medical history of patients _specifically assigned_ to them for a consultation today. They cannot browse the database to read the medical files of other patients or Nigerian celebrities who use the platform.
- **The Database Administrator (DBA):**
    - _Temporal Access Applied:_ The DBA does not have permanent, open-ended access to read patient records. If they need to run a system update, they must request temporary (JIT) administrative access, which is automatically revoked after 2 hours and completely logged.
### ISC2 Exam Traps Exposed
ISC2 examiners love to test your ability to separate "good business sense" from "convenient IT practices." Watch out for these traps:
- **The "Convenience vs. Security" Trap:**
    - _The Trap:_ A question might describe an IT Support technician who occasionally assists the HR department. To make things "faster and easier" for support tickets, the system administrator grants the technician permanent "HR Admin" access. The question will ask if this is an acceptable practice.
    - _The Truth:_ **Absolutely not.** This violates Least Privilege. The technician should only be granted temporary, limited access when a specific ticket is open, or they should shadow the HR user. Convenience is never an excuse to bypass Least Privilege.
- **Least Privilege vs. Need-to-Know (The Distractor):**
    - _The Trap:_ You will get a question asking about restricting access to specific sensitive files. Both "Least Privilege" and "Need-to-Know" will be options.
    - _The Rule of Thumb:_ If the question focuses on **system permissions, rights, and roles** (e.g., read, write, run programs, admin rights), the answer is **Least Privilege**. If the question focuses strictly on **the sensitivity of the data/information itself** (e.g., "Why shouldn't a top-secret cleared general read a project file he isn't working on?"), the answer is **Need-to-Know**.   
- **The "Super Admin" Trap:**
    - _The Trap:_ A scenario where a manager wants to perform a simple task, so the IT team gives them the password to the main "Administrator" account to "get it done quickly."
    - _The Truth:_ This violates Least Privilege and destroys **Accountability** (if something goes wrong, you can't prove _who_ did it because everyone is using the shared admin account).
### Simplified Summary
> **Least Privilege** is like renting a room in a shared apartment in Lagos. You get a key to the front gate and a key to _your_ bedroom. You do not get a key to your flatmate's bedroom because you have no business going in there.
> 
> **Need-to-Know** means that even if you find your flatmate's door unlocked, you shouldn't go inside and read their personal diary unless they specifically ask you to find something for them.

## Separation of Duties
Separation of duties is based on the security practice that *no one person* should control an entire high-risk transaction from start to finish.

To pass the exam, you need to understand the subtle differences between how power and access are divided among employees to prevent fraud and mistakes:

- **Separation of Duties (SoD):** Breaking a critical business _process_ into multiple, consecutive steps so no single person can complete the whole process alone. (e.g., Person A writes the invoice, Person B approves it).
- **Collusion:** The ultimate enemy of SoD. This is when two or more employees secretly team up to bypass the security rules and commit a crime together.
- **Dual Control:** A specific type of restriction where two people must act _at the exact same time_ to complete a single action.
- **Two-Person Integrity (The Two-Person Rule):** A physical security rule stating that nobody is ever allowed to be in a highly secure room alone. It requires two bodies in the room at all times to watch each other.
### The Corporate Bank in Lagos
Let's see how all four of these concepts apply to a major commercial bank's headquarters in **Marina, Lagos**:

- **Separation of Duties in action:** A junior bank teller can initiate a 50 million Naira international wire transfer for a corporate client (Step 1). However, the money will not leave the bank until the Branch Manager logs in and approves the system alert (Step 2).
- **Collusion in action:** The teller and the manager are secretly dating. They agree to wire 50 million Naira to a fake shell company they created and split the money. Separation of Duties failed here because of human corruption.
- **Dual Control in action:** To get the physical cash bundles out of the main vault to load the ATMs, the Branch Manager enters a PIN code on the vault keypad, and the Head Cashier turns a physical key at the exact same time. Neither person can open the vault alone.
- **Two-Person Integrity in action:** Inside the bank's core server room, the door will not unlock unless two authorized ID cards are swiped. Once inside, if one network engineer needs to step out to use the restroom, the second engineer _must_ exit the server room with them. No one is ever left alone with the servers. A secondary benefit here is **Life Safety**; if one engineer suffers a medical emergency (like a heart attack) while working on the cables, the other is there to call for help.
### The ISC2 Exam Traps Exposed
- **Trap 1: SoD vs. Dual Control (The Timing Trap):**
    - _The Trap:_ ISC2 will describe two people turning keys simultaneously and ask what concept this is. You might be tempted to pick Separation of Duties.
    - _The Truth:_ SoD is about a _process_ broken into consecutive steps over time (A does step 1, B does step 2 later). Dual Control is about a single _action_ requiring two people simultaneously (A and B do step 1 together).
- **Trap 2: The "Software Fix" for Collusion:**
    - _The Trap:_ The exam asks which firewall or software setting prevents collusion.
    - _The Truth:_ Collusion is a _human_ problem. No technical control perfectly prevents it. You deter collusion through administrative controls like mandatory vacations, job rotation, and background checks.
- **Trap 3: The Hidden Benefit of Two-Person Integrity:**
    - _The Trap:_ The exam asks for a primary reason for Two-Person Integrity, and the options include reducing insider threats and ensuring physical safety.
    - _The Truth:_ ISC2 loves testing life safety. Always remember that Two-Person Integrity isn't just about stopping thieves; it ensures someone is present during a medical emergency.
