# Day 01 - Introduction to Cyber Forensics

## Overview

This session introduced the fundamentals of Cyber Forensics and Digital Evidence Handling.
The focus was on understanding cyber crimes, forensic investigation procedures, evidence preservation, and legal admissibility of digital evidence.

---

# Topics Covered

* Introduction to Cyber Forensics
* Real-world vs Virtual-world Crimes
* Types of Cyber Crimes
* Legal Framework (IT Act & BNS)
* Chain of Custody
* Data Acquisition
* Hashing & Integrity Verification
* Evidence Preservation
* Forensic Investigation Lifecycle

---

# Real-world vs Virtual-world Crime

| Real-world Crime           | Cyber Crime               |
| -------------------------- | ------------------------- |
| Physical environment       | Virtual environment       |
| Traditional evidence       | Digital evidence          |
| Easier evidence collection | Complex volatile evidence |
| Physical investigation     | Digital investigation     |

---

# Types of Cyber Crimes

## Against Organizations

* Hacking
* Denial of Service (DoS)
* Virus/Worm Attacks
* Website Defacement
* IPR Violations
* Trade Secret Theft

## Against Persons

* Cyber Stalking
* Phishing
* Identity Theft
* Email Hijacking
* Defamation
* Internet Fraud

## Against Country

* Cyber Terrorism
* Cyber Warfare

---

# Digital Forensics Process

## 1. Identification

Finding potential digital evidence sources.

## 2. Seizure

Securing digital devices and generating hash values.

## 3. Acquisition

Creating forensic bit-stream images using write-blocked environments.

## 4. Authentication

Verifying integrity using MD5/SHA hashes.

## 5. Analysis

Examining evidence for traces such as:

* Deleted files
* Browser history
* Downloads
* Access timestamps

## 6. Presentation

Presenting findings in a legally understandable format.

## 7. Preservation

Maintaining evidence integrity and chain of custody.

---

# Key Concepts Learned

## Hashing

Used to verify integrity of digital evidence.

### Algorithms

* MD5
* SHA-1
* SHA-256

### Important Principle

Even a tiny modification in data changes the hash completely.

---

## Bit Stream Imaging

Sector-by-sector forensic copy preserving:

* File structure
* Deleted data
* Slack space
* Disk geometry

---

## Write Blocking

Prevents any modification to original evidence during forensic acquisition.

---

# Important Legal Concepts

## Chain of Custody

Proper documentation of:

* Evidence handling
* Transportation
* Storage
* Examination

to maintain court admissibility.

---

# Packaging & Transportation

* Use anti-static bubble wrap
* Avoid electromagnetic interference
* Secure devices properly during transportation

---

# Key Learning Outcome

Understanding that Cyber Forensics is both:

* a technical process
* and a legal procedure

where every forensic action must be:

* documented
* repeatable
* legally admissible

