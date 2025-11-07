# 🧱 OPNsense Multi-Network Lab (VMware Workstation)

This project demonstrates the setup and configuration of **OPNsense 25.7** as a multi-interface firewall and router inside a **virtualized lab environment** using **VMware Workstation Pro**.  
It simulates a small enterprise network with multiple departments — each on its own subnet — and shows how to route and secure traffic between them.

---

## 🧠 Project Overview

**Objective:**  
Design and deploy a virtualized network environment where **OPNsense** acts as the core router and firewall.  
The lab demonstrates:
- Multi-interface routing  
- DHCP server configuration  
- Firewall segmentation  
- Connectivity verification across isolated subnets  

**Virtualization Platform:**  
VMware Workstation Pro

**Operating Systems Used:**
- **OPNsense 25.7** – Router / Firewall  
- **Ubuntu 24.04 LTS** – Client machines (LAN and Finance)

---

## 🌐 Network Topology

| Interface | Role | Network | IP/Subnet | Description |
|------------|------|----------|------------|--------------|
| `em0` | WAN | NAT | DHCP | Internet access via host |
| `em1` | LAN | 192.168.1.0/24 | Gateway: 192.168.1.1 | General office LAN |
| `em2` | Finance | 192.168.10.0/24 | Gateway: 192.168.10.1 | Finance subnet |
| `em3` | OPT2 | 192.168.20.0/24 | Gateway: 192.168.20.1 | Optional test subnet |

---

## ⚙️ Step-by-Step Configuration with Screenshots

### 🧩 Step 1: Installing OPNsense
**Goal:** Install OPNsense inside VMware and verify all network interfaces are detected.

- ![Installation Screen](images/01-opnsense-install.png)  
  → Starting the OPNsense installation in VMware Workstation.

- ![Installation Complete](images/02-opnsense-install-complete.png)  
  → Installation completed — system ready for interface configuration.

---

### 🌐 Step 2: Assigning Network Interfaces
**Goal:** Map each OPNsense interface (WAN, LAN, Finance, OPT2) to a corresponding VMware virtual network (VMnet).

- ![Interface Assignments](images/03-interface-assignments.png)  
  → Assigning adapters to WAN, LAN, and Finance networks.

- ![Interface Confirmation](images/04-assign-interfaces.png)  
  → Confirming OPNsense recognizes all connected interfaces.

- ![Set Interface IPs](images/05-set-interface-ips.png)  
  → Assigning IPs for LAN (192.168.1.1) and Finance (192.168.10.1).

---

### 🧮 Step 3: DHCP Configuration
**Goal:** Enable and configure DHCP servers so clients receive IPs automatically.

- ![Enable DHCP](images/06-dhcp-config.png)  
  → Enabling DHCP services on LAN and Finance interfaces.

- ![Finance DHCP Range](images/07-dhcp-finance-range.png)  
  → Defining Finance DHCP range: 192.168.10.100–192.168.10.200.

- ![Services Running](images/08-opnsense-services.png)  
  → Verifying that DHCP and DNS Resolver services are active.

- ![Final Interface Overview](images/09-final-interface-config.png)  
  → Reviewing interface IPs and DHCP configurations before applying.

---

### 🧭 Step 4: Web GUI Setup
**Goal:** Access OPNsense web GUI and complete the initial configuration wizard.

- ![Wizard Welcome](images/10-wizard-welcome.png)  
  → Accessing OPNsense GUI at https://192.168.1.1 and starting setup.

- ![Wizard Finish](images/11-wizard-finish.png)  
  → Completing the setup wizard and applying defaults.

- ![Dashboard Overview](images/12-dashboard.png)  
  → Dashboard shows interfaces, gateways, and system statistics.

---

### 🔥 Step 5: Firewall Configuration
**Goal:** Create firewall rules to isolate and control traffic between Finance and LAN subnets.

- ![Firewall Rule Finance](images/13-firewall-rule-finance.png)  
  → Adding custom rules on the Finance interface to manage LAN and internet access.

---

### 🧪 Step 6: Connectivity Testing
**Goal:** Verify routing, DHCP functionality, and outbound internet access.

- ![Ping Test Results](images/Screenshot%202025-11-06%20032020.png)  
  → Successful ping to 8.8.8.8 and google.com confirms outbound NAT and routing are functional.

---

## ✅ Results

- Built and configured a **multi-interface OPNsense firewall** within VMware Workstation.  
- Implemented **DHCP, routing, and interface segmentation** for isolated subnets.  
- Verified **internet connectivity and inter-VLAN control** through firewall rules.  
- Documented each configuration stage for reproducibility and portfolio presentation.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|----------|
| **VMware Workstation Pro** | Virtualization platform |
| **OPNsense 25.7** | Firewall and router |
| **Ubuntu 24.04 LTS** | Client testing systems |
| **PowerShell / Git** | Documentation and version control |

---

## 🪪 License
This project is licensed under the **MIT License** — free to use, modify, and share for educational purposes.
