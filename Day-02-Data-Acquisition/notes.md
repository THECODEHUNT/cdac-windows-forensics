# Day 02 - Data Acquisition

## Introduction

Data Acquisition is one of the most critical phases of a digital forensic investigation. Before any analysis is performed, investigators must first collect digital evidence in a manner that preserves its integrity and admissibility in court.

The primary goal of acquisition is to create an exact copy of the original evidence without modifying the source media.

---

# What is Data Acquisition?

Data Acquisition is the process of collecting digital evidence from storage media, live systems, memory, or network sources while preserving the integrity of the original evidence.

Investigators never perform analysis directly on the original evidence. Instead, a forensic image is created and all analysis is conducted on that copy.

## Primary Rule

**Do not alter the original evidence.**

Any modification to evidence can affect its integrity and may render it inadmissible in court.

---

# Key Considerations During Acquisition

## Chain of Custody

A documented record showing:

* Who collected the evidence
* When it was collected
* Where it was collected
* Who accessed it
* How it was transported

Maintaining chain of custody is essential for legal admissibility.

---

## Write Blocking

Write blocking prevents accidental modification of evidence during acquisition.

A write blocker allows:

✔ Read Operations

❌ Write Operations

This ensures that timestamps, metadata, and file contents remain unchanged.

---

## Live vs Dead Acquisition

Investigators must determine whether acquisition should be performed while the system is running or after it has been powered off.

The decision depends on:

* Encryption status
* Running processes
* Business requirements
* Available evidence

---

## Hash Verification

Hash values act as digital fingerprints.

They are used to verify that:

```text
Original Evidence = Forensic Image
```

Any modification results in a completely different hash value.

---

# Order of Volatility (RFC 3227)

Volatility refers to how quickly data can disappear from a system.

Evidence should always be collected from the most volatile source to the least volatile source.

| Priority | Data Type             | Description                    |
| -------- | --------------------- | ------------------------------ |
| 1        | CPU Registers & Cache | Disappears within nanoseconds  |
| 2        | RAM                   | Lost after power off           |
| 3        | Network State         | Active connections, ARP tables |
| 4        | Running Processes     | Current process information    |
| 5        | Disk Storage          | Non-volatile storage           |
| 6        | Remote Logs & Backups | Least volatile evidence        |

### Example

Suppose a laptop uses full disk encryption.

The decryption key may exist only in RAM.

If the system is powered off before memory acquisition:

* Encryption keys disappear
* Evidence may become inaccessible

Correct sequence:

1. Capture RAM
2. Capture Network State
3. Acquire Disk Image

---

# Types of Data Acquisition

## Physical Acquisition

Physical acquisition creates a bit-stream copy of the entire storage device.

It includes:

* Allocated space
* Unallocated space
* Slack space
* Deleted files

### Advantages

* Most complete acquisition method
* Allows deleted file recovery
* Preserves hidden data

### Disadvantages

* Large image size
* Longer acquisition time

---

## Logical Acquisition

Logical acquisition copies only active files and folders visible to the operating system.

### Advantages

* Faster
* Smaller image size

### Disadvantages

* Misses deleted files
* Misses slack space
* Misses unallocated space

---

## Targeted / Sparse Acquisition

Only selected files, folders, or sectors are acquired.

Examples:

* Registry hives
* Browser artifacts
* Event logs

Useful during triage investigations.

---

## Remote Acquisition

Evidence is collected over a network.

Common in:

* Enterprise environments
* Cloud servers
* Remote investigations

Examples:

* F-Response
* FTK over network

---

## Live Memory Acquisition

Captures volatile memory (RAM).

Can reveal:

* Running processes
* Active malware
* Network connections
* Encryption keys
* User credentials

This is often the first step in live incident response.

---

# Storage Formats for Forensic Images

## RAW (dd)

A simple byte-for-byte copy of the source media.

### Characteristics

* No compression
* No metadata
* Universal compatibility

### Limitation

Requires separate hash storage.

---

## E01 (EnCase Evidence File)

Industry-standard forensic image format.

### Features

* Compression
* Encryption
* Embedded metadata
* Error recovery
* Hash storage

Commonly used in professional investigations.

---

## AFF (Advanced Forensic Format)

Open-source forensic image format.

### Features

* Compression
* Encryption
* Multiple hashes
* Embedded metadata

---

## VHD / VMDK

Virtual machine disk formats.

Used in:

* Hyper-V
* VMware
* Virtualized forensic environments

---

# Image Segmentation

Large forensic images can be split into smaller files.

Example:

```text
Image.E01
Image.E02
Image.E03
```

Benefits:

* Easier storage
* Easier transfer
* FAT32 compatibility

---

# Image Compression

E01 and AFF support compression.

Compression can significantly reduce storage requirements, especially on drives containing large amounts of unused space.

---

# Acquisition Methods

## Dead Acquisition

Performed when the system is powered off.

Process:

1. Remove drive
2. Connect via write blocker
3. Create forensic image

### Advantages

* Original operating system never runs
* Reduced contamination risk

---

## Live Acquisition

Performed while the system is running.

Recommended order:

1. RAM
2. Network state
3. Running processes
4. Logical files

### Required When

* Full disk encryption exists
* Critical servers cannot be powered off
* Active malware investigation

---

## Remote Acquisition

Performed through secure network access.

Often used in:

* Enterprise environments
* Cloud infrastructure
* Distributed systems

---

# Tools for Data Acquisition

## FTK Imager

Popular forensic acquisition tool.

Capabilities:

* Physical imaging
* Logical imaging
* RAM capture
* Hash verification
* Read-only image mounting

---

## Write Blockers

### Hardware

Examples:

* Tableau
* WiebeTech

Most reliable option.

### Software

Examples:

* hdparm (Linux)
* diskpart (Windows)

Less reliable than hardware solutions.

---

## Bootable Forensic Disks

Examples:

* CAINE
* Kali Linux (Forensics Mode)
* Paladin
* REMnux

Benefits:

* Bypass suspect operating system
* Prevent contamination
* Include forensic utilities

---

## Non-Writable USB Devices

USB drives equipped with physical write-protection switches.

Used for storing:

* Memory dumps
* Logs
* Reports
* Collected evidence

---

# Validating Evidence Using Hashing

## Purpose

Hashing proves that the acquired image is identical to the original source.

---

## Common Algorithms

### MD5

* Fast
* 128-bit
* Collision weaknesses

Still commonly used for integrity checks.

---

### SHA-1

* 160-bit
* Considered deprecated

---

### SHA-256

* 256-bit
* Recommended forensic standard

---

## Best Practice

Store both:

* MD5
* SHA-256

---

# When to Validate Hashes

Hash verification should be performed:

1. Before acquisition
2. During acquisition
3. After acquisition
4. After transfer
5. Before analysis
6. After analysis

---

# Hash Mismatch Scenario

If the original hash and image hash do not match:

1. Stop investigation immediately.
2. Re-acquire evidence.
3. Document the issue.

Proceeding with mismatched evidence may compromise legal admissibility.

---

# Chain of Custody & Documentation

Every acquisition should generate a forensic log containing:

* Date and Time
* Timezone
* Examiner Name
* Device Information
* Serial Number
* Capacity
* Acquisition Tool
* Tool Version
* Hash Values
* Errors or Bad Sectors

---

# Key Takeaways

* Never analyze original evidence.
* Follow the Order of Volatility.
* Use write blockers whenever possible.
* Verify evidence using hash values.
* Maintain a complete chain of custody.
* Document every forensic action.
* Perform analysis only on forensic copies.
