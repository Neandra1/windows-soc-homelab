# 🛡️ Enterprise Windows SOC Homelab

> An enterprise-style Windows Security Operations Center (SOC) homelab built using Windows Server 2022, Active Directory, Splunk Enterprise, Sysmon, and Windows 11 Enterprise.

---

## 📖 Project Overview

This project documents the design, deployment, and administration of a Windows enterprise environment built inside Oracle VirtualBox.

The lab simulates a corporate network consisting of a Windows Server 2022 Domain Controller (DC01) and a Windows 11 Enterprise workstation (CLIENT01). Enterprise services including Active Directory, DNS, DHCP, Group Policy, department file shares, Sysmon, and Splunk Enterprise were deployed to demonstrate centralized authentication, endpoint monitoring, and security event analysis.

Throughout this project I gained practical experience deploying enterprise Windows infrastructure, troubleshooting networking issues, configuring centralized logging, and validating security events within a SIEM.

---

# 📑 Table of Contents

- Project Overview
- Project Objectives
- Key Technologies
- Lab Environment
- Network Configuration
- Lab Architecture
- Repository Structure
- Project Screenshots
- Documentation
- Skills Demonstrated
- Lessons Learned
- Future Improvements
- Disclaimer

---

# 🎯 Project Objectives

- Deploy Windows Server 2022
- Configure Active Directory Domain Services
- Create Organizational Units
- Create Domain Users
- Create Security Groups
- Configure DNS
- Configure DHCP
- Deploy Group Policy Objects
- Configure Department File Shares
- Configure NTFS Permissions
- Install Splunk Enterprise
- Deploy the Splunk Universal Forwarder
- Install Sysmon
- Collect Windows Security Events
- Perform basic threat hunting using Splunk

---

# 🔧 Key Technologies

- Windows Server 2022
- Windows 11 Enterprise
- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- SMB File Shares
- NTFS Permissions
- Oracle VirtualBox
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Windows Event Viewer
- PowerShell

---

# 🖥️ Lab Environment

| Component | Technology |
|-----------|------------|
| Hypervisor | Oracle VirtualBox |
| Domain Controller | Windows Server 2022 |
| Client Workstation | Windows 11 Enterprise |
| Active Directory | AD DS |
| DNS | Windows DNS |
| DHCP | Windows DHCP |
| Group Policy | Windows GPO |
| File Services | SMB Shares & NTFS Permissions |
| SIEM | Splunk Enterprise |
| Endpoint Monitoring | Sysmon |
| Log Collection | Splunk Universal Forwarder |

---

# 🌐 Network Configuration

| Device | Hostname | IP Address |
|----------|----------|------------|
| Domain Controller | DC01 | 192.168.10.10 |
| Windows Client | CLIENT01 | DHCP Assigned |

**Domain Name**

```
homelab.local
```

---

# 🏗️ Lab Architecture

```text
                     Host Computer
                  Windows 11 (Physical)

                           │
                   Oracle VirtualBox

                           │
        ┌──────────────────┴──────────────────┐
        │                                     │

 Windows Server 2022                  Windows 11 Enterprise
        DC01                               CLIENT01

        │                                     │
        ├── Active Directory                  │
        ├── DNS                               │
        ├── DHCP                              │
        ├── SMB File Shares                   │
        ├── Group Policy                      │
        ├── Splunk Enterprise ◄───────────────┘
        └── Sysmon
```

---

# 📂 Repository Structure

```text
windows-soc-homelab

├── documentation
├── screenshots
│   ├── active-directory
│   ├── dhcp
│   ├── gpo
│   ├── networking
│   ├── server
│   ├── splunk
│   └── sysmon
│
└── README.md
```

---

# 📸 Project Screenshots

The repository includes screenshots documenting:

- Windows Server deployment
- Active Directory configuration
- DHCP configuration
- Group Policy configuration
- Department File Shares
- Network connectivity
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon installation
- Windows Event Collection

---

# 📚 Documentation

Detailed documentation is available for each stage of the project.

| Guide | Description |
|------|-------------|
| 01 - Building DC01 | Windows Server deployment |
| 02 - Active Directory | Users, OUs, and Security Groups |
| 03 - DHCP | Scope and Lease Configuration |
| 04 - Group Policy | GPO Configuration |
| 05 - File Server | Department Shares |
| 06 - Splunk Enterprise | SIEM Deployment |
| 07 - Sysmon | Endpoint Monitoring |
| 08 - Threat Hunting | Detection Queries |

---

# 🛠️ Skills Demonstrated

## Windows Administration

- Windows Server Administration
- Active Directory
- DNS
- DHCP
- Group Policy
- File Services
- NTFS Permissions

## Security

- Splunk Enterprise
- SIEM Administration
- Endpoint Monitoring
- Sysmon
- Windows Event Logs
- Log Collection

## Networking

- TCP/IP
- DNS
- DHCP
- Static IP Configuration
- VirtualBox Networking
- Network Troubleshooting

## Professional Skills

- Technical Documentation
- Enterprise Troubleshooting
- Security Monitoring
- Windows Administration
- Problem Solving

---

# 📈 Lessons Learned

This project provided hands-on experience administering an enterprise Windows environment while improving my understanding of system administration, security monitoring, and troubleshooting.

Key areas of growth included:

- Active Directory administration
- DNS configuration
- DHCP deployment
- Group Policy management
- NTFS permissions
- Department file shares
- Splunk Enterprise deployment
- Universal Forwarder configuration
- Sysmon endpoint monitoring
- Windows Event Log analysis
- SIEM implementation
- Enterprise troubleshooting

---

# 🔍 Challenges Encountered

Like most real-world deployments, several technical issues were encountered and resolved during the build process.

Challenges included:

- Troubleshooting VirtualBox networking
- Configuring NAT and Internal Networks
- Restoring Internet connectivity to DC01
- Synchronizing system time between DC01 and CLIENT01
- Resolving Splunk authentication issues
- Deploying the Universal Forwarder
- Configuring Splunk receiving port 9997
- Verifying Sysmon event collection
- Confirming Windows Security Events were successfully indexed inside Splunk Enterprise

Resolving these issues provided valuable real-world troubleshooting experience beyond simply following deployment documentation.

---

# 🚀 Future Improvements

Future enhancements planned for this project include:

- Deploy Microsoft Defender for Endpoint
- Build custom Splunk dashboards
- Create Splunk alerts
- Simulate cyber attacks
- Develop threat hunting playbooks
- Add additional Windows clients
- Deploy a Linux endpoint
- PowerShell automation
- Windows Event Forwarding (WEF)

---

# Disclaimer

This project was built inside an isolated lab environment for educational purposes and professional portfolio development.

No production systems or unauthorized third-party systems were accessed.
