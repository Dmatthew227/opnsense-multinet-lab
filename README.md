# 🧱 OPNsense Multi-Network Lab (VMware Workstation)

This project demonstrates the setup and configuration of **OPNsense 25.7** as a multi-interface firewall and router inside a **virtualized environment**.  
It simulates a small enterprise network with multiple departments — each on its own subnet — and shows how to route and control traffic between them.

---

## 🧠 Project Overview

**Goal:**  
Design and implement a multi-network environment using **OPNsense** to route and secure traffic between isolated LANs (e.g., Finance and General LAN), while maintaining controlled internet access.

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
| `em3` | OPT2 | 192.168.20.0/24 | Gateway: 192.168.20.1 | Optional test subnet |

---

## ⚙️ Step-by-Step Configuration with Screenshots

### 🧩 Step 1: Installing OPNsense
**Goal:** Install OPNsense inside VMware and verify that all network interfaces are recognized.

- ![Installation Screen](images/01-opnsense-install.png)  
  → Beginning installation of OPNsense inside VMware Workstation.

- ![Installation Complete](images/02-opnsense-install-complete.png)  
  → Installation complete — OPNsense ready for initial configuration.

---

### 🌐 Step 2: Assigning Interfaces
**Goal:** Assign and confirm the correct interface mapping for WAN, LAN, and Finance networks.

- ![Interface Assignments](images/03-interface-assignments.png)  
  → Mapping each OPNsense virtual adapter (em0–em3) to a VMware network.

- ![Assign Interfaces in Console](images/04-assign-interfaces.png)  
  → Confirming OPNsense recognizes and labels all connected interfaces properly.

- ![Set Interface IPs](images/05-set-interface-ips.png)  
  → Setting static IP addresses for each subnet (LAN, Finance, OPT2).

---

### 🧮 Step 3: DHCP and Internal Network Configuration
**Goal:** Enable DHCP servers on LAN and Finance networks so Ubuntu clients receive IPs automatically.

- ![DHCP Configuration](images/06-dhcp-config.png)  
  → Enabling DHCP and defining IP pools for LAN and Finance.

- ![Finance DHCP Range](images/07-dhcp-finance-range.png)  
  → Finance subnet DHCP range: 192.168.10.100–192.168.10.200.

- ![OPNsense Services View](images/08-opnsense-services.png)  
  → Verifying DHCP, DNS Resolver, and routing services are running correctly.

- ![Final Interface Config](images/09-final-interface-config.png)  
  → Reviewing all assigned interface IPs and confirming configuration.

---

### 🧭 Step 4: Web GUI Setup
**Goal:** Access OPNsense web GUI via browser and complete the setup wizard.

- ![Wizard Welcome](images/10-wizard-welcome.png)  
  → Accessing the configuration wizard at https://192.168.1.1.

- ![Wizard Finish](images/11-wizard-finish.png)  
  → Finalizing wizard configuration and applying system defaults.

- ![Dashboard](images/12-dashboard.png)  
  → Main OPNsense dashboard displaying system status, gateway, and traffic graphs.

---

### 🔥 Step 5: Firewall Configuration and Testing
**Goal:** Create and test firewall rules to control access between VLANs and verify outbound internet access.

- ![Firewall Rule for Finance](images/13-firewall-rule-finance.png)  
  → Creating access rules on the Finance interface to allow or restrict LAN/internet connectivity.

---

### 🧪 Step 6: Connectivity Verification
**Goal:** Confirm LAN and Finance clients receive IP addresses and can reach external networks through OPNsense NAT.

- ![Ping Test Results](images/Screenshot%202025-11-06%20032020.png)  
  → Successful ping to 8.8.8.8 and google.com confirms outbound connectivity from LAN and proper routing.

---

## ✅ Results

- Successfully deployed a **multi-interface OPNsense firewall** inside a virtual lab environment.  
- Configured **VLANs/subnets, DHCP, and firewall rules** for traffic control.  
- Verified **internet access and routing functionality** through OPNsense NAT.  
- Documented all key configuration steps with screenshots for replication and learning.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|----------|
| **VMware Workstation Pro** | Virtualization platform |
| **OPNsense 25.7** | Open-source firewall and router |
| **Ubuntu 24.04 LTS** | Client OS for testing |
| **PowerShell / Git** | Version control and documentation |

---

## 🪪 License
This project is licensed under the **MIT License** — free to use, modify, and share for educational purposes.
