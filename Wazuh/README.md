# Wazuh SOC Lab

This repository documents my hands-on journey building a **Security Operations Center (SOC) lab** using **Wazuh SIEM** on VMware Workstation Pro 17.  
The lab simulates a small enterprise environment with Windows, Linux, and Kali endpoints sending logs to a central Wazuh Manager.  

The goal of this project is to strengthen practical SOC skills, test detection use cases, and demonstrate real-world problem solving.

---

## 🔹 Objectives
- Deploy Wazuh SIEM in an isolated VMware lab
- Integrate Windows and Linux endpoints using Wazuh agents
- Simulate attacks with Kali Linux and monitor detections
- Explore File Integrity Monitoring (FIM), Threat Hunting, and MITRE ATT&CK mapping

---

## 🔹 Lab Environment
- **Hypervisor:** VMware Workstation Pro 17  
- **Network:** Custom NAT (VMnet10), `192.168.200.0/24`  
- **Virtual Machines:**  
  - **Wazuh Server (OVA, Debian-based)** → `192.168.200.130` (8GB RAM, 4 vCPUs)  
  - **Windows 11 Client** → `192.168.200.128` (4GB RAM, 2 vCPUs)  
  - **Ubuntu Server** → `192.168.200.131` (4GB RAM, 2 vCPUs)  
  - **Kali Linux** → `192.168.200.129` (2GB RAM, 4 vCPUs)  

---

## 🔹 Key Setup Steps & Challenges

### 1. Creating a Custom VMware Network (VMnet10)
To allow the VMs to talk to each other in an isolated subnet:  
1. Open **VMware Workstation → Edit → Virtual Network Editor**  
2. Add a new network → choose **VMnet10**  
3. Set it to **NAT** (so VMs can share host internet if needed)  
4. Configure subnet: `192.168.200.0/24`  
5. Enable:  
   - “Use local DHCP service…”  
   - “Connect a host virtual adapter to this network”  
6. Save configuration.  

All lab VMs were attached to **VMnet10** under *VM Settings → Network Adapter → Custom (VMnet10)*.  

✅ Result: All machines successfully ping each other.  

---

### 2. Installing Windows 11 Without Internet  
Windows 11 setup was stuck on **“Let’s Connect You to a Network”**.  
The workaround was:  
1. Press **Fn + Shift + F10** → opens Command Prompt  
2. Run:  oobe\bypassnro
3. System rebooted → allowed skipping network setup and completing offline installation.  

✅ Result: Windows 11 installed successfully without requiring an internet connection.  

---

## 🔹 Current Progress
- ✅ VMware network configured (VMnet10, NAT)  
- ✅ Wazuh OVA imported and accessible on `192.168.200.130`  
- ✅ Windows 11 agent installed and registered with Wazuh  
- ✅ Wazuh dashboard shows active agent and events  

---

## 🔹 Repository Structure

Wazuh-Lab/
├── README.md # Project overview
├── Report.md # Detailed technical documentation
├── images/ # Lab screenshots
├── configs/ # Config files (ossec.conf, agent.conf, etc.)
└── notes.txt # Raw notes & troubleshooting steps


---

## 🔹 Next Steps
1. Add Ubuntu Server (`192.168.200.131`) as a Linux endpoint with Wazuh agent  
2. Simulate attacks from Kali (`192.168.200.129`) and monitor detections  
3. Explore FIM, vulnerability detection, and MITRE ATT&CK integration  
4. Continue documenting progress with screenshots, configs, and lessons learned  

---

📌 *Maintained by Oluwagbenga Ogungbemi – Repo: 53cur3dL34rn*

