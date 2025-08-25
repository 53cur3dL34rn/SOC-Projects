# Wazuh Lab - Week 1 Setup

## Objective
Install Wazuh OVA on VMware Workstation 17 and connect a Windows endpoint.

## Steps Taken
1. Downloaded Wazuh OVA from official site.
2. Imported OVA into VMware Workstation.
3. Configured NAT networking for Wazuh + Windows.
4. Booted Wazuh and accessed dashboard at `https://<wazuh-ip>:55000`.
5. Installed Wazuh agent on Windows endpoint.
6. Verified logs appearing in Wazuh dashboard.

## Screenshots
![Wazuh Dashboard](./images/wazuh-dashboard.png)
![Windows Agent Logs](./images/windows-agent-logs.png)

## Next Steps
- Add Linux endpoint for log forwarding.
- Configure basic alert rules.
