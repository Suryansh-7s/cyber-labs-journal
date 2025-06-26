# 🧠 CyberDefenders Lab – Yellow RAT  
**Date:** June 26, 2025  
**Category:** Threat Intel  
**Level:** Tier 1  
**Status:** ✅ Completed (6/6)

---

## 🔍 Scenario  
A new malware strain was detected due to abnormal network behavior. The SOC team flagged a DLL with suspicious characteristics. Using threat intel platforms, I was assigned to investigate and extract insights from the malware's hash.

---

## 🧪 Tools Used  
- 🛡️ [VirusTotal](https://www.virustotal.com/)
- 📚 [Red Canary Threat Blog](https://redcanary.com/blog/threat-intelligence/yellow-cockatoo/)
  
---

## 🧩 What I Did  

- Unzipped the lab file using password `cyberdefenders.org`
- Extracted the hash from the provided `.txt` file: 30E527E45F50D2BA82865C5679A6FA998EE0A1755361AB01673950810D071C85
- Investigated the hash using VirusTotal.
- Found multiple threat intelligence entries identifying the malware as **Yellow Cockatoo RAT**  
- Used Red Canary's writeup to further validate behaviors like dropped filenames, compilation metadata, and C2 communication

---

## 🤯 Interesting Discovery  
The malware used a DLL filename (`111bc461-...`) to evade basic detection and dropped `solarmarker.dat` in the AppData folder. Also, the C2 communication occurred over **HTTPS**, making detection slightly harder without decryption or advanced logging.

---

## ✅ Key Answers (Quick Summary)
| Q | Description                                     | Answer                                   |
|---|-------------------------------------------------|-------------------------------------------|
| 1 | Malware Family                                  | Yellow Cockatoo RAT                       |
| 2 | Common Filename                                 | 111bc461-1ca8-43c6-97ed-911e0e69fdf8.dll  |
| 3 | Compilation Timestamp                           | 2020-09-24 18:26                          |
| 4 | First Submission to VirusTotal                  | 2020-10-15 02:47                          |
| 5 | Dropped .dat File                               | solarmarker.dat                           |
| 6 | C2 Server                                       | https://gogohid.com                       |

---

## 📌 Reflection  
This lab emphasized the importance of correlating multiple sources (like VirusTotal + Red Canary) to extract malware behavior comprehensively. It’s fascinating how seemingly small indicators like filenames and timestamps can reveal large behavioral patterns.