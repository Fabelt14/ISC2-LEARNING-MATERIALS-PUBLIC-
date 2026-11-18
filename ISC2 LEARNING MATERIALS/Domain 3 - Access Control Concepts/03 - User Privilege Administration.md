`Tags: #CC #isc2`
## Privileged Access Management
- **Privileged Access Management (PAM):** The tools, policies, and processes specifically designed to secure, manage, and monitor high-level accounts (like "Administrator," "Root," or "Domain Admin").
- **Static Privileges:** Admin rights that are permanently attached to an account and left "on" 24/7. This is exactly what caused the ransomware disaster in your ABC, Inc. notes.
- **Just-in-Time (JIT) Access:** A core feature of PAM where admin rights are granted _only_ for the exact timeframe required to complete a specific task, and then automatically revoked.
- **Separation of Privileges:** The practice of assigning an IT worker a standard, restricted account for daily tasks (checking email, browsing the web) and a completely separate, heavily monitored account for administrative work.
### The Nigerian / African Context Scenario
Imagine a major payment processing company in **Abuja**. The Lead Systems Engineer is highly trusted.
- **The Bad Way (Static Privileges):** The engineer logs into his work laptop using his permanent "Super Admin" account. During his lunch break, he checks his personal email, clicks a phishing link disguised as a Jumia delivery receipt, and downloads malware. Because his account is currently running with "Super Admin" rights, the malware instantly inherits those rights and deletes the company's entire payment database.
- **The ISC2 Way (JIT and PAM):** The engineer logs into his laptop with a standard user account. When he clicks the phishing link, the malware tries to delete the database but gets a "Permission Denied" error. Later, when he actually needs to fix a server, he logs into a secure PAM portal, requests temporary admin access to that specific server for exactly one hour, completes the fix, and the system automatically revokes the rights.
### The ISC2 Exam Traps Exposed
- **The "Trusted Insider" Trap:** The exam will describe an IT Director who has worked at a company for 20 years with a flawless record, suggesting it is safe to give them permanent 24/7 admin rights to save time. **Do not fall for it.** PAM isn't just about stopping bad employees; it is about stopping malware that hijacks a good employee's account.
- **The "Shared Password" Trap:** A scenario might suggest that keeping the "root" password in a secure, locked spreadsheet that all five IT staff can use is a form of PAM. **No.** Shared accounts destroy accountability. True PAM requires individuals to request access so the system logs exactly _who_ used the privilege.

> Never wear your King's crown to the market. IT administrators should use a regular, restricted account for regular daily tasks. They should only put on the "Super Admin" hat when they are actively performing maintenance, and the system should automatically snatch that hat back the moment they are done.

## Privileged Accounts
Privileged accounts are those with permissions beyond those of normal users, such as managers and administrators.
- **Privileged Account:** Any account with elevated rights (like a Sysadmin, root, or specialized Help Desk role) that can bypass standard security restrictions.
- **Deterrent Control:** The text mentions that extensive logging deters untoward activity. If an employee knows their every click is recorded, they are less likely to attempt insider fraud.
- **Granular Permissions:** This is the core of the Help Desk example. Instead of giving a user broad "Domain Admin" rights, you give them a highly specific, restricted capability (e.g., _only_ resetting passwords). This is the exact application of the **Principle of Least Privilege**.
- **Trust Verification (Administrative Controls):** The non-technical side of managing high-level accounts, including deep background checks, financial investigations, and strict Non-Disclosure Agreements (NDAs).
### Classes of Privileged Users
A **Privileged Account** is simply a "super-user" account. It has the power to change system settings, see private data, or bypass regular security rules.

Different roles need different types of privileged accounts:
- **Systems Administrators:** The "mechanics" of the IT world. They need deep access to keep servers running, install applications, and manage network performance.
- **Help Desk / IT Support:** The "first responders." They need specific, limited power to fix daily employee problems, like unlocking endpoints or resetting passwords.
- **Security Analysts:** The "investigators." They need rapid, sweeping access across the entire network to hunt for hackers and review logs.
- **Project-Based Users:** External consultants or temporary teams who need temporary high-level access to a specific database or app just for the duration of a contract.
### Moderating the Risk
Because these accounts can destroy a company if misused, ISC2 requires specific measures to control them. Let's look at this through the lens of a **major commercial bank in Lagos**:

- **More Extensive Logging:**
    - _The Concept:_ Recording every single click and keystroke.
    - _The Context:_ If a regular bank teller accesses a customer's account, the system notes the time. If the Lead Database Admin accesses the core banking database, the system records the time, the exact SQL commands typed, and the IP address. It acts as a deterrent because the admin knows they are being watched.
- **Stringent Access Control (MFA & JIT):**
    - _The Concept:_ Making it much harder to log in.
    - _The Context:_ A regular employee might just use a password and a token to check email. A privileged admin must use a hardware security key, a biometric scan, and can only activate their admin powers for exactly 30 minutes (Just-In-Time access) to fix a server.
- **Deeper Trust Verification:**
    - _The Concept:_ Administrative controls like background checks and NDAs.
    - _The Context:_ You wouldn't hand the keys to the bank vault to someone without a guarantor. High-level IT staff must pass criminal background checks and financial audits to ensure they aren't desperate for money (which makes them targets for bribery).
- **More Auditing:**
    - _The Concept:_ Actively reviewing the logs to find bad behavior.
    - _The Context:_ The bank's security team doesn't just collect the Help Desk logs; they actively read them every Friday to ensure no one is resetting passwords for accounts they shouldn't be touching.
### The Nigerian / African Context Scenario
Imagine a major Telecom provider in **Abuja**. Their IT Help Desk receives hundreds of calls daily from staff who forgot their passwords.
- **The Flawed Approach:** To speed up resolution times, the IT Manager gives the Help Desk team full "Domain Admin" privileges. Now, a junior Help Desk worker can reset passwords, but they can also delete the CEO's email account or install unauthorized software.
- **The ISC2 Approach:** The Help Desk team is granted a custom role that _only_ allows password resets. Furthermore, the system logs every single reset. Every Friday, a Security Analyst audits those logs and compares them against the actual IT support tickets to ensure no Help Desk worker is secretly resetting passwords without a legitimate user request.
### The ISC2 Exam Traps Exposed
- **The "Technical-Only" Trap:** You will see exam questions asking how to secure privileged accounts. Your instinct might be to look only for technical answers (like MFA or Firewalls). Do not forget that **Trust Verification** (background checks and financial audits) is a highly valid administrative control for privileged users.
- **The "Efficiency vs. Security" Trap:** ISC2 will present a scenario where granting Help Desk workers Domain Admin rights "reduces customer wait times by 50%." They will ask if this is an acceptable risk. The answer is always **No**. Operational convenience never overrides the Principle of Least Privilege.
## Authorized Versus Unauthorized Personnel
### Simple Definitions: Identity & Lifecycle Management
To master this section, you need to understand the difference between proving who you are and what you are allowed to do, as well as the "Joiner, Mover, Leaver" HR lifecycle.

- **Authentication:** Proving you are who you say you are (e.g., swiping your ID badge or entering a password).
    
- **Authorization:** The system checking its rulebook (security matrix) to see what you are allowed to do _after_ you prove who you are (e.g., the door unlocking because your badge is on the approved list).
    
- **Provisioning / Deprovisioning:** The process of creating, updating, or removing an employee's digital accounts and access rights.
    
- **Privilege Creep (Permission Creep):** A major security risk where an employee slowly collects more and more system permissions as they change roles over time, without their old, unnecessary permissions ever being removed.
### The Telecoms Company in Victoria Island 🏢
Let's look at how this plays out at a major telecommunications headquarters in Lagos:

- **The Joiner (New Hire):** A new Customer Support Agent is hired. IT provisions an account giving them access _only_ to the customer billing software.

- **The Mover (Change of Position & Privilege Creep):** Two years later, the agent is promoted to IT Network Engineer. They are granted high-level access to the core routers. However, IT forgets to remove their old customer billing access. The employee now has unnecessary, overlapping access. This is **Privilege Creep**.
    
- **The "Copy Profile" Disaster:** The company hires a new Customer Support Agent to replace them. To save time, IT simply "clones" or copies the promoted engineer's current profile. The brand-new junior agent accidentally inherits high-level IT Network Engineer permissions! _This is why we use standard roles (Role-Based Access) instead of copying user profiles._
    
- **The Leaver (Separation of Employment):** The engineer eventually resigns. IT must immediately **disable** their account so they cannot log in from home. However, IT does _not_ delete the account yet, because the company's auditors need to review the engineer's past activity logs for the annual financial audit.
### The ISC2 Exam Traps Exposed 🪤
- **Trap 1: The "Delete Immediately" Trap:**
    - _The Trap:_ An employee is fired for stealing data. The exam will ask what the first step should be, offering "Delete the user account entirely" as a tempting choice.
    - _The Truth:_ **Never immediately delete an account.** You always **disable** it first. Deleting the account destroys the audit logs and orphaned files tied to that user, destroying your digital evidence.
- **Trap 2: Authentication vs. Authorization Mix-Up:**
    - _The Trap:_ The exam will describe a system checking a user's permissions in an Access Control List (ACL) to see if they can read a file, and ask what process this describes. "Authentication" will be an option.
    - _The Truth:_ Passwords, biometrics, and badges are _Authentication_. Checking permissions, matrices, and rules is _Authorization_.
- **Trap 3: The "Efficient Admin" Trap:**
    - _The Trap:_ The scenario will feature an overworked IT admin who clones an existing employee's account to quickly onboard five new hires, presenting it as a smart, time-saving business decision.
    - _The Truth:_ ISC2 considers account cloning a worst practice because it directly causes privilege creep. Always assign access based on a clean, standardized role.
