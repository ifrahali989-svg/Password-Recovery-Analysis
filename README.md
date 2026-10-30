PDF Password Recovery & Hash Security Analysis

A practical cybersecurity exercise demonstrating offline hash extraction and recovery workflows on encrypted PDF documents using **John the Ripper** (via the **Johnny GUI** interface).

---

##  Project Overview

This project showcases the security implications of weak passphrase selection on password-protected PDF files. By extracting the document's hash and executing an offline recovery attack, it highlights how quickly low-complexity passwords can be compromised using standard auditing tools.

---

##  Technical Workflow

1. **Hash Extraction:**
   * Processed an encrypted PDF document to extract the inner hash format:  
     `$pdf$4*4*128...`
   * Identified hash type/mode: **PDF 1.4 – 1.6 (Mode 10500)**.

2. **Offline Hash Recovery:**
   * Imported the extracted hash string into **Johnny** (GUI for John the Ripper).
   * Executed a dictionary-based recovery attack against the target hash.

3. **Attack Results:**
   * **Target Password:** `password1`
   * **Recovery Time:** Under a few seconds.

---

##  Key Takeaways & Mitigation

* **Vulnerability of Simple Passwords:** Automated hash-cracking utilities process millions of candidate words per second, rendering short or predictable passwords ineffective against dictionary attacks.
* **Defensive Best Practices:**
  * Implement long, complex passphrases (combining uppercase, lowercase, numbers, and symbols).
  * Enforce strong key derivation/encryption standards on sensitive files.
  * Apply multi-factor protection or access control layers where supported.

---

##  Tools & Tech Stack

* **Hash Extractor:** `pdf2john` / PDF Hash Identification
* **Cracking Engine:** John the Ripper / Johnny GUI
* **Hash Target:** PDF 1.4 - 1.6 Encryption (Mode 10500)

---

> ⚠️ **Disclaimer:** *This repository and its content are created strictly for educational and ethical cybersecurity research purposes.*
