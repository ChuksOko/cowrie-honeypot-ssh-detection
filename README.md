# cybersecurity-labs-bincom-academy
Hands-on cybersecurity labs and projects - Bincom Academy Feb 2026
# Cowrie Honeypot – Network Attack Detection Project

## Overview
This project demonstrates the deployment of a Cowrie SSH honeypot, execution of simulated network attacks, traffic capture, and incident reporting.

## Lab Architecture
- Attacker: Kali Linux
- Target: Ubuntu Server + Cowrie Honeypot
- Network: Host-Only Adapter (VirtualBox)

## Tools Used
- Cowrie Honeypot
- Kali Linux
- Nmap
- Wireshark
- VirtualBox

## Attack Simulation
- TCP SYN scan on port 2222
- Unauthorized SSH login attempt
- Honeypot interaction logging

## Detection & Evidence
- PCAP traffic capture
- Cowrie application logs
- Identified attacker IP and activity timeline

## Key Findings
- Port 2222 exposed as SSH honeypot
- Unauthorized authentication attempts detected
- Session interaction logged by Cowrie

## Defensive Recommendations
- Deploy honeypots in segmented networks
- Monitor SSH brute-force patterns
- Correlate PCAP and application logs

## Author
Chukwuemeka Oko
