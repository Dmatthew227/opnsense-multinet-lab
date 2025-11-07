# 🧱 OPNsense Multi-Network Lab (VMware Workstation)

This project demonstrates the setup and configuration of **OPNsense 25.7** as a multi-interface firewall and router inside a **virtualized environment**.  
It simulates a small enterprise network with multiple departments — each on its own subnet — and shows how to route and control traffic between them.

---

## 🧠 Project Overview

**Goal:**  
Design a multi-network environment using **OPNsense** to route traffic between isolated LANs (e.g., Finance and General LAN), while maintaining secure internet access.

**Virtualization Platform:**  
VMware Workstation Pro

**Operating Systems:**
- **OPNsense 25.7 (Firewall/Router)**
- **Ubuntu 24.04 LTS (Clients)**

---

## 🌐 Network Topology

| Interface | Role | Network | IP/Subnet | Description |
|------------|------|----------|------------|--------------|
| `em0` | WAN | NAT | DHCP | Internet access via host |
| `em1` | LAN | 192.168.1.0/24 | Gateway: 192.168.1.1 | General office LAN |
| `em2` | Finance | 192.168.10.0/24 | Gateway: 192.168.10.1 | Finance subnet |
| `em3` | OPT2 | 192.168.20.0/24 | Gateway: 192.168.20.1 | Optional testing subnet |

---

## ⚙️ Step-by-Step Configuration with Screenshots

### 🧩 Step 1: Installing OPNsense
**Goal:** Install OPNsense inside VMware and prepare it for network configuration.

- ![OPNsense Installation Screen](images/01-opnsense-install.png)  
  → Beginning the installation process for OPNsense in VMware.

- ![Installation Complete](images/02-opnsense-install-complete.png)  
  → Installation completed successfully; ready for initial login.

---

### 🌐 Step 2: Interface Assignments
**Goal:** Assign each OPNsense interface (WAN, LAN, Finance, OPT2) to its respective VMnet network.

- ![Interface Assignments](images/03-interface-assignments.png)  
  → Mapping each virtual adapter to a VMware network. Each VMnet simulates a separate physical segment.

- ![Set Interface IPs](images/04-set-interface-ips.png)  
  → Assigning static IPs for LAN, Finance, and optional interfaces inside OPNsense.

- ![Assign Interfaces in Console](images/05-assign-interfaces.png)  
  → Confirming that each interface is correctly identified and configured.

---

### 🧮 Step 3: DHCP and Network Configuration
**Goal:** Enable and configure DHCP for LAN and Finance networks so clients automatically receive IP addresses.

- ![DHCP Configuration](images/06-dhcp-config.png)  
  → Enabling DHCP service on both LAN and Finance interfaces.

- ![OPNsense Services View](images/07-opnsense-services.png)  
  → Verifying that DHCP and DNS services are running properly.

- ![Finance DHCP Range](images/08-dhcp-finance-range.png)  
  → Defining the Finance DHCP pool (192.168.10.100–192.168.10.200).

- ![Final Interface Config](images/09-final-interface-config.png)  
  → Reviewing all interface IPs and DHCP settings before applying.

---

### 🧭 Step 4: Web GUI Configuration
**Goal:** Access OPNsense via the web interface (https://192.168.1.1) and complete setup wizard.

- ![Wizard Welcome](images/10-wizard-welcome.png)  
  → Starting the OPNsense setup wizard in the browser.

- ![Wizard Finish](images/11-wizard-finish.png)  
  → Completing setup and applying configuration defaults.

- ![OPNsense Dashboard](images/12-dashboard.png)  
  → The dashboard confirms active interfaces, gateways, and services.

---

### 🔥 Step 5: Firewall Rules and Connectivity Testing
**Goal:** Apply firewall rules to restrict or allow traffic between subnets and confirm proper routing.

- ![Firewall Rule for Finance](images/13-firewall-rule-finance.png)  
  → Creating rules to control access from Finance to LAN and WAN.

---

### 🧪 Step 6: Connectivity Verification
**Goal:** Ensure LAN devices can access the internet, and inter-VLAN routing works correctly.

- ![Ping Test Results](images/Screenshot%202025-11-06%20032020.png)  
  → Successful ping to 8.8.8.8 and google.com confirms internet access through OPNsense NAT.

---

## ✅ Results

- Successfully deployed a **multi-interface OPNsense firewall** in a virtualized lab.  
- Verified **LAN internet access** and **Finance subnet routing**.  
- Demonstrated DHCP configuration, routing, and interface separation within OPNsense.  
- Captured screenshots for all core setup stages.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|----------|
| **VMware Workstation Pro** | Virtualization platform |
| **OPNsense 25.7** | Open-source firewall and router |
| **Ubuntu 24.04 LTS** | Client operating system |
| **PowerShell / Git** | Version control and documentation |

---

## 🪪 License
This project is licensed under the **MIT License** — free to use, modify, and share for educational purposes.
