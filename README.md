# Networkwalks Cybersecurity Internship – Week 2 Project

## Reconnaissance and Network Scanning

**Internship:** Cybersecurity Internship  
**Week:** 2  
**Project Modules:**  
-  Footprinting with Maltego
-  Network Scanning with Zenmap
---

# 1. Introduction

As part of Week 2 of my Cybersecurity Internship with Networkwalks, I completed practical exercises focused on two important areas of cybersecurity reconnaissance:

1. **Footprinting using Maltego**
2. **Network scanning using Zenmap**

The purpose of these exercises was to understand how cybersecurity professionals collect information about a target and identify systems that are visible within a network.

The exercises were performed for educational and authorized lab purposes. No unauthorized access, exploitation, or destructive activity was performed.

---

# 2. Objectives

The main objectives of this project were to:

- Understand the concept of reconnaissance and footprinting.
- Install and configure Maltego.
- Perform domain-based reconnaissance using Maltego.
- Identify information associated with a target domain.
- Install and configure Zenmap.
- Identify the local IP address and subnet.
- Discover live hosts within the authorized local network.
- Identify IP addresses of discovered hosts.
- Identify MAC addresses where available.
- Generate and save a network topology.
- Analyze the security implications of reconnaissance and network discovery.
---

# 3. Lab Environment

## Hardware / Operating Environment

The practical exercises were performed using a local computer and a controlled laboratory environment.

### Tools Used

| Tool | Purpose |
|---|---|
| Maltego | Footprinting and graphical reconnaissance |
| Zenmap | Graphical network scanning |
| Nmap | Scanning engine used by Zenmap |
| Windows CMD | Network configuration and IP information |
---

# 4. Footprinting with Maltego

## 5.1 Overview

Maltego is a graphical reconnaissance and investigation platform that can be used to discover relationships between domains, infrastructure, organizations, people, email addresses, and other publicly available information.

In this project, Maltego was used to perform domain-based footprinting against the authorized training target:

`networkwalks.com`

The objective was to understand how publicly available information can contribute to an organization's reconnaissance profile.

---

## 5.2 Maltego Installation

Maltego was downloaded, installed, and launched successfully on the Windows environment following these steps:
  1.  Open the website https://maltego.com → Resources tab → download Maltego → OS = Windows, Extention = .exe + Java (x64)
  2.  then Download Maltego Graph
  3.  After download complete, install the Maltego in standard way and launch.
  4.  Complete the free Maltego account creation.

### Evidence

![Maltego Installation](maltego/01.maltego-installed-and-launched.PNG)

**Observation:**  
The Maltego application was successfully installed, launched, andprepared for running reconnaissance transforms

---

## 5.3 Creating the Domain Entity

A Domain entity was created inside the Maltego workspace.

### Evidence

![Domain Entity](Module-3-Maltego/screenshots/03-domain-entity.png)

**Observation:**  
The Domain entity was added to the Maltego workspace and prepared for target configuration.

---

## 5.5 Configuring the Target Domain

The Domain entity was configured with the authorized target:

`networkwalks.com`

### Evidence

![Networkwalks Target](Module-3-Maltego/screenshots/04-networkwalks-target.png)

**Observation:**  
The target domain was successfully configured in Maltego before executing the reconnaissance transforms.

---

## 5.6 Running Email-Related Transforms

Email-related transforms were selected and executed against the configured domain.

### Evidence

![Transform Execution](Module-3-Maltego/screenshots/05-transform-execution.png)

**Observation:**  
The selected transforms were executed successfully and Maltego generated relationship data associated with the target domain.

---

## 5.7 Maltego Results

The final graph and reconnaissance results were captured after the transforms completed.

### Evidence

![Maltego Final Results](Module-3-Maltego/screenshots/06-final-results.png)

### Results Summary

The Maltego investigation produced the following results:

- **Target domain:** `networkwalks.com`
- **Email-related results:** `[ENTER YOUR ACTUAL RESULT/COUNT HERE]`
- **Other discovered entities:** `[ENTER IF APPLICABLE]`

> Note: The results obtained from reconnaissance tools may change over time because public information sources and their underlying data can change.

---

## 5.8 Analysis of Maltego Results

The exercise demonstrated how a domain can be used as a starting point for discovering relationships and publicly available information.

From a defensive cybersecurity perspective, information such as publicly exposed email addresses and infrastructure relationships can contribute to an organization's attack surface.

For example, exposed organizational email addresses may increase the risk of:

- Phishing attempts
- Social engineering
- Password-spraying attempts
- Targeted reconnaissance

The important lesson is that information does not need to be obtained through unauthorized access to become useful to an attacker. Publicly exposed information can already provide valuable intelligence.

---

# 6. Module 5 – Network Scanning with Zenmap

## 6.1 Overview

Zenmap is the official graphical user interface for Nmap.

It provides a visual interface for network discovery and scanning while using the Nmap scanning engine underneath.

In this exercise, Zenmap was used to identify live hosts within my authorized local network.

---

# 6.2 Identifying the Local IP Address and Subnet

The Windows `ipconfig` command was used to identify the local network configuration.

### Command Used

```text
ipconfig
