# Day 02 - Data Acquisition

## What is Data Acquisition?

Definition:
The process of collecting digital evidence from storage media, live systems, or network sources while preserving integrity and admissibility.

### Primary Rule
- Do not alter original evidence.

### Key Considerations
- Chain of Custody
- Write Blocking
- Live vs Dead Acquisition
- Hash Verification

---

## Order of Volatility (RFC 3227)

| Priority | Data Type | Description |
|-----------|------------|-------------|
| 1 | CPU Registers & Cache | Disappears in nanoseconds |
| 2 | RAM | Lost after power off |
| 3 | Network State | Connections, ARP tables |
| 4 | Running Processes | Active processes |
| 5 | Disk Storage | Non-volatile |
| 6 | Remote Logs & Backups | Least volatile |

Example:
Encrypted laptop → Capture RAM → Network State → Disk Image

---

## Types of Data Acquisition

### Physical Acquisition
- Bit-stream copy
- Includes allocated, unallocated and slack space
- Captures deleted files

### Logical Acquisition
- Copies only active files
- Faster but misses deleted data

### Targeted / Sparse Acquisition
- Selected files or sectors only

### Remote Acquisition
- Collection over network

### Live Memory Acquisition
- Captures RAM contents

---

## Storage Formats

### RAW (dd)
- Byte-to-byte copy
- No compression

### E01
- Compression
- Encryption
- Metadata

### AFF
- Open format
- Multiple hashes

### VHD / VMDK
- Virtual machine disks

---

## Acquisition Methods

### Dead Acquisition
- System powered off
- Use write blocker
- Image with FTK/dd

### Live Acquisition
- Capture RAM first
- Then network state
- Then logical files

### Remote Acquisition
- Secure network collection

---

## Tools for Data Acquisition

### FTK Imager
- Physical imaging
- Logical imaging
- RAM capture
- Hash verification

### Write Blockers
- Hardware
- Software

### Bootable Forensic Disks
- CAINE
- Kali Forensics
- Paladin
- REMnux

### Non-Writable USB
- Write-protected storage media

---

## Validating Evidence

### Hash Algorithms

- MD5
- SHA1
- SHA256

### Validation Stages

- Before acquisition
- During acquisition
- After acquisition
- Before analysis
- After analysis

---

## Chain of Custody

Required Information:

- Date & Time
- Examiner Name
- Evidence Details
- Acquisition Method
- Hash Values
- Errors / Bad Sectors

---

## Key Takeaways

- Preserve evidence integrity.
- Always verify hashes.
- Use write blockers.
- Follow chain of custody.
- Acquire data according to volatility.
