## Encryption Overview
Cryptography is foundational to modern digital operations, protecting business transactions and utilizing digital signatures to verify the authenticity of software creators or suppliers. Furthermore, digitally signed contracts exchanged via email prevent senders from later repudiating their agreements.
### Core Definitions and Objectives
- **Primary Objective**: An encryption system transforms an original set of data (**plaintext**) into an otherwise unintelligible encrypted form (**ciphertext**).
- **Secret Protection**: Cryptography keeps information content secret and unintelligible to anyone lacking the decryption key.
- **Encryption System**: Defined as a set of hardware, software, algorithms, control parameters, and operational methods that collectively provide encryption services.
### Core Security Services Provided by Cryptography
- **Confidentiality**: *Cryptography* provides confidentiality by hiding or obscuring a message so it cannot be understood by anyone except the intended recipient, keeping sensitive information hidden from unauthorized parties.
- **Integrity**: Implemented via hash functions and digital algorithms to allow recipients to verify that a message has not been altered by malice or error. Any deliberate or accidental change made to the message results in a completely different output value.

![[Encryption Overview.png]]

### Understanding Plaintext
Plaintext is data or messages in their normal, unencrypted form and format, where meaning or value is immediately available to an end user or process. It encompasses diverse digital formats:
- Images, audio, or video files in raw or compressed forms.
- Non-renderable text and numeric data, with or without markup language elements and metadata.
- Database files, records, and individual fields within a database.
- Any data represented in digital form for computer processing, transmission, and storage.
- _Note_: Plaintext can be any digital file format and is not restricted to human-readable text.

### Encryption System
An encryption system is defined as a set of hardware, software, algorithms, control parameters, and operational methods that provide a set of encryption services.

To understand how these components work together in practice, consider a secure armored transit and vault service operated by a cash-in-transit company in Lagos (such as Bankers Warehouse moving physical currency for commercial banks).

An armored van service is not just a vehicle with a lock; it is a complete ecosystem. Breaking down an enterprise encryption system reveals a direct parallel to this physical security operation:

- **Hardware**: In digital encryption, this includes *Hardware Security Modules (HSMs)* or secure cryptographic processors built into servers to securely store and process encryption keys. In our physical analogy, this is the armored bullion van itself, the reinforced vaults, and the physical GPS tracking hardware.
    
- **Software**: In cryptography, this is the operating system modules, *cryptographic libraries,* and applications that execute the encryption commands. In our analogy, this is the dispatch management software and digital logging dashboards used to monitor transit.
    
- **Algorithms**: These are the mathematical formulas (*such as AES-256 or RSA*) that perform the actual transformation of plaintext into unintelligible ciphertext. In the physical analogy, this represents the strict structural design and engineering specifications of the vault doors and multi-ton locking mechanisms.
    
- **Control Parameters**: These are the configuration settings, such as key length (e.g., *128-bit vs. 256-bit keys*) and initialization vectors. In our analogy, this corresponds to the specific digital combination codes, biometric access tokens, and time-lock settings required to open the vault.
    
- **Operational Methods**: These are the *policies, procedures, and Standard Operating Procedures (SOPs)* governing how keys are generated, rotated, and retired. In our analogy, this is the mandatory protocol that requires armed guards, two-person integrity rules, and defined secure routes between Lagos Island and Ikeja.

When all these elements function together, they deliver core encryption services like confidentiality and integrity.

### Nigerian Operational Scenario
A commercial bank in Lagos utilizes cryptographic protocols when transmitting customer loan applications and financial statements over API channels. The raw application data (**plaintext**) is encrypted using *AES algorithms* into **ciphertext** before transmission. If a malicious actor intercepts the packet mid-transit, the data remains unintelligible without the decryption keys. Additionally, cryptographic hash functions verify message integrity upon arrival, ensuring the file has not been tampered with by an adversary.

>***Cryptography*** is a broad method used to protect information by turning readable data into secret code that can only be unlocked with a key, ensuring confidentiality.
>
>***Hashing,*** on the other hand, is a one-way mathematical function that creates a unique data fingerprint used to check if a message has been altered, ensuring integrity. 
>
>While cryptography locks data away so unauthorized people cannot read it, hashing works within encryption systems to prove the data remains exact and untampered.

## Hashing
Hashing takes an input set of data of almost arbitrary size and returns a fixed-length result called the *hash value*. 

A *hash function* is the algorithm used to perform this transformation. When used with cryptographically strong hash algorithms, this is the most common method of ensuring message integrity today.
### Uses in Computing and Security
Hashes have many uses in computing and security, one of which is to create a message digest by applying such a hash function to the plaintext body of a message.

*To be useful and secure, a cryptographic hash function must demonstrate five main properties:*

- **Useful:** It is easy to compute the hash value for any given message.
- **Non-reversible:** It is computationally infeasible to reverse the hash process or otherwise derive the original plaintext of a message from its hash value, unlike an encryption process, for which there must be a corresponding decryption process.
- **Content integrity assurance:** It is computationally infeasible to modify a message such that reapplying the hash function will produce the original hash value.
- **Unique:** It is computationally infeasible to find two or more different, sensible messages that hash to the same value.
- **Deterministic:** The same input will always generate the same hash, when using the same hashing algorithm.
### Cryptographic Hash Functions
Cryptographic hash functions support digital signatures, message authentication codes, and other authorization forms.
- **Fingerprinting**: They act as fingerprinting values to check if data has been modified by malice or error.
- **One-Way Property**: The algorithm converts input data (such as a large document, program, or file) into a fixed-size digest, but the process is strictly one-way, the original message cannot be recreated from the output.
### The Hashing Workflow and the Avalanche Effect
- **Data Flow**: The process moves from variable data input through a hashing algorithm to yield a fixed bit-size data output (the digest).
- **Sender and Receiver Flow**: Originators generate a digest from a message and send both; receivers run the received message through the same hashing algorithm and verify the resulting digest against the sender's digest.
- **Sensitivity to Change**: A one-bit change in an input message results in a completely different hash output value. Even a tiny modification completely alters the resulting digest, making tampering immediately obvious.

>Hashing puts data through a hash function or algorithm to create an alphanumeric set of figures, or a digest that means nothing to people who might view it.
>
>No matter how long the input is, the hash digest will be the same number of characters.
>
>Before we go live with a software product provided by a third party, for instance, we have to make sure no one has changed anything since it was tested by you and the programmer. They will usually send you the digest of their code and you compare that to the original. This is also known as a ***checksum***.

## Asymmetric Encryption
***Asymmetric*** encryption uses *one key to encrypt and a different key to decrypt* the input plaintext. This is in stark contrast to symmetric encryption, which *uses the same key* to encrypt and decrypt.

>Asymmetric cryptography uses a two-key system to secure digital communications without requiring a prior secure key exchange.

To maintain high security, key pairs are typically generated automatically by *cryptographic applications* or *Public Key Infrastructure (PKI)* implementations rather than manually by users.

- **Public Key:** One half of the key pair that can be freely distributed and shared publicly via corporate websites or key servers. Anything encrypted using a recipient's public key can only be decrypted by that specific recipient.

- **Private Key:** The other half of the key pair, kept strictly secret and known only to the key holder.
### Major Advantages
- **Key Distribution:** Asymmetric eliminates the logistical challenge of securely distributing secret keys beforehand across untrusted networks.
- **Scalability:** Scales efficiently as the number of users grows. For $N$ users, asymmetric encryption requires only $2N$ keys (one public and one private per user), which is significantly more manageable than symmetric encryption as organizational size increases.
- **Advanced Security Services:** Provides features beyond simple confidentiality, including data integrity, access control, and **non-repudiation** (ensuring a sender cannot deny sending a message).
### The Primary Disadvantage
- **Performance Speed:** Asymmetric algorithms are computationally *intensive*, making them *extremely slow* compared to symmetric encryption. Because of this speed limitation, they are impractical for encrypting large volumes of daily operational data.

>Let’s use a secure drop-box analogy to see how this works in practice.
>
>Imagine a bank branch with a heavy steel drop-box mounted outside.
>
>- **The Public Key 🔓:** The open slot on the box is available to everyone. Anyone in the public can write a message, fold it up, and drop it through the slot. Once it falls inside, the sender no longer has access to it.
>- **The Private Key 🔑:** Only the bank manager holds the physical key to unlock the main door and read the collected messages.
>
>If an attacker walks by, they can see the drop-box, but they can never reach inside to read what customers sent because they lack the manager's private key.

## Symmetric Encryption
The central characteristic of a symmetric algorithm is that it uses *the same key in both the encryption and the decryption processes.* It could be said that the decryption process is a mirror image of the encryption process. While it is computationally fast and efficient for large datasets, it introduces distinct operational challenges.
### Core Challenges of Symmetric Encryption
- **Key Distribution and Out-of-Band Exchange:** Because the key cannot be transmitted across the same network channel as the encrypted data (or a Man-in-the-Middle could intercept it), organizations must use *out-of-band channels* such as a secure physical courier, telephone call, or separate secure network to distribute the key.
- **Compromised Paths :** If a communication path is suspected of being intercepted, the key cannot safely be shared or updated over that same path.
- **Lack of Non-Repudiation:** Anyone possessing the shared key can decrypt, read, and alter the message. Because both parties hold the exact same key, it cannot prove which specific person sent a message, failing to provide non-repudiation.
- **Scalability Limitations:** The number of required keys grows exponentially as users increase. For $N$ users to communicate securely in pairs, the formula $\frac{N(N-1)}{2}$ applies. For example, an organization of 1,000 employees requires 499,500 unique keys to ensure private pairwise communication.
### Real-World Scenario: Inter-Branch Financial Transfers
Imagine a commercial bank in Lagos needing to transmit daily ledger backups from an Ikeja branch to the central data center on Victoria Island.
1. **The Setup:** Both the Ikeja branch manager and the data center lead must possess the exact same secret encryption key to lock and unlock the backup files.
2. **The Distribution Challenge:** They cannot email this key over the standard internet connection without risking interception. Instead, an IT security officer must physically deliver the key on a secure device via an armored courier *(out-of-band distribution)*.
3. **The Scalability Issue:** If every single one of the bank's 50 branches needed a unique pairwise shared key to communicate securely with every other branch, managing the sheer volume of unique keys would quickly overwhelm IT staff.

### Primary uses of symmetric algorithms:
- Encrypting bulk data (e.g., backups, hard drives, portable media)
- Encrypting messages traversing communications channels (e.g., IPsec, TLS)
- Streaming large-scale, time-sensitive data (e.g., audio/video materials, gaming)
### Other names for symmetric algorithms:
- Same key
- Secret key
- Single key
- Session key
- Shared key

![[Pasted image 20261029225708.png]]

>This image illustrates **symmetric encryption** using a classic substitution cipher and a decoding ring.
>- **Substitution Cipher**: This method replaces each letter of the plaintext with another letter further down the alphabet. In modern digital systems, this exact substitution concept is applied to binary bits instead of letters.
>- **Cryptovariable**: The secret key or rotation offset represented by how the inner and outer rings are aligned relative to each other determines how characters are substituted.
>- **Shared Secret**: Because it is **symmetric encryption**, both the sender and the receiver must possess and use the exact same ring alignment (the shared secret key) to both lock and unlock the message.
