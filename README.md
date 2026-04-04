# Wazuh SIEM Home Lab

## Overview
This project demonstrates a multi-endpoint SIEM home lab built using Wazuh in VirtualBox. The lab consists of one Ubuntu-based Wazuh manager and two monitored endpoints: one Ubuntu agent and one Windows agent. The environment was configured to collect, forward, and visualize security events across multiple systems through the Wazuh dashboard.

## Lab Architecture
- **Wazuh Manager:** Ubuntu Server VM
- **Agent 1:** Ubuntu VM
- **Agent 2:** Windows 10 VM
- **Platform:** Oracle VirtualBox
- **Network:** NAT Network

## Objectives
- Build a working SIEM home lab using Wazuh
- Configure multiple agents to communicate with a centralized Wazuh manager
- Monitor security events from Linux and Windows systems
- Create dashboard visualizations for alerts over time, alert severity, and top alert types
- Practice troubleshooting agent enrollment, network communication, and service status issues

## Tools and Technologies
- Wazuh
- Ubuntu
- Windows 10
- Oracle VirtualBox
- Linux systemd
- PowerShell
- NAT Network configuration

## Setup Summary

### 1. Wazuh Manager Setup
- Installed Wazuh manager, indexer, and dashboard on an Ubuntu VM
- Verified dashboard access through the browser
- Confirmed Wazuh services were running properly

### 2. Ubuntu Agent Setup
- Created a separate Ubuntu VM
- Installed the Wazuh agent package
- Registered the agent with the Wazuh manager
- Updated the manager IP in the agent configuration
- Restarted the agent service and verified active connection

### 3. Windows Agent Setup
- Created a Windows 10 VM
- Connected the VM to the same NAT Network as the Wazuh manager
- Installed the Wazuh Windows agent
- Configured the agent to communicate with the Wazuh manager
- Verified the Windows agent appeared as active in the dashboard

## Dashboard Visualizations
The following visualizations were created in Wazuh:
- **Ubuntu Agent Alerts Over Time**
- **Ubuntu Agent Alert Severity**
- **Ubuntu Agent Top Alert Types**

## Example Security Events Generated

### Ubuntu Agent
- Custom log generation using `logger`
- File creation and modification
- `sudo` activity
- Agent restarts

### Windows Agent
- Windows event creation using `eventcreate`
- Wazuh service restart events

## Key Challenges and Troubleshooting
During setup, several issues were encountered and resolved:
- Agent registration showing "Never connected"
- VMs using the same IP when configured with plain NAT
- Switching to NAT Network for proper VM-to-VM communication
- Updating the Wazuh agent configuration with the correct manager IP
- Restarting services and reloading configurations to establish successful connections

## Results
The final lab successfully achieved:
- Centralized monitoring of Ubuntu and Windows endpoints
- Active agent visibility in the Wazuh dashboard
- Working security event collection and alert visualization
- A custom SIEM dashboard built from collected alerts

## Screenshots
Add screenshots in the `screenshots/` folder and reference them here.

Suggested screenshots:
- Agents active in dashboard
- Alerts over time chart
- Alert severity chart
- Top alert types table
- Security events page

## Learning Outcomes
This project helped build hands-on skills in:
- SIEM architecture
- Endpoint monitoring
- Wazuh deployment and configuration
- Linux and Windows agent enrollment
- VirtualBox networking
- Dashboard creation and alert analysis

## Future Improvements
- Add a Kali Linux attacker VM for attack simulation
- Expand dashboard visualizations
- Generate more diverse endpoint activity
- Document detection use cases in more detail

## Author
Sreeram
