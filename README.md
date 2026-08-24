# PENETRATION TESTING REPORT
## Reconnaissance and Network Scanning
W2-PM-FINAL | CYBERSECURITY |  NETWORKWALKS

**Pentester Name:** Nur Dirow Afrah

**Program/Batch:** B082-Networkwalks

**Date:** 24August 2026

**Modules completed:**  
-  Footprinting with Maltego
-  Network Scanning with Zenmap
  
**Client/Target:** Networkwalks and my own local LAN network

---

# 1. Liability Disclaimer ⚠️

I have performed these activities only on systems and devices for which I had secured written permission, or on systems and devices that I personally own.
All materials presented in this project are intended **for educational and research purposes only**.
Do not use any information or techniques presented here to violate the law or gain unauthorized access to systems, networks, or devices.
The instructor, authors, and Networkwalks are not responsible for any misuse of the information provided. **Every action you take is your own responsibility.**
Misuse of cybersecurity knowledge may result in **criminal charges, significant fines, loss of employment, and a permanent criminal record**.
In most countries, **unauthorized access to computer systems or networks is a criminal offense, even when no damage is caused**.

---

# 1. Introduction

As part of Week 2 of my Cybersecurity Internship with Networkwalks, I completed practical exercises focused on two important areas of cybersecurity reconnaissance:

1. **Footprinting using Maltego**
2. **Network scanning using Zenmap**

The purpose of these exercises was to understand how cybersecurity professionals collect information about a target and identify systems that are visible within a network.

This report covers footprinting the **networkwalks.com** domain using maltego and scanning my own local network with Zenmap. One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. It is the Week 2 part of my ongoing internship program at Networkwalks.

All tasks were run on a windows PC with maltego (footprinting) and Zenmap (scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.

---

# 2. Lab Environment (Tools Used)

## Hardware / Operating Environment

The practical exercises were performed using a local computer with the following tools:

| Tool | Purpose |
|---|---|
| Maltego | Footprinting and graphical reconnaissance |
| Zenmap | Graphical network scanning |
| Nmap | Scanning engine used by Zenmap |
| Windows CMD | Network configuration and IP information |
---

# 3. Footprinting with Maltego

## 3.1 Overview

Maltego is a graphical reconnaissance and investigation platform that can be used to discover relationships between domains, infrastructure, organizations, people, email addresses, and other publicly available information.
In this project, Maltego was used to perform domain-based footprinting against the authorized training target: `networkwalks.com`
The objective was to understand how publicly available information can contribute to an organization's reconnaissance profile.

---

## 3.2 Maltego Installation

Maltego was downloaded, installed, and launched successfully on the Windows environment following these steps:
  1.  Open the website https://maltego.com → Resources tab → download Maltego → OS = Windows, Extention = .exe + Java (x64)
  2.  then Download Maltego Graph
  3.  After download complete, install the Maltego in standard way and launch.
  4.  Complete the free Maltego account creation.

### Evidence

![Maltego Installation](maltego/01.maltego-installed-and-launched.PNG)

**Observation:**  
The Maltego application was successfully installed, launched, and prepared for running reconnaissance transforms

---

## 3.3 Creating the Domain Entity

A Domain entity was created inside the Maltego workspace by Searching for “Domain” & draging to the main area.

### Evidence

![Domain Entity](maltego/02.Domain-Entity.png)

**Observation:**  
The Domain entity was added to the Maltego workspace and prepared for target configuration.

---

## 3.4 Configuring the Target Domain

The Domain entity was configured with the authorized target: `networkwalks.com`

### Evidence

![Networkwalks Target](maltego/03.network-walks-target.PNG)

**Observation:**  
The target domain was successfully configured in Maltego before executing the reconnaissance transforms.

---

## 3.5 Running Email-Related Transforms

Email-related transforms were selected and executed against the configured domain.

### Evidence

![Transform Execution](maltego/04.Transform-Excusion.png)

**Observation:**  
The selected transforms were executed successfully and Maltego generated relationship data associated with the target domain.

---

## 3.6 Maltego Results

The final graph and reconnaissance results were captured after the transforms completed.

### Evidence

![Maltego Final Results](maltego/5.result.PNG)

### Results Summary

The Maltego investigation produced the following results:

- **Target domain:** `networkwalks.com`
- **Email-related results:** `info@networkwalks.com`
- **Other discovered entities:** `Mail Server:` mail.networkwalks.com

> Note: The results obtained from reconnaissance tools may change over time because public information sources and their underlying data can change.

---

## 3.7 Analysis of Maltego Results

The exercise demonstrated how a domain can be used as a starting point for discovering relationships and publicly available information.

From a defensive cybersecurity perspective, information such as publicly exposed email addresses and infrastructure relationships can contribute to an organization's attack surface.

For example, exposed organizational email addresses may increase the risk of:

- Phishing attempts
- Social engineering
- Password-spraying attempts
- Targeted reconnaissance

The important lesson is that information does not need to be obtained through unauthorized access to become useful to an attacker. Publicly exposed information can already provide valuable intelligence.

---

# 4. Network Scanning with Zenmap

## 4.1 Overview

Zenmap is the official graphical user interface for Nmap.

It provides a visual interface for network discovery and scanning while using the Nmap scanning engine underneath.

In this exercise, Zenmap was used to identify live hosts within my authorized local network.

---

# 4.2 Identifying the Local IP Address and Subnet

The Windows `ipconfig` command was used to identify the local network configuration as shown bellow:
![Maltego Final Results](nenmap/01.local-ip-and-subnet.PNG)

---

# 4.3 Configuring the Zenmap Ping Scan

After identifying the local subnet, Zenmap was configured to perform a Ping Scan against the authorized local network.
Scan Configuration:
|Parameter	|Value |
|---|---|
|Scan Type|	Ping Scan |
|Target| [YOUR LOCAL SUBNET] |
|Purpose|	Live Host Discovery |
Evidence
![Maltego Final Results](nenmap/02.zenmap-configuration-pingscan.PNG)

---

# 5.3 Live Host Discovery

The Ping Scan was executed to identify active hosts within the authorized local network.

Evidence
![Zenmap live hosts](nenmap/03.zenmap-live-hosts.PNG)

Discovered Hosts
No.	IP Address	Status
1	[IP ADDRESS]	Up
2	[IP ADDRESS]	Up
3	[IP ADDRESS]	Up
4	[IP ADDRESS]	Up
5	[IP ADDRESS]	Up
Total Live Hosts

[NUMBER OF LIVE HOSTS]

# 5.5 IP Address Information

The scan results were reviewed to identify the IP addresses of the discovered live hosts.

No.	IP Address	Status
1	[IP ADDRESS]	Up
2	[IP ADDRESS]	Up
3	[IP ADDRESS]	Up
4	[IP ADDRESS]	Up
5	[IP ADDRESS]	Up

# 5.6 MAC Address Information

MAC address information was reviewed for the discovered hosts where available.

Evidence

MAC Address Results
No.	IP Address	MAC Address
1	[IP ADDRESS]	[MAC ADDRESS]
2	[IP ADDRESS]	[MAC ADDRESS]
3	[IP ADDRESS]	[MAC ADDRESS]
4	[IP ADDRESS]	[MAC ADDRESS]
5	[IP ADDRESS]	[MAC ADDRESS]

# 5.7 Network Topology

After completing the network discovery scan, the network topology was generated and saved as a PDF.

Topology

![Maltego Final Results](NMAP-TOPOLOGY-1.jpg)
Topology File
zenmap/
└── 06-zenmap-topology.pdf

# 5.8 Zenmap Scan Results

The Zenmap scan successfully identified active hosts within the authorized local network.

Summary
Item	Result
Scanned Network	[YOUR LOCAL SUBNET]
Scan Type	Ping Scan
Live Hosts	[NUMBER]
IP Addresses Identified	[NUMBER]
MAC Addresses Identified	[NUMBER]
Topology Generated	Yes

# 5.9 Analysis

The network scan demonstrated how Zenmap can be used to discover active systems within an authorized network.

The scan identified live hosts and provided IP address information, while MAC address information was available for hosts where it could be determined.

The topology generated from the scan provided a visual representation of the discovered network environment.

# 5.10 Security Relevance

Network discovery is an important part of cybersecurity because it helps organizations understand which systems are active and visible within their networks.

The information obtained during the scan can support:

Network asset inventory
Identification of unknown devices
Detection of unauthorized systems
Network segmentation reviews
Security monitoring
Network administration

# 5.11 Conclusion

The Zenmap practical exercise was successfully completed. I installed Zenmap, identified the local IP address and subnet, configured and performed a Ping Scan, discovered live hosts, reviewed IP and MAC address information, and generated a network topology.

This exercise provided practical experience in network discovery and demonstrated how Zenmap can be used as a cybersecurity reconnaissance and network administration tool within an authorized environment.
