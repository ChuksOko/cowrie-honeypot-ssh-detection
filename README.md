# Cowrie Honeypot – Network Attack Detection (Bincom Academy Lab)

## Overview
This project demonstrates a complete “detect + evidence + report” workflow using a Cowrie SSH honeypot. I deployed Cowrie on Ubuntu Server, simulated a network scan from Kali Linux, captured traffic in Wireshark, validated attacker activity in Cowrie logs, and produced a short incident report.

## Lab Architecture
- Attacker VM: Kali Linux
- Target VM: Ubuntu Server + Cowrie SSH Honeypot
- Network: VirtualBox Host-Only Adapter (Kali ↔ Ubuntu)

## Tools Used
- Cowrie Honeypot
- Nmap
- Wireshark
- VirtualBox
- Ubuntu Server / Kali Linux

## What Happened (Attack Simulation)
- Nmap TCP SYN scan against the honeypot SSH port (2222)
- Attempted SSH interaction (honeypot logging)
- Traffic captured to PCAP for analysis

## Evidence (Where to Look)
- Incident report: `incident-report/`
- PCAP capture: `evidence/`
- Screenshots: `evidence/screenshots/`
- Wireshark filters (IoC-focused): `wireshark-filters/`

## Key Findings
- SSH honeypot exposed on TCP/2222
- Recon activity observed from attacker IP (Kali)
- Activity corroborated across PCAP + Cowrie application logs

## IoCs / Indicators
- Attacker IP: 192.168.56.102
- Target IP: 192.168.56.103
- Target Port: 2222/tcp
- Protocol: SSH

## Wireshark Filters (Quick IOC Views)
See `wireshark-filters/ioc-filters.txt`, including:
- `tcp.port == 2222`
- `ip.addr == 192.168.56.102`
- `tcp.flags.syn == 1 && tcp.flags.ack == 0`
- `ssh`

## Defensive Recommendations
- Segment honeypots from production networks (separate VLAN / host-only lab)
- Monitor and rate-limit SSH authentication attempts
- Correlate host logs (Cowrie) with network telemetry (PCAP/SIEM)

## Skills Demonstrated
- Virtual lab setup (Kali + Ubuntu) and network segmentation
- Recon detection (Nmap scan behavior)
- Packet capture and IOC filtering in Wireshark
- Log review and incident reporting

## Author
Chukwuemeka Oko
