# Cybersecurity Foundation: Networking Basics

**Date:** June 2026  
**Concepts Covered:** OSI Model, TCP/UDP, IP Addressing, Wireshark Packet Analysis.

---

## 1. OSI Model Understanding
Cybersecurity me network layers ko samajhna sabse zaroori hai. Maine OSI model ki 7 layers aur unke security implications ko seekha:
- **Layer 7 (Application):** HTTP/HTTPS, DNS (Yahan Web Application Attacks hote hain).
- **Layer 4 (Transport):** TCP (Connection-oriented) aur UDP (Connectionless) protocols.
- **Layer 3 (Network):** IP Routing aur ICMP (Ping requests).

## 2. Packet Sniffing with Wireshark
Maine `Wireshark` ka use karke live network traffic ko capture aur analyze kiya:
- Unencrypted protocols jaise **HTTP** aur **FTP** ke packets se credentials (username/password) ko plain text me extract karna seekha.
- **TCP Three-Way Handshake** (SYN -> SYN-ACK -> ACK) ko live packets me trace kiya.

---
**Conclusion:** Strong networking knowledge ke bina firewall bypass ya network intrusion detection samajhna namumkin hai.
