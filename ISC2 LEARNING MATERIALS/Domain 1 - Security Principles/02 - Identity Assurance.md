`Tags: #cybersecurity #cc #isc2 #Domain_Security`
# **Identification** and **Authentication**
- **Identification** is you walking up to the system and saying, _"I am Prime."_ (Entering your Username).
- **Authentication** is the system saying, _"Prove it."_ (Entering your Password).

> **Identification** = Username. **Authentication** = Password.

_Authentication is the process of verifying or proving the user’s identification_
## Three Factors of Authentication
To prove you are who you say you are, you can use three different categories of evidence.
- **Something you KNOW**: This is ***knowledge-based***. A secret value memorized by the user. such as _Passwords, PINs and Passphrases._ Your GTBank mobile app password, or the answer to ***What is your mother's maiden name?***
- **Something you HAVE**: This is ***token-based***. A physical or digital object in the user's possession. such as *Your Devices. Your physical physical ATM debit card, a [^2]YubiKey, or your smartphone receiving an SMS OTP, tokens*,
- **Something you ARE**: This is ***characteristic-based***. Biometrics or measurable human traits such as *Your Body, Scanning your fingerprint on your laptop, FaceID on your iPhone, or the BVN facial capture.*
## Methods of Authentication
- **Single-factor authentication (SFA):** This is the use of just one of the three available factors ***(something you know, something you have, something you are)*** to carry out the authentication process being requested. *Using only one of the three categories.*
- **Multi-Factor Authentication (MFA):** This is the use of two or more distinct instances of the three factors of authentication ***(something you know, something you have, something you are)*** for identity verification. *Using _two or more DIFFERENT_ categories.*

> If a system asks for your Password (Something you Know) and then asks for a 4-digit PIN (Something you Know), **this is still Single-Factor Authentication (SFA)**. Even though you typed two different things, they both came from the same category (Type 1). If a hacker installs a keylogger on your computer, they will steal both the password and the PIN at the same time.

## Real-World True MFA Scenarios
- **The ATM Machine:** This is the most common example of true MFA in Nigeria. To get cash, you must insert your physical ATM Card (**Something you Have**) AND type in your 4-digit PIN (**Something you Know**). If a thief steals your card, they don't have the PIN. If they shoulder-surf your PIN, they don't have the card.
- **Modern Cloud Access:** When you log into your AWS or GitHub account for your Atlas Scope project, you enter your password (**Something you Know**), and then the system forces you to open an Authenticator app on your phone to type in a rotating 6-digit code (**Something you Have**).

# What is Non-repudiation?
**Non-repudiation** is the legal and technical assurance that a subject cannot successfully deny having performed a specific action (like sending a message, approving a transfer, or signing a contract). The system proves beyond a shadow of a doubt that _you_ pushed the button, so you cannot play the "my account was hacked" card later to escape responsibility.

It is a combination of two things: 
**Strong Authentication (Who are you?) + Data Integrity (Was the action altered?) = Non-repudiation.**
_If the system can prove exactly who logged in (MFA) and prove exactly what they typed without it being changed (Hashing/Digital Signatures), the user is legally bound to that action._

> - **Purpose:** Ensures trust in digital and e-commerce transactions because participants are legally held accountable for their actions.
> - **Tools used:** Digital signatures, strict MFA, and secure audit logs.

### Real-World Scenarios
- **The Nigerian Fintech Dispute:** Imagine a customer uses a mobile money app like OPay or PalmPay to transfer ₦500,000 to buy a used car. The next day, having buyer's remorse, they call their bank and claim, "I never made that transfer! Someone must have cloned my phone. Reverse the charge!"
    - _How Non-repudiation stops them:_ The bank's security team pulls the logs. The logs show the transfer was initiated from the user's registered physical device (Something you Have), authorized using their specific fingerprint (Something you Are), and accompanied by a cryptographic digital signature. The user cannot repudiate (deny) the transaction. They are held legally responsible.
- **The Insider Threat:** An employee at a Lagos tech hub gets fired. On their way out the door, they log into the server and delete an entire project database. When the police question them, they say, "It wasn't me, anyone could have done it." If the company has strict, individual user accounts (no shared 'admin' passwords) and secure audit logs detailing every keystroke tied to that user's ID, they have non-repudiation.
- **The Offensive Security Angle:** Since you are studying penetration testing, think about why hackers always try to "clear the event logs" before disconnecting from a compromised server. They are actively trying to destroy non-repudiation so their actions cannot be traced back to them!




















[^2]: ![[Pasted image 20260602164131.png]]
