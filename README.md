# 🔬 Cisco Networking Labs — Packet Tracer

> CCNA-level hands-on labs covering subnetting, routing protocols (RIP, OSPF), and DHCP configuration.  
> Built as part of my networking studies alongside my Master's in Cybersecurity at EPITA Paris.

---

## 📁 Lab Files

| File | Topic | Concepts Covered |
|------|-------|-----------------|
| `exercise_1.pkt` | Subnetting & Basic Routing | IP addressing, subnet masks, static routes |
| `exercise_4.pkt` | Routing Practice | Multi-router topologies, routing tables |
| `RIP_config.pkt` | RIP v2 | Distance-vector routing, auto-summarisation, convergence |
| `OSPF_config.pkt` | OSPF | Link-state routing, areas, DR/BDR election, cost metric |
| `pratice.pkt` | Mixed Concepts | Subnetting + routing + DHCP combined scenario |
| `ilke-cabral.pkt` | Full Topology | End-to-end network design — subnetting, routing, DHCP |

---

## 🧠 Concepts Covered

### 📐 Subnetting
- CIDR notation and subnet mask calculation
- Dividing a network into multiple subnets
- Identifying network address, broadcast address, and usable host range
- VLSM (Variable Length Subnet Masking) for efficient IP allocation

### 🔄 Routing Protocols

#### RIP v2
- Distance-vector protocol using hop count as metric
- Configuration of RIP on multiple routers
- Understanding convergence and routing loops
- Auto-summarisation and manual summarisation

#### OSPF (Open Shortest Path First)
- Link-state protocol using Dijkstra's algorithm (cost metric)
- Single-area OSPF configuration
- Router ID assignment
- DR/BDR election on multi-access networks
- Verifying adjacencies and LSDB with `show ip ospf neighbor`

### 🖥️ DHCP
- Configuring a Cisco router as a DHCP server
- Defining address pools, default gateway, and DNS
- Excluding static IP ranges from the pool
- Verifying client IP assignment

---

## 🛠️ How to Open These Labs

1. Download and install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with Cisco NetAcad account)
2. Clone this repo:
```bash
git clone https://github.com/ilkecabral/cisco-labs.git
```
3. Open any `.pkt` file directly in Packet Tracer

---

## 💡 Key Commands Reference

### Subnetting & Interfaces
```bash
# Assign IP to interface
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown

# Verify
Router# show ip interface brief
Router# show interfaces
```

### RIP v2
```bash
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# no auto-summary

# Verify
Router# show ip route
Router# show ip protocols
```

### OSPF
```bash
Router(config)# router ospf 1
Router(config-router)# router-id 1.1.1.1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0

# Verify
Router# show ip ospf neighbor
Router# show ip ospf database
Router# show ip route ospf
```

### DHCP
```bash
# Exclude static IPs
Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10

# Create pool
Router(config)# ip dhcp pool LAN_POOL
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# dns-server 8.8.8.8

# Verify
Router# show ip dhcp binding
Router# show ip dhcp pool
```

---

## 📊 Skills Demonstrated

```
Subnetting        ████████████████████  Strong
RIP v2            ████████████████░░░░  Good
OSPF              ████████████████░░░░  Good
DHCP              ████████████████████  Strong
Static Routing    ████████████████████  Strong
Network Design    ███████████████░░░░░  Developing
```

---

## 🗺️ Roadmap — What's Coming Next

- [ ] VLAN configuration and inter-VLAN routing
- [ ] ACL (Access Control Lists) — standard and extended
- [ ] NAT/PAT configuration
- [ ] Multi-area OSPF
- [ ] BGP basics
- [ ] Integration with BuzzLab (pfSense firewall rules ↔ Cisco ACLs)

---

## 🔗 Related

- [BuzzLab](https://github.com/ilkecabral/buzzlab) — my home lab running pfSense, Wazuh SIEM, and Docker on Proxmox VE
- [LinkedIn](https://linkedin.com/in/ilke-cabral)
- [TryHackMe](https://tryhackme.com) — Jr Penetration Tester ✅

---

*Part of my CCNA self-study — Ilke Augusto Cabral, Master's in Cybersecurity, EPITA Paris*
