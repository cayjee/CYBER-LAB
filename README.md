# CYBER-LAB
Detecting SSH Brute Force, ICMP Ping, and Nmap Scans with Snort (Port Mirroring Setup)

## Introduction
Intrusion Detection Systems (IDS) are widely used to monitor network traffic and detect suspicious activity.  
In this lab, **Snort IDS** is deployed in **port mirroring mode** (SPAN port) on winbdows HyperV.  
This means Snort does not sit inline with the target server, but instead listens to a copy of the traffic forwarded by the hypervisor.  

The objective is to detect:
- SSH brute force alerts attempts
- ICMP ping sweeps alerts
- Nmap port scans alerts

This setup simulates a realistic enterprise scenario where IDS sensors are connected to mirrored traffic.

---

## Lab Architecture

### Components
- **Attacker** → Kali Linux (Hydra, ping, Nmap)  
- **Target** → Ubuntu Server (SSH service enabled)  
- **IDS** → Snort (connected via port mirroring on the VswitchExterne (HyperV Vswitch))  
