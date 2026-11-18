## The Goal of Disaster Recovery
Disaster recovery planning steps in where business continuity (BC) leaves off.

When a disaster strikes or an interruption of business activities occurs, the disaster recovery plan (DRP) guides the actions of emergency response personnel until the end goal is reached, which is to see the business restored to full last-known reliable operations.

If Incident Response (IR) is the paramedics stopping the bleeding, and Business Continuity (BC) is the life-support machine keeping the patient breathing, then **Disaster Recovery (DR)** is the physical therapy that gets the patient walking again.

- **Incident Response (The Attack):** Focused entirely on the malicious event. Kicking the hacker out, stopping the malware, and patching the vulnerability.
    
- **Business Continuity (The Operations):** Focused entirely on the business mission. Using manual workarounds, paper maps, or backup generators to ensure the company doesn't go bankrupt today.
    
- **Disaster Recovery (The Technology):** Focused entirely on **IT and communications**. Rebuilding servers, restoring databases from backups, and bringing the primary data center back online.

### IR, BC, and DR Comparison

|Metric|Incident Response (IR)|Business Continuity (BC)|Disaster Recovery (DR)|
|---|---|---|---|
|**Focus Area**|Security Threat|Business Ops|IT Infrastructure|
|**Primary Goal**|Stop Breach|Maintain Services|Restore Data|
|**Example Action**|Isolating Host|Alternate Site Ops|Restoring Backups|
|**Timeline**|Minutes/Hours|Ongoing|Hours/Days|
### The Lagos Scenario: Completing the Story
Let’s go back to the Oshodi Logistics company that got hit with ransomware to see how the final phase looks.
- **The Incident Response:** The SOC isolated the infected servers and deleted the ransomware payload from the network.
- **The Business Continuity:** The dispatchers used whiteboards and two-way radios to keep the delivery trucks moving while the computers were dead.
- **The Disaster Recovery:** This is where the DR team takes over. The IT engineers format the corrupted hard drives. They pull the clean, unencrypted database backups from their off-site storage in Abuja. They reinstall the operating systems, reload the delivery data, and verify that the routing software works perfectly.

The goal of the DR plan is achieved the moment the dispatchers can throw away their paper maps and log back into the digital routing system. The text defines this exact moment as reaching **"full last-known reliable operations."**

>If a question asks about fixing a server, restoring data, or rebuilding IT infrastructure after a crash, the answer is **Disaster Recovery**. If it asks about keeping the business running _during_ the crash, the answer is **Business Continuity**.

This section highlights two of the biggest nightmares for a Disaster Recovery (DR) team. As an offensive security student, this is exactly what you are trying to exploit: the gap between what a company _thinks_ they backed up, and what they _actually_ need to survive.

If an organization's DR plan only consists of "we back up the server every night," they are going to fail. Here is how you break down these two real-world concepts for your vault, anchored in Nigerian scenarios.
## 1. The "Dwell Time" Trap (Infected Backups)
In the movies, hackers break in, steal data, and immediately trigger an alarm. In reality, Advanced Persistent Threats (APTs) are patient. The time between a hacker breaching a network and the company actually noticing is called **Dwell Time** (in your textbook's example, 260 days).

- **The Lagos Microfinance Scenario:** A hacker compromises a microfinance bank in Victoria Island in January by installing a silent backdoor. The hacker does nothing for nine months, just quietly watching. In October, they finally detonate the ransomware, encrypting everything.
- **The DR Failure:** The bank's DR team panics and restores the system using last week's backup. But because the hacker has been inside since January, _last week's backup contains the hacker's backdoor._ The moment the system comes back online, the hacker immediately encrypts it again.
- **The Solution:** A proper DR plan requires **multiple retention periods**. You don't just keep backups from yesterday; you keep monthly and yearly archives so you can roll back to a clean state from a year ago if necessary, and then manually rebuild the missing data.
## 2. The Web of Dependencies (The Domino Effect)
Modern enterprise networks are not just one big computer. They are dozens of different systems constantly whispering to each other. If you don't restore them in the correct order, the whole network shatters.
- **The General Hospital Scenario:** Imagine a massive general hospital in Surulere.
    1. A patient walks in and gives their details to the **Registration Database**.
    2. The doctor orders a blood test, so that data flows to the **Laboratory Database**.
    3. The patient gets an X-ray, sending data to the **Radiology Database**.
- **The DR Failure:** A server crash wipes out the entire hospital network. The IT team rushes to restore the Laboratory and Radiology databases first because they seem "more critical" than the front desk.
- **The Result:** The lab systems crash immediately upon booting up. Why? Because the lab database is trying to verify patient IDs against the Registration database, which hasn't been restored yet.
- **The Solution:** The DR plan must document the **flow of data**. You must know exactly which system depends on another, and restore them in the exact sequence required to keep the dependencies intact.
### The Key Takeaway for the Exam
Disaster Recovery is not just about copying files. It is about **Time** (having historical backups to avoid reinfection) and **Architecture** (knowing the exact order to turn the machines back on).
## Components of Disaster Recovery
This section highlights a critical psychological reality of disaster management: **When everything is on fire, nobody wants to read a 500-page manual.**

A Disaster Recovery Plan (DRP) is not a single, massive textbook that every employee memorizes. It is modular. It is broken up into highly specific, bite-sized pieces so that every person gets _exactly_ the information they need to do their job, and nothing more.

Think of it like a military operation. The General needs the entire battle map. The sniper only needs the coordinates and the wind speed. If you give the sniper the entire battle map, they get distracted and miss the shot.

Here is how you categorize the DRP documents for the exam:

## The Modular DRP: Who Gets What?

During a catastrophic failure, the atmosphere is pure chaos. ISC2 expects you to know exactly which document to hand to which employee to cut through that chaos.

- **The Full Copy (The Master Blueprint):** Only the Disaster Recovery Coordinator (the "General") gets this. They need to see how every single moving part connects so they can orchestrate the entire recovery effort.
    
- **Technical Guides & Checklists (The IT Sniper):** The systems engineers rebuilding the database do not care what the CEO is telling the press. They need a highly technical, step-by-step checklist of exact command-line codes and server configurations to bring the alternate data center online.
    
- **Department-Specific Plans (The Ground Troops):** The HR department gets a specific plan that only covers how to restore the payroll files. The Logistics department gets a plan that only covers how to restore the shipping manifests. They stay in their own lanes.
    
- **Executive Summary (The Boardroom):** Senior management gets a high-level overview. They don't need to know the IP addresses of the backup servers; they just need to know the estimated time to recovery and the financial impact.
    
- **Public Relations Guidelines (The Shield):** This is crucial. When a massive bank in Nigeria goes offline, Twitter (X) erupts immediately. The PR and Communications team needs simple, non-technical talking points to release to the public. _Why?_ Because if PR has to call the IT engineers to ask for updates, they are distracting the exact people who are trying to fix the problem.
### The Exam Trap
ISC2 will often present a scenario where an executive or a PR manager is given a highly technical IT checklist, or a system administrator is handed the executive summary. Your job is to recognize that giving the wrong document to the wrong person delays the recovery.
