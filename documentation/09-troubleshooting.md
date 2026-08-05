# 🛠️ 09 - Troubleshooting Journal

---

# 📖 Overview

Building an enterprise Windows Security Operations Center (SOC) homelab involved much more than simply installing software.

Throughout this project, I encountered several real-world technical issues involving virtualization, networking, Active Directory, Windows configuration, and Splunk. Each issue required troubleshooting, research, testing, and validation before the lab could function correctly.

This journal documents the challenges I encountered, the troubleshooting process I followed, and the solutions that allowed the project to move forward.

---

# 💻 Challenge 0 – Hardware Limitations

## Problem

When I began building this homelab, my laptop only had **4 GB of RAM**. Running Windows Server 2022, Windows 11 Enterprise, and Oracle VirtualBox simultaneously caused significant performance issues.

Common problems included:

- Slow virtual machine performance
- Long boot times
- Limited ability to run multiple virtual machines
- Resource constraints while configuring the lab

These limitations made it difficult to build and manage an enterprise environment efficiently.

## Investigation

After monitoring system performance, I determined that the primary bottleneck was available system memory.

Rather than lowering the scope of the project, I decided to upgrade the hardware so the lab could better support virtualization and multiple operating systems.

## Resolution

I upgraded my laptop from **4 GB of RAM to 16 GB of RAM**.

The memory upgrade significantly improved the performance of Oracle VirtualBox and allowed me to comfortably run:

- Windows Server 2022 (DC01)
- Windows 11 Enterprise (CLIENT01)
- Splunk Enterprise
- Sysmon
- Active Directory services

The additional memory made the environment much more stable and greatly improved the overall lab experience.

## Skills Demonstrated

- Hardware Upgrades
- Performance Troubleshooting
- Virtualization
- Resource Planning
- Problem Solving
  
--- 

# 🔧 Challenge 1 – CLIENT01 Could Not Join the Domain

## Problem

After deploying Windows 11, CLIENT01 was unable to join the **homelab.local** domain.

## Investigation

I verified:

- Active Directory was installed
- DNS was configured
- Network adapters were enabled
- DC01 was online

After reviewing the installation, I discovered that CLIENT01 had been installed using **Windows 11 Home**, which does not support joining an Active Directory domain.

## Resolution

I recreated CLIENT01 using **Windows 11 Enterprise**.

After reinstalling the operating system, the workstation successfully joined the domain.

## Skills Demonstrated

- Active Directory
- Windows Installation
- Domain Administration
- Troubleshooting

---

# 🌐 Challenge 2 – VirtualBox Networking

## Problem

Communication between DC01 and CLIENT01 was inconsistent.

Internet connectivity worked, but domain communication did not.

## Investigation

Multiple VirtualBox network configurations were tested, including:

- NAT
- Internal Network
- Adapter configuration
- Static addressing

Network connectivity was verified using:

- ping
- ipconfig
- route print
- nslookup

## Resolution

DC01 was configured with:

- Adapter 1 → NAT
- Adapter 2 → Internal Network (LabNetwork)

CLIENT01 was connected to the same Internal Network.

This allowed:

- Domain communication
- Internet access
- Active Directory functionality

## Skills Demonstrated

- Windows Networking
- VirtualBox
- TCP/IP
- Network Troubleshooting

---

# 🌍 Challenge 3 – DC01 Lost Internet Access

## Problem

After changing network adapters, DC01 lost Internet connectivity.

## Investigation

I verified:

- IP configuration
- Adapter settings
- DNS
- Default gateway
- Routing table

Connectivity tests included:

- ping
- nslookup
- Browser testing

## Resolution

The network adapters were reconfigured and connectivity was verified.

Internet access was restored while maintaining communication with CLIENT01 over the Internal Network.

## Skills Demonstrated

- DNS
- Routing
- Windows Networking
- Troubleshooting

---

# ⏰ Challenge 4 – Splunk Login Failed on CLIENT01

## Problem

Splunk credentials worked from:

- DC01
- My personal computer

However, CLIENT01 consistently displayed:

> Invalid username or password

## Investigation

Password resets were performed, but the issue remained.

Further investigation revealed that CLIENT01's system clock did not match DC01.

## Resolution

After synchronizing the system time, authentication immediately began working correctly.

## Skills Demonstrated

- Authentication Troubleshooting
- Windows Time Service
- Active Directory
- Splunk Administration

---

# 📡 Challenge 5 – Universal Forwarder Configuration

## Problem

The Splunk Universal Forwarder was installed but was not forwarding Windows event logs.

## Investigation

Several configuration items were verified:

- Forward Server
- Port 9997
- inputs.conf
- Splunk service
- Firewall
- Connectivity

Command-line tools were used to verify the forwarder configuration.

## Resolution

After correcting the configuration, the Universal Forwarder successfully connected to Splunk Enterprise and began forwarding Windows Security Events.

## Skills Demonstrated

- Splunk
- SIEM Administration
- Windows Services
- Endpoint Monitoring

---

# 📊 Challenge 6 – Verifying Sysmon Events

## Problem

After installing Sysmon, it was necessary to verify that endpoint events were successfully collected.

## Investigation

Sysmon was monitored using:

- Event Viewer
- Splunk Enterprise

Events observed included:

- Event ID 1 (Process Creation)
- Event ID 4
- Event ID 16
- Event ID 22 (DNS Query)

## Resolution

The successful appearance of Sysmon events within Splunk confirmed that endpoint monitoring had been configured correctly.

## Skills Demonstrated

- Sysmon
- Endpoint Monitoring
- SIEM
- Log Analysis

---

# 🎯 Biggest Lesson Learned

One of the most valuable lessons from this project was that enterprise deployments rarely work perfectly on the first attempt.

Many of the most important learning experiences came from diagnosing and resolving issues rather than simply completing installation steps.

Each troubleshooting session strengthened my understanding of:

- Windows Server Administration
- Active Directory
- Windows Networking
- DNS
- DHCP
- Splunk Enterprise
- Sysmon
- Enterprise troubleshooting methodology

---

# 💭 Reflection

This project reinforced that successful IT and cybersecurity professionals are not defined by avoiding problems—they are defined by their ability to investigate issues, identify root causes, and implement effective solutions.

Completing this homelab improved both my technical skills and my confidence working with enterprise Windows infrastructure.

The experience gained from troubleshooting real deployment challenges has prepared me to approach future systems administration and cybersecurity tasks with a structured, methodical mindset.
