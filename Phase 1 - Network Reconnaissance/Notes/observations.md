# Network Security Assessment Notes

## Lab Environment

Attacker:
- Kali Linux

Target:
- Metasploitable 2

Network:
- VMware Host-only network

---

# Nmap Observations

## Host Discovery

Command:

nmap -sn 192.168.56.0/24

Purpose:
- Identify active hosts in the network.

Observation:
- Metasploitable machine was discovered on the network.

---

# Port Scan

Command:

nmap <target-ip>

Observation:

Open ports discovered:

| Port | Service |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 80 | HTTP |

---

# Service Detection

Command:

nmap -sV <target-ip>

Purpose:
- Identify service versions running on open ports.

Observation:
- Service banners were visible.
- Version information was collected.

---

# Wireshark Analysis

Capture:
nmap_scan.pcapng

Observed packets:

## TCP SYN Scan

Nmap sends:

Client → Server

SYN packet


If port is open:

Server → Client

SYN + ACK


If port is closed:

Server → Client

RST packet


---

# Security Observations

Findings:

- Multiple services were exposed.
- Older services may contain vulnerabilities.
- Open ports increase attack surface.

---

# Recommendations

- Disable unnecessary services.
- Restrict exposed ports.
- Keep software updated.
- Monitor network traffic.