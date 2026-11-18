Here are the primary things to remember in this domain: 
1. The Incident Response plan responds to unexpected changes in operating conditions to keep the business operating.
2. The Business Continuity plan enables the business to continue operating throughout the crisis.
3. If both the Incident Response and Business Continuity plans fail, the Disaster Recovery plan is activated to help the business return to normal operations as quickly as possible.
## Incident Terminology
Before you can understand how a Security Operations Center (SOC) responds to an attack, you need to speak their language. On the CC exam, ISC2 loves to test if you know the difference between an "Event" and an "Incident." In the real world, confusing these terms during a panicked phone call to the CISO will get you yelled at.

As an offensive security professional, this is the exact vocabulary the blue team uses when they are tracking _you_ on their network.
### The Timeline of Bad News (Event $\rightarrow$ Incident $\rightarrow$ Breach)
These three terms represent an escalation. Not all events are incidents, and not all incidents are breaches.
#### Event
Any observable occurrence in a network or system. **"Something happened."** A user logged in, a router rebooted, or an automated bash script ran. 99% of events are completely harmless and normal.
#### Incident
An event that actually or potentially jeopardizes the CIA Triad of an information system. **"Something BAD happened."** A user logged in at 3:00 AM from a country the company does not operate in, or a malware payload executed. The SOC is now actively investigating.
#### Breach
The loss of control, unauthorized disclosure, or unauthorized acquisition of PII (Personally Identifiable Information). **"The data is gone, call the lawyers."** The bad guy didn't just get into the system; they successfully stole or exposed customer data. This triggers legal penalties and public notifications.
### The Mechanics of the Attack
This is the exact sequence of how you, as a penetration tester, compromise a system.
#### Threat
Any circumstance or event with the potential to adversely impact organizational operations via unauthorized access. **The Danger.** This could be a ransomware gang, a disgruntled employee, or a hurricane. It is the entity or force _capable_ of doing damage.
#### Vulnerability
Weakness in an information system, security procedures, internal controls, or implementation. **The Open Window.** An unpatched Windows server, a weak firewall rule, or a poorly written web application. It is the flaw waiting to be abused.
#### Exploit
A particular attack. It is named this way because these attacks exploit system vulnerabilities. **Climbing through the Window.** The actual code, script, or technique you run to take advantage of the vulnerability.
#### Intrusion
A deliberate security incident in which an intruder gains access to a system without authorization. **You are Inside.** The exploit was successful. You now have unauthorized access to the network or the specific machine.
#### Zero Day
A previously unknown system vulnerability with the potential of exploitation without risk of detection. **The Ghost Weapon.** A vulnerability that the software vendor (like Microsoft or Cisco) does not even know exists yet. Because it is unknown, there is no patch and antivirus software has no signature to detect it. If you have a true Zero Day, you are practically invisible.

>A **Threat** (The burglar) sees a **Vulnerability** (an unlocked door). They use an **Exploit** (turning the handle) to cause an **Intrusion** (stepping inside). This creates an **Incident** (the alarm goes off). If they steal the files on the desk, it becomes a **Breach**.
## The Importance of Business Continuity
The intent of a business continuity plan is to sustain business operations while recovering from a significant disruption. 

*Incident Response (IR) fixes the problem. Business Continuity (BC) keeps the company breathing while the problem is being fixed.*

### The Nigerian Scenario: The Undersea Cable Cut
Imagine a massive disruption like the undersea fiber optic cables getting severed in the Atlantic Ocean, causing a massive internet blackout across Lagos.
- **The Incident Response (IR):** The specialized engineers getting on a ship, finding the broken fiber optic cable in the ocean, and physically splicing it back together. Their goal is to fix the disruption.
- **The Business Continuity (BC):** The executives at a major commercial bank in Marina realizing their branches can no longer process withdrawals. They open the Business Continuity Plan, which instructs them to immediately route all critical banking traffic through backup VSAT (satellite) links and prioritize offline USSD transactions. Their goal is to ensure customers can still buy food and fuel, keeping the bank in business even though the primary internet is dead.

*The BCP is the survival guide. It acknowledges that the environment is completely broken, but asks: "How do we keep our operations running today?"*

### Here are critical BCP components
#### 1. Communication is King (The Phone Tree)
When a disaster strikes, normal communication often dies. If the internet is down, the company cannot use Slack, Microsoft Teams, or WhatsApp.
- **The Phone Tree:** A hierarchical list of who calls whom. The CEO calls the CISO and the COO. The CISO calls the SOC Manager. The SOC Manager calls the analysts. If the SOC Manager doesn't pick up, the checklist tells the CISO exactly who the backup contact is. You never waste time wondering who is in charge.
- **Out-of-Band Communications:** Your text mentions special emergency networks. In Nigeria, critical infrastructure like a central bank or major hospital won't just rely on MTN or Airtel. If the national grid collapses, they have backup satellite phones, dedicated radio frequencies, or private microwave links to coordinate with suppliers and law enforcement.
#### 2. Checklists (The Pilot's Rule)
During a crisis, humans panic. Even senior executives make foolish mistakes under pressure.
- A pilot with 20,000 hours of flight time still reads a printed checklist before takeoff because human memory fails under stress. A BCP removes the need to "think" or brainstorm during a disaster. You just open the binder and execute Step 1, then Step 2.
#### 3. Executive Authority
You cannot run a BCP with just IT staff. You must have senior management in the room.
- **Why?** Because surviving a disaster requires making massive business decisions. If a company needs to authorize ₦50,000,000 immediately to buy emergency server space, or if they need to make the brutal decision to intentionally shut down the customer-facing website to protect the internal databases, a junior SOC analyst does not have the authority to do that. Executives must be present to shift priorities and authorize actions.
## Components of Business Continuity Plan
Business continuity planning (BCP) is the proactive development of procedures to restore business operations after a disaster or other significant disruption to the organization.

>**It is not an IT plan. It is a business survival plan.**

As an offensive security student, you are used to staring at terminal screens, breaking web apps, and bypassing firewalls. But if you take down a company's network, the executives don't just sit around waiting for IT to fix it. They open the BCP binder to figure out how to keep making money while the network is dead.

The text emphasizes that BCP is **proactive**. You cannot build a parachute while you are falling.

Here is how you translate the core components of a BCP into real-world, Lagos-based scenarios for your vault:

## The Anatomy of a Business Continuity Plan

A proper BCP is basically a massive "In Case of Emergency, Break Glass" manual. If a disaster hits, nobody should be guessing what to do.

| **The BCP Component**               | **The Textbook Definition**                                     | **The Lagos Reality**                                                                                                                                                                                                                                                           |
| ----------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **The Trigger (How/When to enact)** | Criteria defining exactly when the plan becomes active.         | If the IKEDC/Eko Disco grid goes down for 30 minutes, that is normal Tuesday traffic. You don't declare a corporate disaster. But if your main server room in Ikeja floods during the rainy season and will be offline for 48 hours, _that_ is the trigger to activate the BCP. |
| **Notification & Call Trees**       | Hierarchical alerting systems to enact the plan.                | If the primary internal network is down, the SOC manager sends an SMS broadcast to the executive WhatsApp group. The CEO calls the COO. The COO calls the branch managers. Everyone knows exactly who they are supposed to call next.                                           |
| **Designation of Authority**        | Guidance on which managers have specific decision-making power. | If the company needs to spend ₦20,000,000 instantly to rent emergency office space, a junior manager cannot authorize that. The BCP explicitly names which executives have emergency financial authority so the company doesn't stall waiting for approvals.                    |
| **Immediate Response Checklists**   | Step-by-step safety and security procedures.                    | Step 1: Evacuate the building. <br>Step 2: Ensure the diesel generators are shut off to prevent electrical fires. <br>Step 3: Call the Lagos State Fire Service. No thinking required, just reading.                                                                            |
| **Supply Chain Contacts**           | Alternative contact numbers for vendors and partners.           | If a major logistics company like GIGM gets hit by a cyberattack and their app goes down, they still need to move packages. The BCP contains the personal phone numbers of their third-party truck drivers and fuel suppliers so they can coordinate routes manually.           |

## Why "Cross-Functional" Matters
The text notes that members from _across_ the organization must participate in creating the BCP.

- **The Trap:** If only the IT department writes the BCP, they will focus purely on servers and firewalls.
    
- **The Reality:** If a massive supermarket chain in Lagos loses its entire digital inventory network, the IT guys will be focused on fixing the SQL database. But the **Store Manager** needs to know: _"How do we process checkout for the 50 customers standing in line right now?"_
    
- **The Cross-Functional Solution:** Because the Store Manager was involved in writing the BCP, the plan includes a directive to pull out battery-powered calculators and manual receipt books, allowing the store to stay open and process cash payments while IT fights the fire in the background.

This is exactly why technology must align with business needs, not the other way around.

## Business Continuity in Action
This is where the theory hits the pavement. A Business Continuity Plan (BCP) is useless if it only exists in a binder; it has to work when the building is literally on fire.

The most important concept introduced in this section is the **Business Impact Analysis (BIA)**. *The BIA is the cheat sheet that tells executives exactly how long the company can survive without a specific department before it goes bankrupt.*

Here is how this exact textbook scenario plays out in the Lagos tech ecosystem.

### The Lagos Scenario: The Yaba Fire Outbreak

Imagine a fast-growing B2B SaaS company based in a multi-story building in Yaba. They provide logistics software to trucking companies. At 2:00 AM on a Sunday, a severe electrical surge causes a fire that completely guts the 3rd floor, which houses their Billing and Accounts Receivable department. The servers (on the 1st floor) are perfectly fine, but the billing team’s computers, physical contracts, and office space are ash.

Because they did a BIA last year, there is zero panic. Here is why the BCP succeeds:

#### 1. The BIA Dictated the Priority
During the Business Impact Analysis phase months ago, the executives asked a brutal question: _"If this department disappears, when do we die?"_

- **Engineering/Servers:** If the servers go down, the trucking clients can't route their deliveries. The company dies in **1 hour**.
    
- **Billing Department:** If billing goes down, the company just can't send invoices or process payments this week. The trucking software still works. Because the company has solid cash reserves in the bank to cover payroll, they realize they can survive for **2 weeks** without the billing department.
#### 2. The Alternate Site Agreement
Because the BIA proved they had a 2-week survival window, they didn't waste money building an exact, expensive replica of the billing office. Instead, they pre-signed a contract with a co-working space in Ikeja (like a Regus or Hub360). The contract guarantees that if a disaster happens, the billing staff can move into the Ikeja hub within 5 days.
#### 3. The Operational Workaround
For those 5 days, clients will naturally call asking, _"Where is my invoice for this month?"_ The BCP already accounted for this. The Customer Support team (working remotely) is given a script: _"We are upgrading our financial systems this week; your invoice will be sent next Monday with no late penalties."_
### The Ultimate Goal Achieved
Look at the result: The building burned down, but the clients never noticed a service disruption, the software kept running, and the company didn't lose a single customer.

That is what a successful BCP looks like. It is not about stopping the fire; it is about masking the chaos so the business keeps moving.
### Exam Focus: The BIA
For the CC exam, you must remember that the **Business Impact Analysis (BIA)** is always the _first_ step in continuity planning. You cannot write a BCP until the BIA tells you which departments are critical and which ones can wait.
