# Network Security Assessment

## Overview

This project demonstrates a basic network security assessment performed in a controlled lab environment using Kali Linux and Metasploitable.

The objective was to perform network discovery, identify open ports/services, and analyze the network traffic generated during scanning.

---

## Lab Environment

### Attacker Machine
- OS: Kali Linux
- Tool: Nmap
- Packet Analysis: Wireshark

### Target Machine
- OS: Metasploitable 2

### Network Setup
- Virtualization: VMware
- Network Mode: Host-only Network

---

## Objectives

- Perform host discovery
- Identify open ports and running services
- Analyze Nmap scan packets using Wireshark
- Understand TCP communication during scanning
- Document security findings

---

## Tools Used

| Tool | Purpose |
|---|---|
| Nmap | Network scanning and enumeration |
| Wireshark | Packet capture and analysis |
| Kali Linux | Security testing environment |
| Metasploitable | Vulnerable testing target |

---

## Scan Performed

Example:

```bash
nmap -sV <target-ip>

---

## Purpose

- Detect open ports
- Identify service versions
- Perform service enumeration

---

## Results

Port	Service	 Version	Risk
21	    FTP	     vsftpd	    Weak configuration
22	    SSH	     OpenSSH	Review access
80	    HTTP	 Apache	    Web assessment 

---

## Disclaimer

This assessment was performed only in an authorized lab environment for educational purposes.