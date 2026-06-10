# Day 01 - Introduction to Cyber Forensics

## Real-world vs. Virtual-world Crime

* Conventional crimes happen in the real world.
* Cyber crimes occur in a virtual environment, creating unique challenges in investigation and evidence collection.

---

# Types of Cyber Crimes

| Against Organizations   | Against Persons | Against Country |
| ----------------------- | --------------- | --------------- |
| Hacking                 | Cyber Stalking  | Cyber Terrorism |
| Denial of Service (DoS) | Phishing        | Cyber Warfare   |
| Virus/Worm Attacks      | Identity Theft  |                 |
| IPR Violations          | Email Hijacking |                 |
| Stealing Trade Secrets  | Defamation      |                 |
| Website Defacement      | Spamming        |                 |
|                         | Internet Fraud  |                 |
|                         | Gambling        |                 |
|                         | Pornography     |                 |
|                         | Software Piracy |                 |

---

# Legal Framework & Evidence

## Laws in India

* Information Technology (IT) Act
* Bharatiya Nyaya Sanhita (BNS)

## Court Requirement

Evidence must be collected and presented in a legally accepted manner.

---

# What is Cyber Forensics?

Cyber Forensics is the process of:

* Identifying
* Extracting
* Preserving
* Analyzing
* Presenting

digital evidence in a legally accepted manner.

---

# Cardinal Rules (Golden Rules)

* Never mishandle evidence.
* Never work on original evidence.
* Use proper forensic software utilities.
* Never trust the suspect operating system.
* Document everything.

---

# Steps of Cyber Forensics

## 1. Identification

Determine:

* What evidence exists
* Where it exists
* How it is stored
* Retention duration

Examples:

* Standalone systems
* Servers
* Laptops
* Handheld devices
* Remote storage

Includes testimonial evidence such as:

* Interviews
* Personnel records

---

## 2. Seizure

Capturing suspect systems or storage media systematically.

### Hashing Algorithms Used

* MD5
* SHA-1
* SHA-2

Purpose:

* Verify integrity of evidence.

---

## 3. Acquisition

Creating a bit-stream image:

* Sector-by-sector copy
* Performed in write-blocked environment
* Destination drive must have larger capacity than source

---

## 4. Authentication

Verify integrity using hash comparison.

### Rule

Original hash = Acquired image hash

---

## 5. Analysis

Methodical examination of digital evidence.

Can reveal:

* Deleted files
* Browsing history
* Downloaded content
* Last access timestamps
* Fabricated evidence

### Important

Analysis must be repeatable.

---

## 6. Presentation

Present findings in court using simple language.

Must include:

* Tools used
* Examiner details
* Hash results
* Media information
* Photographs

---

## 7. Preservation

Maintain chain of custody.

Requirements:

* No modification to evidence
* Complete evidence copy
* Reliable acquisition process
* Secure evidence storage

---

# Key Tools & Techniques

## Hashing Algorithms

* MD5 (Message Digest)
* SHA (Secure Hash Algorithm)

## Bit Stream Imaging

Sector-by-sector forensic copy preserving disk geometry.

## Write Blocking

Prevents modification of original evidence during acquisition.

---

# Important Concepts

## Hashing Example

"Hang him not, kill him"

and

"Hang him, not kill him"

produce completely different hash values.

### Conclusion

Even a small change in data creates a completely different hash.

---

# Chain of Custody

Chain of custody must be maintained during:

* Transportation
* Storage
* Handling
* Examination

---

# Packaging & Transportation Tips

* Use anti-static bubble wrap for storage media.
* Secure systems properly during transportation.
* Avoid magnetic fields and electromagnetic interference.

---

# Conclusion

Cyber Forensics is not only technical but also a legal process.

Every action must be:

* Documented
* Repeatable
* Court admissible
