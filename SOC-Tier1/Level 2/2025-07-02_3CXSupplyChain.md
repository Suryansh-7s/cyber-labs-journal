# 3CX Supply Chain – CyberDefenders Lab Journal  
**Date:** 2 July 2025  
**Track:** SOC Analyst Tier 1  
**Completed Lab:** 3CX Supply Chain  
**Badge:** [View Achievement](https://cyberdefenders.org/blueteam-ctf-challenges/achievements/suryansh7s/3cx-supply-chain/)  
**Focus Area:** Threat Intelligence

---

## 🧠 Summary

This lab dissected a real-world supply chain attack involving 3CX, where a legitimate installer was weaponized to distribute malware. The focus was on tracing file behavior, identifying MITRE ATT&CK mappings, and recognizing APT-level tactics and anti-analysis evasion mechanisms.

---

## 🔍 What I Did

- Verified that **2 Windows versions** of 3CX were flagged as malicious  
- Extracted creation timestamp: `2023-03-13 06:33 UTC` from the `.msi` file  
- Identified dropped DLLs: `ffmpeg.dll` and `d3dcompiler_47.dll`  
- Mapped **DLL sideloading** persistence to MITRE ID **T1574**  
- Recognized both DLLs categorized as **Trojan**  
- Noted virtualization evasion via MITRE ID **T1497**  
- Analyzed **VMware-targeted anti-analysis** behavior in `ffmpeg.dll`  
- Detected use of **RC4 encryption algorithm**  
- Attributed the attack to **APT group Lazarus**

---

## 💡 Takeaways

This lab offered insights into the challenges of detecting malicious code in otherwise trusted software. Seeing how DLL sideloading and sandbox evasion played out in a real-world case strengthened my understanding of post-exploitation behavior in supply chain breaches.

It also emphasized the power of threat intelligence tools (VirusTotal, ANY.RUN, etc.) when combined with frameworks like MITRE ATT&CK.

---

## 🗒️ Reflection

What made this lab stand out was the blend of static and dynamic analysis techniques. I realized the importance of early identification of threat actors and their TTPs—especially when tracking APT groups like Lazarus.

With each lab, I’m becoming more confident in correlating technical evidence with threat intelligence frameworks and attack models.
