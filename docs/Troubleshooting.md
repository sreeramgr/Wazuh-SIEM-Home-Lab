# Wazuh SIEM Home Lab - Troubleshooting Notes

## Overview
This document records the main issues encountered while building the Wazuh SIEM home lab and the actions used to resolve them.

---

## 1. Wazuh installation failed during setup

### Problem
During early installation attempts, the Wazuh installer repeatedly removed previously installed components after failing to complete dashboard initialization.

### Cause
The installation environment was unstable and service initialization was failing during setup.

### Fix
- Reviewed `/var/log/wazuh-install.log`
- retried installation after adjusting VM resources
- confirmed services step by step after installation

---

## 2. Unsupported operating system warning

### Problem
The Wazuh install script returned an error saying the current system was not in the supported OS list.

### Cause
The selected Ubuntu version did not match the install script's recommended list.

### Fix
- used a compatible supported Ubuntu version for the final lab build
- proceeded only after verifying platform compatibility

---

## 3. Agents showed "Never connected"

### Problem
The Ubuntu agent was registered in the manager but stayed in the "Never connected" state.

### Cause
The agent configuration and server communication settings were not fully aligned.

### Fix
- verified the manager IP address in the agent config
- restarted the Wazuh agent service
- checked `ossec.log` on the agent side
- confirmed network connectivity between agent and manager

Useful command:
```bash
sudo tail -n 50 /var/ossec/logs/ossec.log
