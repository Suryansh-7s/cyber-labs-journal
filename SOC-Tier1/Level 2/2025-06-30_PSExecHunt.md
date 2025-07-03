# PsExec Hunt – CyberDefenders Lab Journal  
**Date:** 30 June 2025  
**Track:** SOC Analyst Tier 1  
**Completed Lab:** PsExec Hunt  
**Badge:** [View Achievement](https://cyberdefenders.org/blueteam-ctf-challenges/achievements/suryansh7s/psexec-hunt/)  
**Focus Area:** Network Forensics

---

## 🧠 Summary

This lab focused on identifying lateral movement within a network through the use of PsExec — a legitimate Windows Sysinternals tool often abused by attackers. The objective was to analyze `.pcap` traffic in Wireshark and uncover details about how the attacker pivoted between systems.

---

## 🔍 What I Did

- Loaded the provided `.pcap` into **Wireshark** and applied filters like `smb2`, `ip.addr`, and `tcp.port == 445`  
- Identified the **source IP (10.0.0.130)** from which the attacker initiated PsExec-based movement  
- Found the first compromised system: **Sales-PC** and user **ssales**  
- Traced PsExec artifacts:
  - Discovered the service executable used: **psexesvc**
  - Noted that PsExec leveraged the **ADMIN$** share for installation and **IPC$** share for communication  
- Tracked lateral movement to another target system: **Marketing-PC**

---

## 💡 Takeaways

This lab showed how lateral movement can be hidden within routine SMB traffic if you’re not alert. PsExec leaves behind predictable forensic artifacts — service installation paths, network share usage, and executables — that SOC analysts should always recognize.

Also, understanding hostnames, share names, and authentication logs within packet captures provides critical visibility into attacker behavior in post-exploitation phases.

---

## 🗒️ Reflection

I now better understand how tools like PsExec work “under the hood” when used in malicious ways. It reinforced the importance of monitoring SMB usage and setting proper permissions on administrative shares like `ADMIN$` and `IPC$`.

With this knowledge, I feel more confident spotting unauthorized lateral movement and strengthening defenses against such abuse.
