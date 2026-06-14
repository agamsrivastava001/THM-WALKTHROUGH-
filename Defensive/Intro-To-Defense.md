# Blue Teaming: Intro to Defensive Security

**Date:** June 2026  
**Concepts Covered:** Log Analysis, Incident Response, Firewalls, Cryptography.

---

## 1. Incident Response & Log Analysis
Defensive security (Blue Teaming) me attack ko detect karna pehla step hota hai. Maine Linux aur Windows logs ko analyze karna seekha:
- `/var/log/auth.log` check karke SSH Bruteforce attacks ko pehchanna.
- Web server logs (`access.log`) me malicious inputs jaise **SQL Injection** payload detect karna.

## 2. Cryptography & Hashing
Data ko secure rakhne ke liye encryption aur hashing ka practical use seekha:
- **Symmetric vs Asymmetric Encryption** (RSA, AES).
- Files ki integrity verify karne ke liye `MD5` aur `SHA-256` hashes ko generate aur compare karna.

---
**Conclusion:** Security sirf break karne ka naam nahi hai, use build aur protect karna hi asli defensive security hai.
