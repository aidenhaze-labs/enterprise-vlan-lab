# Enterprise VLAN Lab
## Overview

This project simulates a small office network in Cisco Packet Tracer. The network utilizes:

- VLAN segmentation
- trunk/access port configurations
- router-on-a-stick inter-VLAN routing

The goal of this lab was to utilize common Layer 2 and Layer 3 networking concepts used in enterprise environments.

## Network Topology

<img width="1895" height="726" alt="image" src="https://github.com/user-attachments/assets/26df3e36-6433-4528-bac9-00bb355bfbd4" />

## VLAN Design

| VLAN | Name | Subnet |       Purpose |
|------|------|--------------|---------|
| 10   | IT   | 192.168.1.0/24 | IT Department |
| 20   | SALES | 192.168.2.0/24 | Sales Department |
| 30   | GUEST | 192.168.3.0/24 | Guest devices |

## Configurations

### Access Port Example

    interface fa0/1 
    switchport mode access 
    switchport access vlan 10

### Trunk Port Example

    interface fa0/24
    switchport mode trunk
    switchport trunk allowed vlan 10,20,30

## Router-on-a-Stick Example

    interface g0/0.10
    encapsulation dot1Q 10
    ip address 192.168.1.1 255.255.255.0
