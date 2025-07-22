# GVLan Configuration

This repository contains configuration files and documentation for setting up a VLAN-segmented network using standard Layer 3 addressing. Each VLAN represents a different department in the organization.

---

## VLAN Overview

| VLAN ID | Name        | Subnet            | Description                 |
|---------|-------------|-------------------|-----------------------------|
| 10      | Marketing   | 192.168.1.0/24     | Used for marketing team     |
| 20      | Sales       | 192.168.2.0/24     | Used for sales department   |
| 30      | Engineering | 192.168.3.0/24     | Used for development team   |
| 40      | HR          | 192.168.4.0/24     | Used for HR and payroll     |

---

## Configuration Goals

- **Segmentation:** Isolate traffic between departments to improve security and manageability.
- **Scalability:** Allow easy addition of new departments or devices.
- **Centralized Management:** Compatible with centralized DHCP and firewall policies.

---

## Sample VLAN Configuration (Cisco IOS Syntax)

```bash
# VLAN Creation
vlan 10
 name Marketing
vlan 20
 name Sales
vlan 30
 name Engineering
vlan 40
 name HR

# Interface Assignment
interface GigabitEthernet0/1
 switchport mode access
 switchport access vlan 10

interface GigabitEthernet0/2
 switchport mode access
 switchport access vlan 20

interface GigabitEthernet0/3
 switchport mode access
 switchport access vlan 30

interface GigabitEthernet0/4
 switchport mode access
 switchport access vlan 40
