# OPNsense Multi-Network Lab

This project demonstrates the configuration of **OPNsense** as a multi-interface firewall and router in a virtual lab environment.  
The lab was built using **VMware Workstation**, **Ubuntu 24.04**, and **OPNsense 25.7** to simulate a small business network with separate LANs for departments like *Finance*.

---

## 🧠 Project Overview

**Goal:**  
To design and implement an isolated lab environment where OPNsense routes traffic between multiple internal networks while maintaining internet connectivity through a NAT interface.

**Topology Summary:**
- **OPNsense Router (R1)**  
  - `em0 (WAN)` → NAT (connected to the host for internet)  
  - `em1 (LAN)` → 192.168.1.0/24  
  - `em2 (Finance)` → 192.168.10.0/24  
  - `em3 (OPT2)` → 192.168.20.0/24  

- **Ubuntu Clients:**  
  - One Ubuntu VM connected to the **LAN** network  
  - One Ubuntu VM connected to the **Finance** network  

---

## ⚙️ Configuration Steps

### 1. Installing OPNsense
![Install OPNsense](images/01-opnsense-install.png)
![Install Complete](images/02-opnsense-install-complete.png)

### 2. Interface Assignments
![Interface Assignments](images/03-interface-assignments.png)
![Set Interface IPs](images/04-set-interface-ips.png)
![Assign Interfaces](images/05-assign-interfaces.png)

### 3. DHCP & Basic Config
![DHCP Config](images/06-dhcp-config.png)
![OPNsense Services](images/07-opnsense-services.png)
![Finance DHCP Range](images/08-dhcp-finance-range.png)
![Final Interface Config](images/09-final-interface-config.png)

### 4. Web Interface Setup
![Wizard Welcome](images/10-wizard-welcome.png)
![Wizard Finish](images/11-wizard-finish.png)
![Dashboard](images/12-dashboard.png)

### 5. Firewall & Testing
![Firewall Rule Finance](images/13-firewall-rule-finance.png)
![Finance No Internet](images/14-finance-no-internet.png)

---

## ✅ Results

- Successfully configured multi-network routing via OPNsense.  
- Verified LAN internet access via ping tests to `8.8.8.8` and `google.com`.  
- Demonstrated how VLAN isolation or firewall rules can block specific subnets (e.g., Finance).

---

## 🧩 Tools Used
- **VMware Workstation**
- **OPNsense 25.7**
- **Ubuntu 24.04 LTS**
- **PowerShell / CLI for configuration tracking**

---

## 📸 Screenshots
All configuration screenshots are available in the `images/` folder.

---

## 📄 License
This project is licensed under the MIT License.  
Feel free to clone, modify, and learn from it.
