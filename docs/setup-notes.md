# Wazuh SIEM Home Lab - Setup Notes

## Overview
This document summarizes the main setup steps used to build the Wazuh SIEM home lab in Oracle VirtualBox. The lab includes one Ubuntu-based Wazuh manager, one Ubuntu agent, and one Windows 10 agent.

## Lab Components
- Wazuh Manager: Ubuntu Server VM
- Ubuntu Agent: Ubuntu VM
- Windows Agent: Windows 10 VM
- Virtualization Platform: Oracle VirtualBox
- Network Mode: NAT Network

## IP Addressing Used
- Wazuh Manager: `10.0.3.3`
- Ubuntu Agent: `10.0.3.4`
- Windows Agent: `10.0.3.5`

---

## 1. Wazuh Manager Setup

### Main components installed
The Wazuh server VM was configured with:
- Wazuh manager
- Wazuh indexer
- Wazuh dashboard

### Useful commands
Check service status:
```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
