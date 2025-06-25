# 🧠 CyberDefenders Lab – PoisonedCredentials  
**Date:** June 25, 2025  
**Category:** Network Forensics  
**Level:** Tier 1  
**Status:** ✅ Completed (5/5)

---

## 🔍 Scenario  
An attacker exploited a mistyped LLMNR query from a legitimate machine to respond with a poisoned result. This allowed the attacker to collect NTLMv2 hashes and gain unauthorized access to a target system.

---

## 🧪 Tools Used  
- 🔬 Wireshark  
- 🛜 Network packet capture (PCAP analysis)

---

## 🧩 What I Did  

- Filtered LLMNR traffic using: `llmnr && ip.src == 192.168.232.162`
- Identified the typo in the broadcast query: `fileshaare`
- Tracked poisoned response and rogue responder IP: `192.168.232.215`
- Used `ntlmssp.auth.username` filter to find the compromised username
- Inspected SMB access logs to identify the attacked machine

---

## 🤯 Interesting Discovery  
Even a **single mistyped hostname** can trigger a name resolution request over LLMNR, which opens the door for attackers to poison the response and capture NTLM credentials — a very real, often overlooked threat inside enterprise networks.

---

## ✅ Key Answers (Quick Summary)  
| Q | Description                               | Answer              |
|---|-------------------------------------------|----------------------|
| 1 | Mistyped Query                            | fileshaare           |
| 2 | Rogue Machine IP                          | 192.168.232.215      |
| 3 | Second Victim Machine IP                  | 192.168.232.176      |
| 4 | Compromised Username                      | janesmith            |
| 5 | Target Hostname (via SMB)                 | AccountingPC         |

---

## 📌 Reflection  
This lab deepened my understanding of **LLMNR spoofing and NTLM relay** techniques. It highlighted how critical internal name resolution protocols can be abused and showed the power of simple packet analysis for uncovering credential theft.

---
