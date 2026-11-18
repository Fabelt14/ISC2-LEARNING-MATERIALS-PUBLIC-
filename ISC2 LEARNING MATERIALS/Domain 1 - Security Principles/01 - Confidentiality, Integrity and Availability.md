`Tags: #cybersecurity #cc #isc2 #Domain_Security`
# The CIA Triad
When defining security, it is common to use the CIA Triad:  **Confidentiality, Integrity, and Availability.** The purpose of these terms is to describe security using relevant and meaningful words that make security more understandable to management and users and define its purpose.
### Confidentiality
- This means permitting authorized access to information while at the same time protecting it from improper disclosure.
- It ensures that sensitive data is kept private and only accessed by authorized individuals. It prevents unauthorized disclosure or data leaks.
- **_Examples of protection:_** Encryption, multi-factor authentication (MFA), and strict access control lists. #secrecy
### Integrity
- Integrity is the property of information whereby it is recorded, used, and maintained in a way that ensures its completeness, accuracy, internal consistency, and usefulness for a stated purpose.
- It ensures that data and systems remain accurate, authentic, and reliable. It protects against unauthorized creation, alteration, or destruction of information.
- **_Examples of protection:_** File hashing, digital signatures, and version controls.
_A popular mobile money platform in Kenya experiences a logic flaw in its API. Attackers cannot view anyone else's account balance, and the system remains online and accessible to all users. However, malicious users discover a way to intercept their own money transfer requests and change the transaction amount from 100 KES to 10,000 KES right before it processes in the database. Which core security principle of the CIA Triad has failed?_

> **Version control** is a system that tracks and manages every change made to software code, documents, or files over time. It allows you to view history, compare modifications, and revert to earlier versions if needed. It logs exactly **who** made a change, **what** they changed, and **when** they did it. This accountability prevents anonymous tampering.
### Availability  
- Availability means that systems and data are accessible at the time users need them.
- It ensures that systems, networks, and data are accessible and usable to authorized users whenever they are needed.
- **_Examples of protection:_** Redundant servers, data backups, and using firewalls or load balancers to mitigate Distributed Denial of Service (DDoS) attacks.
### Privacy vs. Security
- **Security**: This is the technical, administrative, and physical controls put in place to protect data from unauthorized access, alteration, or destruction. It's like a **Bodyguard.** It is the locked door, the high fence, and the alarm system keeping the bad guys out.
- **Privacy**: This is the legal and ethical right of an individual to control how their personal identifiable information (PII) is collected, used, and shared. It's like a **Rulebook.** containing the agreement on _what_ the person inside the house is allowed to do with your secrets once you hand them over.

> Ensuring that protective security measures are in place is not enough to meet privacy regulations or to protect a company from incurring penalties or fines from mishandling, misuse, or improper protection of personal or private information.

> This is because you can have perfectly secure data that completely violates privacy. If a company stores your phone number in an unbreakable, military-grade encrypted database (Great Security!), 
> 
> But then legally sells your phone number to a telemarketing company without your permission, your privacy was violated even though the security held up perfectly.
### GDPR and "Borderless" Privacy Laws
The European Union’s GDPR **(General Data Protection Regulation)** (2016) has **"multinational implications."** This is called ***extraterritoriality***, and it means laws no longer care where your server is physically plugged in.
### Real-World Scenarios
- **The Lagos E-Commerce Scenario:** Imagine a startup in Yaba, Lagos, selling custom tech-wear. A customer in Paris visits the site and buys a hoodie. Even though the startup is 100% Nigerian, physically located in Lagos, and routing money through African payment gateways, they collected the name and address of an EU citizen. Under GDPR, that startup must handle the data according to EU law. If they misuse it, the EU can hit them with massive fines.
- **The Nigerian Context (NDPA):** Nigeria has its own version of this now, the **Nigeria Data Protection Act (NDPA)**. If a fintech app in Abuja collects BVNs and NINs securely, but uses that data to run background credit checks without telling the user in the Terms of Service, they will answer to the Nigeria Data Protection Commission (NDPC).

>Because the EU set such a high standard with GDPR, other places copied it. **South Africa** created ***POPIA (Protection of Personal Information Act)***, and states like California created the ***CCPA***. For a global company, it is too expensive to build 50 different privacy systems, so they usually just adopt the strictest one (GDPR) globally.

>**Summary**
> - **Security** = Protecting data from hackers.
> - **Privacy** = Respecting the user's right to control their data.
> - **GDPR** = The EU law that applies to _anyone, anywhere_ who touches the data of an EU citizen.
> - **Compliance** = You need both. A firewall (security) doesn't stop you from illegally selling user data (privacy violation).

### Jurisdiction & Extraterritoriality
- **Jurisdiction**: The legal authority granted to a legal body or political entity to administer justice within a defined area of responsibility. The specific area or group of people a government is allowed to make rules for.
- **Extraterritoriality**: A principle in international law where a government's laws apply to entities operating outside its physical, geographic borders. A country saying, "*I don't care where your company is located; if you touch my citizens' data, you play by my rules."*

# **Confidentiality**
#### **PII (Personally Identifiable Information):**
This is data that can be used on its own or with other information to identify, contact, or locate a single person. It consist of **Who you are** (Your NIN, BVN, phone number, home address, or fingerprint).

#### **PHI (Protected Health Information):**
These are health information that can be tied to an individual. Example: **Your Medical History.** Your blood type, prescriptions, or a diagnosis from the clinic.

#### **Sensitive/Classified Info**
These are information whose unauthorized disclosure would cause harm to national security, a business, or an individual. Example: **The Crown Jewels.** A company's secret recipe, future business plans, or the source code for a new app.

_Confidentiality is a difficult balance to achieve when... it is not known if they are accessing the system from a compromised machine._

> It is easy to keep a secret if you lock it in a vault and throw away the key. But in the real world, businesses have to let customers access their data. As a security pro, you have to protect the data while still letting the authorized user see it even if that user is logging in from a malware-infected phone or a public Wi-Fi network at a coffee shop.
### Real-World Scenarios
- **The Mobile Banking Balance:** Think about a Nigerian banking app like GTBank or Kuda. The bank must keep your account balance confidential. But they also have to let _you_ see it. If a customer connects to the app using a compromised public Wi-Fi network in a bustling Lagos cybercafe, the bank still has an obligation to protect that data in transit ***(using encryption)*** so a hacker on the same network can't read it.
#### **Sensitivity**
sensitivity measures the importance of information and the level of protection it requires. It defines how much harm such as financial loss, legal penalties, or privacy breaches would occur if the data were accessed, altered, or exposed without authorization. 
If a major fintech company gets hacked, the company's reputation takes a hit (internal harm). But the _external stakeholders_, the everyday Nigerians whose life savings or BVNs are now in the hands of identity thieves are the ones who suffer the most devastating harm.

## How PHI is Weaponized Against Individuals
On the dark web, a stolen credit card might sell for $5, but a complete Protected Health Information (PHI) record can sell for hundreds of dollars. Why? Because you can cancel a credit card, but you cannot change your medical history.
Here is how threat actors use PHI to attack individuals:
- **Extortion and Blackmail:** Medical records contain a person's deepest secrets—mental health diagnoses, HIV status, reproductive history, or terminal illnesses. Hackers will contact the individual directly and threaten to publish this information to their family, employer, or the public unless a ransom is paid in crypto.
- **Medical Identity Theft:** A hacker sells your PHI to someone who needs expensive medical treatment or prescription drugs. That person goes to a hospital pretending to be you, using your HMO or health insurance. Not only does this drain your insurance limits, but the fraudster's blood type, allergies, and diagnoses get mixed into _your_ permanent medical record, which could kill you if a doctor relies on it later in an emergency.
- **Precision Spear-Phishing:** Imagine getting an SMS that says, _"Dear Prime, regarding your malaria treatment at Reddington Hospital on May 20th, your payment of ₦45,000 failed. Click here to update your card."_ Because the hacker stole the hospital's PHI database, they know exactly when you were there and what you were treated for. It is incredibly easy to trick victims when the bait is that accurate.
- **Total Financial Takeover:** PHI doesn't just contain health data; it usually includes your full name, home address, date of birth, and sometimes your BVN or NIN used for billing. Hackers use this complete "profile" to open fake bank accounts or take out loans in your name.
> - **Intellectual Property (IP) / Trade Secrets:** These are the unique processes, formulas, and strategies that give a company its competitive advantage.
> - **Non-Disclosure Agreement (NDA):** This is the legal contract you sign when you get hired. It explicitly states that the company's internal operations are classified and sensitive.
>   
>   Even if the information doesn't contain user data or passwords, exposing _how_ a company does its security makes them incredibly vulnerable to competitors and hackers. If Company A finds out you shared their proprietary processes with Company B, they can sue you for corporate espionage and breach of contract.

# **Integrity**
_Integrity is all about trust. If you cannot trust that your data is accurate and unchanged, the system is useless._
#### **The Two Types of Integrity**
1. **Data Integrity**: This is the assurance that data has not been altered in an unauthorized manner during storage, processing, or transit. **The Unbroken Seal.** Proving that the file, email, or transaction hasn't been tampered with since it was created.
2. **System Integrity**: This is the maintenance of a known good configuration and expected operational function. **The Clean Slate.** Knowing your server or software hasn't been secretly reconfigured by a hacker or a careless employee.
#### **Baselines and State (The "Before and After")**
Imagine you build a fresh Windows Server for your Atlas Scope project. You configure all the firewalls perfectly. That exact snapshot of perfection is your **Baseline** (the known good state).
- **The Problem:** Over time, employees change settings, software updates break things, or hackers slip in. The server's **State** changes.
- **The Solution:** To guarantee _System Integrity_, you constantly compare the _current State_ to your original _Baseline_. If they match, your integrity is intact. If they don't, something changed, and you need to investigate.
##### ***Real-World Scenarios***
- **The Nigerian Fintech Scenario (Data Integrity):** You are sending ₦50,000 to a vendor in Lagos via a bank transfer. The bank must ensure **Data in Transit** integrity. If a man-in-the-middle attacker intercepts the transaction and changes the receiving account number or adds an extra zero to make it ₦500,000, that is a catastrophic failure of data integrity.
- **The "Database Sync" (Consistency):** Think of a large telco like MTN. If you update your home address in their mobile app, but the customer service rep in the call center still sees your old address on their screen, the system lacks **Internal Consistency**. The data is no longer identical in form and content across the organization.
### **How Do We Actually Prove Integrity?**
In cybersecurity, we use math to prove that data hasn't been tampered with. We do this using **Hashing**.
A hash is like a digital fingerprint for a file or a piece of text. If you change even one single letter or space in a 100-page document, the entire fingerprint changes completely. This is how we prove that the current state matches the baseline.

***Original Data*** 
![[Pasted image 20260525230627.png]]
***Original Data Modified***
![[Pasted image 20260525230720.png]]

# **Availability and Criticality**
- **Availability:** This is timely and reliable access to data and information services for authorized users. **The Open Sign.** It makes sure the system is online, fast, and working when the people who need it actually show up.
- **Criticality:** This is the measure of importance an organization assigns to a system in performing its core mission. **The Heartbeat.** It determines how fast the company bleed out and die if this specific system goes offline.
#### ***The CC Exam Trap: Criticality vs. Sensitivity***
- **Sensitivity** (tied to Confidentiality) answers: _"How bad is the damage if this data is LEAKED to the public?"_
- **Criticality** (tied to Availability) answers: _"How bad is the damage if this system goes OFFLINE and we can't use it?"_
### ***The Myth of 100% Uptime***
_"Availability does not mean that data or systems are available 100% of the time."_
In the real world, achieving 100% uptime is impossible and trying to get close to it (like 99.999% or "five nines") costs millions of dollars. As a security professional, your job isn't to keep everything online forever; your job is to ask the business owners, "How much downtime can you afford?"
### Real-World Scenarios
- **High Criticality (The Lagos Hospital):** Think of the intensive care unit database at LUTH (Lagos University Teaching Hospital). If doctors cannot access patient blood types or medication allergies immediately, people could die. The _Criticality_ is extreme. The hospital must invest in backup servers, multiple internet providers, and heavy-duty generators to ensure maximum _Availability_.
- **Low Criticality (The University Portal):** Now think of a university's student course registration portal. If the portal goes down for 4 hours at 2:00 AM on a Sunday for database maintenance, nobody dies. The university doesn't lose millions of Naira. The _Criticality_ is low, so the business accepts a lower level of _Availability_.
- **The Power Grid Reality:** In Nigeria, we deal with physical availability issues all the time due to national grid collapses. True availability in cybersecurity doesn't just mean protecting against DDoS attacks; it means ensuring you have an Uninterruptible Power Supply (UPS) and automated failover systems so your servers don't crash when the physical power drops.

>_We don't aim for 100% uptime. We aim to meet the ***business requirements*** for reliability._
>
>**Threats to Availability:** Ransomware (encrypts data so you can't use it), DDoS attacks (floods the network), and hardware/power failures.

[[02 - Identity Assurance]]
