# 🚀 Spine-Leaf eBGP VXLAN Fabric Lab

## 📌 Overview

This project simulates a modern Data Center fabric using a Spine-Leaf architecture with:

- 🔹 eBGP Underlay
- 🔹 ECMP load balancing
- 🔹 VXLAN Overlay
- 🔹 Multi-Tenant segmentation
- 🔹 Linux bridging and VXLAN VTEPs
- 🔹 FRRouting (FRR)

The lab was built in GNS3 using FRRouting containers and VPCS hosts to emulate a scalable VXLAN fabric similar to modern enterprise and cloud networking environments.

---

# 🏗️ Architecture

## 🌐 Underlay

The underlay network uses eBGP between Spine and Leaf switches to provide routed IP connectivity across the fabric.

### ✅ Features implemented

- 🔹 eBGP Spine-Leaf design
- 🔹 Loopback reachability
- 🔹 ECMP multipath routing
- 🔹 Clos Fabric topology

---

## 🌉 Overlay

The overlay network uses VXLAN to extend Layer-2 segments across the routed underlay.

### ✅ Features implemented

- 🔹 VXLAN VTEPs
- 🔹 Multiple VNIs
- 🔹 Multi-tenant segmentation
- 🔹 Layer-2 extension over Layer-3 fabric

---

# 🖧 Topology

```text
             Spine1
            /      \
           /        \
        Leaf1------Leaf2
           \        /
            \      /
             Spine2
```

---

# 🛠️ Technologies Used

- 🔹 FRRouting (FRR)
- 🔹 BGP
- 🔹 VXLAN
- 🔹 Linux Networking
- 🔹 GNS3
- 🔹 VPCS
- 🔹 Linux Bridges
- 🔹 ECMP
- 🔹 Clos Fabric Architecture

---

# 🌍 IP Addressing

## 🌐 Underlay

| Link | Network |
|------|----------|
| Spine1 ↔ Leaf1 | 10.0.11.0/30 |
| Spine1 ↔ Leaf2 | 10.0.12.0/30 |
| Spine2 ↔ Leaf1 | 10.0.21.0/30 |
| Spine2 ↔ Leaf2 | 10.0.22.0/30 |

---

## 🔁 Loopbacks

| Device | Loopback |
|--------|-----------|
| Spine1 | 1.1.1.1 |
| Spine2 | 1.1.1.2 |
| Leaf1 | 2.2.2.2 |
| Leaf2 | 3.3.3.3 |

---

# 🏢 Multi-Tenant VXLAN Design

| Tenant | VNI | Subnet |
|--------|-----|---------|
| Tenant-A | 10010 | 192.168.10.0/24 |
| Tenant-B | 10020 | 192.168.20.0/24 |

---

# ✅ Validation Tests

## 🌐 Underlay Validation

- 🔹 BGP adjacency verification
- 🔹 ECMP route installation
- 🔹 Loopback reachability

### 🧪 Commands used

```bash
show ip bgp summary
show ip route bgp
```

---

## 🌉 Overlay Validation

- 🔹 VXLAN tunnel verification
- 🔹 MAC learning over VXLAN
- 🔹 Tenant isolation tests

### 🧪 Commands used

```bash
bridge fdb show
bridge vlan show
```

---

# 📡 Connectivity Results

## 🟢 Tenant-A

- ✅ PC1 ↔ PC2

## 🔵 Tenant-B

- ✅ PC3 ↔ PC4

## 🔒 Isolation Test

- ❌ Tenant-A ↔ Tenant-B

Successful traffic isolation was achieved using separate VXLAN VNIs.

---

# 🧠 Challenges and Troubleshooting

During the implementation several issues were identified and resolved:

- ⚠️ FRR "(Policy)" BGP state
- ⚠️ Linux bridge membership issues
- ⚠️ VXLAN MAC learning
- ⚠️ VTEP reachability
- ⚠️ VXLAN encapsulation over the underlay
- ⚠️ Bridge VLAN configuration
- ⚠️ Interface binding to Linux bridges

These troubleshooting scenarios provided practical experience with Linux networking and VXLAN operations.

---

# 🔮 Future Improvements

Planned next steps for the lab:

- 🚀 BGP EVPN Control Plane
- 🚀 Dynamic MAC learning via EVPN
- 🚀 VRF implementation
- 🚀 Anycast Gateway
- 🚀 Distributed routing
- 🚀 Automation with Python and Netmiko
- 🚀 Containerized workloads

---

# 📸 Screenshots

## 🌐 BGP Underlay

<img width="1043" height="639" alt="image" src="https://github.com/user-attachments/assets/e7adbaad-d33a-418b-949d-0c88700467a7" />
<img width="1025" height="669" alt="image" src="https://github.com/user-attachments/assets/b2e1e77e-5f24-4944-aecc-b13936fea5fc" />
<img width="1031" height="792" alt="image" src="https://github.com/user-attachments/assets/757db2b7-ebc1-4a96-9e6a-664152d066d2" />
<img width="1027" height="768" alt="image" src="https://github.com/user-attachments/assets/602b0c69-9773-4ae5-be24-d207bb7b0913" />

---

## ⚖️ ECMP Routing



---

## 🌉 VXLAN MAC Learning
<img width="859" height="1039" alt="image" src="https://github.com/user-attachments/assets/64665f46-ce44-4f48-afb6-f33c1dd2b96f" />

<img width="859" height="1039" alt="image" src="https://github.com/user-attachments/assets/f05620d1-3ba1-4f2d-b29b-46320481717d" />


---

## 📡 Tenant Connectivity Tests
<img width="1296" height="812" alt="image" src="https://github.com/user-attachments/assets/7b5d966b-b57d-4468-81b8-f60156174898" />
<img width="1346" height="869" alt="image" src="https://github.com/user-attachments/assets/88b86316-d626-4849-af8e-bc3e4c750020" />



---

# 👨‍💻 Author

## Jaime Alexander Rosero Mesa

Network Engineer focused on:

- 🔹 Data Center Networking
- 🔹 BGP
- 🔹 VXLAN
- 🔹 Linux Networking
- 🔹 Network Automation
- 🔹 Modern Enterprise Infrastructure
