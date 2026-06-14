# TryHackMe: RootMe Room Write-up

**Difficulty:** Easy  
**Concepts Learned:** Nmap Scanning, Directory Busting, Privilege Escalation via SUID.

---

## 1. Reconnaissance (Information Gathering)
Sabse pehle maine target IP ko scan kiya yeh dekhne ke liye ki kaun se ports open hain:

```bash
nmap -sV -sC -A <TARGET_IP>
```

**Findings:**
- Port 80 (HTTP) open hai (Apache Web Server).
- Port 22 (SSH) open hai.

## 2. Directory Busting
Port 80 par website chal rahi thi, isliye maine hidden directories dhundhne ke liye `Gobuster` chalaya:

```bash
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirb/common.txt
```

Mujhe ek hidden directory mili: `/panel/` jahan file upload karne ka option tha.

## 3. Gaining Access (Exploitation)
Maine ek PHP Reverse Shell (`php-reverse-shell.php`) upload karne ki koshish ki, lekin `.php` extension blocked tha. 

Maine bypass karne ke liye extension ko `.phtml` mein badla, aur file successfully upload ho gayi.
Maine apne terminal par Netcat listener start kiya:

```bash
nc -lvnp 1234
```

Jaise hi maine uploaded file ko `/uploads/` directory se execute kiya, mujhe **Reverse Shell** mil gaya!

## 4. Privilege Escalation (Root Access)
User flag milne ke baad, maine SUID files check keen:

```bash
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null
```

Mujhe pata chala ki `/usr/bin/python` ke paas SUID permissions hain. GTFOBins ki madad se maine root access liya aur `root.txt` flag haasil kiya.

---
**Conclusion:** Yeh room offensive security ke basics jaise web exploitation aur misconfigured SUID ki achhi knowledge deta hai.
