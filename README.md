# Enterprise Network Simulation Project (Cisco Packet Tracer)

###  Author: Fuyu Dong  
###  Contact: d1513891560@gmail.com  
###  Purpose: Showcase enterprise network features and hands-on networking skills

---

##  Project Overview

This project is a simulation of a small-to-medium-sized enterprise network built with Cisco Packet Tracer. It combines essential infrastructure components and services—like VLANs, DHCP, DNS, NAT, FTP, Email, ACLs, Syslog, SSH, and VPN tunneling—into a functional and security-aware network environment. The goal is to demonstrate practical configuration skills and a solid understanding of enterprise networking.

---

##  Network Topology

> Refer to `topology.png` or open the Packet Tracer file `Enterprise_Network.pkt` for full details.

- Two routers: **HQ-Router** and **Internet-Router**
- Multiple internal VLANs (HR, IT, Server)
- DMZ network with public-facing services
- Simulated public host (PC-Internet) for external testing scenarios

---

## Implemented Features

###  Network Infrastructure
- VLAN-based segmentation (HR / IT / Server)
- Static routing and default gateway setup
- Subnet planning and address allocation
- **GRE Tunnel** setup over the public Internet
- **DHCP with relay agent** for dynamic IP assignment
- **DNS server** for internal name resolution

###  External Access & Security
- Web service hosted in DMZ, accessible from LAN and WAN
- **ACLs** to restrict public access to HTTP only
- **NAT configuration**:
  - Overload (PAT) for internal clients
  - Static NAT for DMZ server (203.0.114.100 → 192.168.100.10)
- **VPN** simulated via GRE Tunnel between HQ and Internet routers

###  Management & Security
- Syslog logging enabled, logs received by DNS server
- SSH remote access configured for HQ-Router
- ACL used to isolate and secure internal communication
- Ping and traceroute used for connectivity and path verification

###  Internal Services
- Web server (HTTP)
- FTP server for internal file sharing
- Email server (SMTP and POP3)
- All services hosted on a single multi-role server

---

##  Feature Testing Summary

| Feature              | Test Description                              | Result |
|----------------------|-----------------------------------------------|--------|
| Internal access       | HR-PC ↔ IT-PC / DNS / Web-Server              |  Pass |
| Public Web access     | PC-Internet successfully loads DMZ web page   |  Pass |
| DNS resolution        | Internal clients resolve domain via DNS       |  Pass |
| GRE tunnel            | Tunnel established and reachable end-to-end   |  Pass |
| VPN communication | Internal traffic routed securely via GRE tunnel|  Pass |
| ACL restrictions      | Public PC limited to TCP port 80 only         |  Pass |
| NAT (PAT)        | Internal clients access Internet using PAT    |  Pass |
| Static NAT       | DMZ Web server mapped to public IP            |  Pass |
| Email service         | SMTP/POP3 exchange between internal PCs       |  Pass |
| FTP file transfer     | Internal FTP login, upload/download OK        |  Pass |
| SSH login             | Remote access to HQ-Router from PC-Internet   |  Pass |
| Syslog logging        | HQ-Router logs visible on DNS server          |  Pass |

---

##  Project Files

- `Enterprise_Network.pkt` – Main Packet Tracer topology file
- `topology.png` – Overview of network structure

---

Feel free to explore the `.pkt` file in Cisco Packet Tracer to review configurations in detail.
