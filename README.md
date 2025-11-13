# 🧭 Small Office Network Configuration Project

This project demonstrates the setup and configuration of a **small organizational network** using Cisco Packet Tracer.  
It includes a **router**, multiple **switches**, a **server**, and several **client PCs** across different departments — **IT**, **HR**, and **Sales** — all interconnected to enable seamless communication and resource sharing.

---

## 📸 Network Topology

![Network Topology](https://raw.githubusercontent.com/najibulazam/Small-Office-Network-Configuration-Project/main/Small%20Organization%20Project.png)

**Departments and Devices:**
- **IT Department (192.168.2.0/24)**
  - PCs: `192.168.2.2`, `192.168.2.3`
- **Sales Department (192.168.3.0/24)**
  - PCs: `192.168.3.2`, `192.168.3.3`
- **HR Department (192.168.4.0/24)**
  - PCs: `192.168.4.2`, `192.168.4.3`
- **Server Department (192.168.1.0/24)**
  - Server: `192.168.1.100`

**Router Interfaces:**
| Interface | IP Address   | Department |
|------------|--------------|-------------|
| F0/1       | 192.168.1.1  | Server |
| F0/0       | 192.168.2.1  | IT |
| F1/1       | 192.168.3.1  | Sales |
| F1/0       | 192.168.4.1  | HR |

---

## 🧩 Objectives

- Configure and interconnect multiple departments via a central router.
- Assign IP addresses and gateways to all devices.
- Set up a **DNS Server** for name resolution.
- Host a simple **HTTP Web Page** on the server.
- Verify connectivity and troubleshoot DNS and routing issues.

---

## ⚙️ Configuration Steps

### 1. **Device Setup**
- Connect the router to four switches.
- Connect departmental PCs and a server to their respective switches.
- Label devices for clarity.

### 2. **IP Address Assignment**
Assign static IPs to all PCs and the server according to their subnet.  
Set the **default gateway** for each department to the router interface IP (e.g., IT → `192.168.2.1`).

### 3. **Router Configuration**
Use the Cisco CLI to configure interfaces:
```bash
Router> enable
Router# configure terminal
Router(config)# interface f0/1
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown

Router(config)# interface f0/0
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# no shutdown

Router(config)# interface f1/1
Router(config-if)# ip address 192.168.3.1 255.255.255.0
Router(config-if)# no shutdown

Router(config)# interface f1/0
Router(config-if)# ip address 192.168.4.1 255.255.255.0
Router(config-if)# no shutdown
