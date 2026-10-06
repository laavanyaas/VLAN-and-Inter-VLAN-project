# VLAN and Inter-VLAN Routing Labs (Cisco Packet Tracer)

Hands-on labs from my **CCNA** course on creating VLANs and routing between them, built in **Cisco Packet Tracer 9.0**.


## Labs at a Glance

| # | Lab | Topic | Routers | Switches | PCs |
| --- | --- | --- | --- | --- | --- |
| 1 | [VLAN + Four-Router Lab](#1-vlan--four-router-lab) | 8 VLANs and a four-router backbone | 4 | 4 | 14 |
| 2 | [Inter-VLAN Routing Lab](#2-inter-vlan-routing-lab) | 7 VLANs across 4 switches routed by one router | 1 | 4 | 14 |

## Tools Used

- Cisco Packet Tracer 9.0
- Cisco ISR / PT8200 / CGR1240 routers
- Cisco 2960-24TT switches
- PC-PT end devices

---

## 1. VLAN + Four-Router Lab

**Objective:** Build a four-router backbone with eight VLANs spread across four switches.

![VLAN + Four-Router Lab](images/vlan-multi-router-lab.png)

| VLAN | Name | Subnet |
| --- | --- | --- |
| 10 | a | 172.18.10.0/24 |
| 20 | b | 172.18.20.0/24 |
| 30 | c | 172.16.10.0/24 |
| 40 | d | 172.16.20.0/24 |
| 50 | e | 10.20.7.0/24 |
| 60 | f | 10.10.5.0/24 |
| 70 | g | 192.168.40.0/24 |
| 80 | h | 192.168.30.0/24 |

| Router link | Subnet |
| --- | --- |
| Router0 – Router2 | 10.10.1.0/24 |
| Router0 – Router1 | 40.30.10.0/24 |
| Router1 – Router3 | 30.20.10.0/24 |
| Router2 – Router3 | 20.10.0.0/24 |

**Verification:** `show vlan brief`, `show ip route`, and pings between PCs in different VLANs.

---

## 2. Inter-VLAN Routing Lab

**Objective:** Create seven VLANs across four switches and route between them using a single central router.

![Inter-VLAN Routing Lab](images/inter-vlan-routing-lab.png)

| VLAN | Name | Subnet |
| --- | --- | --- |
| 10 | hr | 172.16.1.0/24 |
| 20 | SALES | 172.16.2.0/24 |
| 30 | dev | 10.10.5.0/24 |
| 40 | python | 192.168.1.0/24 |
| 50 | react | 172.20.5.0/24 |
| 60 | namedb | 10.20.1.0/24 |
| 70 | test | 172.16.3.0/24 |

Topology: a CGR1240 router connects to Switch0, Switch2, and Switch3, while Switch1 connects to Switch0 over a trunk link. Each switch carries one or two VLANs with two PCs per VLAN.

**Verification:** `show vlan brief`, `show interfaces trunk`, and pings between PCs in different VLANs.

---

## Useful Commands

```
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
show running-config
ping <ip-address>
```

## Skills Demonstrated

- VLAN creation and naming
- Access and trunk port configuration
- Inter-VLAN routing
- IP addressing and subnetting
- Troubleshooting with `show` commands and ping

## Author

**Lavanya** – CCNA course labs
