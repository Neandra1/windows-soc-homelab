# 🛡️ Enterprise Windows SOC Homelab

> An enterprise-style Windows Security Operations Center (SOC) homelab built using Windows Server 2022, Active Directory, Splunk Enterprise, Sysmon, and Windows 11 Enterprise.

---

# 📖 Project Overview

This project demonstrates the deployment and administration of a Windows enterprise environment within Oracle VirtualBox.

The environment includes a Windows Server 2022 Domain Controller (DC01) and a Windows 11 Enterprise workstation (CLIENT01). Enterprise services such as Active Directory, DNS, DHCP, Group Policy, file sharing, and centralized log collection with Splunk Enterprise were configured to simulate a real-world corporate network.

The objective of this project was to gain hands-on experience with Windows system administration, endpoint monitoring, security event analysis, and SIEM implementation.

---

# 🎯 Project Objectives

- Deploy Windows Server 2022
- Configure Active Directory Domain Services
- Create Organizational Units, users, and security groups
- Configure DNS and DHCP
- Deploy Group Policy Objects (GPOs)
- Configure secure department file shares
- Install Splunk Enterprise
- Deploy the Splunk Universal Forwarder
- Install and configure Sysmon
- Centralize Windows event logs
- Validate security events using Splunk searches

---

# 🖥️ Lab Environment

| Component | Technology |
|-----------|------------|
| Hypervisor | Oracle VirtualBox |
| Domain Controller | Windows Server 2022 |
| Client | Windows 11 Enterprise |
| Active Directory | AD DS |
| DNS | Windows DNS |
| DHCP | Windows DHCP |
| Group Policy | Windows GPO |
| File Services | SMB Shares & NTFS Permissions |
| SIEM | Splunk Enterprise |
| Endpoint Logging | Sysmon |
| Log Collection | Splunk Universal Forwarder |

---

# 🌐 Network Configuration

| System | Hostname | IP Address |
|---------|----------|------------|
| Domain Controller | DC01 | 192.168.10.10 |
| Windows Client | CLIENT01 | DHCP Assigned |

Domain:

```text
homelab.local
```

---

# 📂 Repository Structure

```text
windows-soc-homelab
│
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

The screenshots folder contains documentation covering:

- Windows Server installation
- Active Directory configuration
- DHCP configuration
- Group Policy
- File shares and permissions
- Networking validation
- Splunk Enterprise
- Sysmon installation

---

# 📚 Documentation

| Guide | Description |
|------|-------------|
| Building DC01 | Windows Server installation and promotion |
| Active Directory | Users, OUs, and Security Groups |
| DHCP | DHCP Scope and Lease Configuration |
| Group Policy | Password Policies and Drive Mapping |
| File Server | Department Shares and NTFS Permissions |
| Splunk | SIEM Deployment |
| Sysmon | Endpoint Monitoring |
| Threat Hunting | Splunk Detection Searches |

---

# 🛠 Skills Demonstrated

- Windows Server Administration
- Active Directory
- DNS
- DHCP
- Group Policy
- Windows Networking
- NTFS Permissions
- SMB File Shares
- Splunk Enterprise
- SIEM Administration
- Splunk Universal Forwarder
- Sysmon
- Windows Event Monitoring
- Security Log Analysis
- Troubleshooting
- Virtualization

---

# 🚀 Future Improvements

Future enhancements planned for this project include:

- Splunk Dashboards
- Custom Detection Rules
- Windows Event Forwarding (WEF)
- Additional Domain-Joined Endpoints
- PowerShell Automation
- Threat Detection Use Cases

---

# Disclaimer

This project was built in an isolated lab environment for educational and portfolio purposes. No production systems or unauthorized third-party systems were accessed.
