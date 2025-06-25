# WebStrike – CyberDefenders Lab Journal  
**Date:** 23 June 2025  
**Track:** SOC Analyst Tier 1  
**Completed Lab:** WebStrike  
**Badge:** [View Achievement](https://cyberdefenders.org/blueteam-ctf-challenges/achievements/sharmasury04/webstrike/)  
**Focus Area:** Network Forensics

---

## 🧠 Summary

This lab involved investigating a `.pcap` file that captured a suspected web attack. I loaded it into Wireshark and worked through six questions focused on tracing attacker behavior — from file uploads to exfiltration attempts.

---

## 🔍 What I Did

- Used **Wireshark** filters like `http.request`, `tcp.port == 8080`, and `ip.addr == x.x.x.x` to narrow down traffic  
- Followed **HTTP and TCP streams** to understand request flows and payloads  
- Detected a suspicious file upload (`image.jpg.php`) — likely a web shell  
- Identified the upload path (`/reviews/uploads/`) and an attempt to fetch `/etc/passwd`  
- Used a **GeoIP lookup tool** to trace the attacker's IP to **Tianjin**

---

## 💡 Takeaways

This lab showed how much you can uncover from just a packet capture — if you ask the right questions and know where to look. The combination of simple filtering, stream analysis, and a bit of curiosity made the investigation flow naturally.

Also realized how often attackers rely on weak upload protections — and how small things like user-agent headers can give away their tools.

---

## 🗒️ Reflection

I’m starting to get a feel for how Tier-1 SOC analysts approach network logs and packet data. It’s not just about spotting “red alerts” — it’s about noticing small patterns, asking *why* something is happening, and building the story from there.

Definitely motivated to try the next few labs with a bit more speed and structure.

