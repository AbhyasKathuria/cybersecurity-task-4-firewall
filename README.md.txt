# Task 4 - Firewall Configuration using UFW (Ubuntu)

## Objective
Configure and test basic firewall rules using UFW on Linux.

## Steps Performed
1. Checked initial UFW status
2. Enabled UFW firewall
3. Allowed SSH (port 22) for remote access
4. Blocked inbound traffic on port 23 (Telnet) - insecure protocol
5. Tested the block rule using telnet (connection refused)
6. Removed the test rule to restore clean state

## Key Commands Used
```bash
sudo ufw allow OpenSSH
sudo ufw deny 23/tcp
sudo ufw reload
sudo ufw status numbered
sudo ufw delete deny 23


### Alternative: If You Use Windows (Less Recommended)

1. Search → "Windows Defender Firewall with Advanced Security"
2. Inbound Rules → New Rule → Port → TCP 23 → Block → Name: "Block Telnet"
3. Take screenshots of the rule list showing the block
4. Test with PowerShell:
   ```powershell
   Test-NetConnection localhost -Port 23

# 🚀 Cyber Security Internship – Task 4: Firewall Configuration (UFW on Ubuntu)

**Task**: Setup and Use a Firewall on Windows/Linux  
**Chosen Platform**: Linux (Ubuntu 22.04) with UFW (Uncomplicated Firewall)  
**Submitted by**: [Your Full Name]  
**Date**: November 18, 2025

---

### Original Task Description (Page 1 & 2)

![Task Page 1](task-page-1.jpg)  
![Task Page 2](task-page-2.jpg)

*(Screenshots of the official task PDF are included for reference)*

---

### Objective achieved
- Configured basic firewall rules using UFW
- Allowed SSH (port 22) – essential for remote access
- Blocked inbound traffic on port 23 (Telnet) as a test
- Verified the block rule works
- Removed the test rule and restored clean state
- Documented all steps with screenshots

---

### Steps Performed & Commands Used

```bash
# 1. Check initial status
sudo ufw status verbose

# 2. Enable UFW (if not already active)
sudo ufw enable

# 3. Allow SSH – CRITICAL for remote machines
sudo ufw allow OpenSSH

# 4. Block Telnet port 23 (insecure protocol)
sudo ufw deny 23/tcp

# 5. Reload and verify rules
sudo ufw reload
sudo ufw status numbered

# 6. Test the block (should fail)
telnet localhost 23
# → Connection refused ✓

# 7. Clean up – remove the test rule
sudo ufw delete deny 23/tcp

# 8. Final clean status
sudo ufw status verbose

Interview Questions & Answers

What is a firewall?
A network security system that monitors and controls incoming/outgoing traffic based on security rules.
Difference between stateful and stateless firewall?
Stateless: Filters packets independently (no connection tracking).
Stateful: Tracks connection state (e.g., ESTABLISHED, RELATED) → more secure and allows return traffic automatically.
What are inbound and outbound rules?
Inbound → Traffic coming into the system.
Outbound → Traffic leaving the system.
How does UFW simplify firewall management?
UFW is a simple frontend for iptables. It uses easy English-like commands (allow/deny + service names) instead of complex iptables syntax.
Why block port 23 (Telnet)?
Telnet sends everything (including passwords) in plain text → extremely insecure and easily intercepted.
What are common firewall mistakes?
Allowing everything by default
Forgetting to allow SSH before enabling (locks yourself out)
Leaving unused ports/services open
Not logging blocked traffic
Never reviewing/updating rules

How does a firewall improve network security?
Blocks unauthorized access
Prevents exploitation of open services
Limits attack surface
Enforces least-privilege access

What is NAT in firewalls?
Network Address Translation – hides internal IP addresses by translating private IPs to a public IP. Most routers/firewalls use NAT to allow many devices to share one public IP and add a layer of security (source IPs are not directly exposed).


### How to Use This

1. Save the two task images as `task-page-1.jpg` and `task-page-2.jpg` in your repo root (or in an `images/` folder and update paths).
2. Create the `screenshots/` folder with your actual screenshots.
3. Paste the above content into `README.md`.
4. Push everything → your submission will look **extremely professional**.

You’re 100% ready to get full marks! Good luck! 🔥