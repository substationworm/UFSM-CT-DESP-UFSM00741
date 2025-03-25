# UFSM00741 - Homework 01

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Task 01 - Collisions Domains

- 🖥️ **Equipment:**
    - 🌐 01 hub.
    - 🌐 01 switch.
    - 🖳 03 PCs.
- 📋 **Procedures:**
    1. Connect all PCs to the hub using straight-through cables.
    2. Assign simple IP addresses, for example:
        - 🖳 PC0: `192.168.1.10`.
        - 🖳 PC1: `192.168.1.11`.
        - 🖳 PC2: `192.168.1.12`.
    3. Perform simultaneous ping tests between PCs (e.g., PC0 ➡️ PC1 while PC2 ➡️ PC1 at the same time).
    4. Observe any potential collisions or delays in response time.
    5. Replace the hub from the initial setup with the switch, keeping the same connections and IP addresses.
    6. Repeat the simultaneous ping tests.
    7. Observe the absence of collisions and improved performance.
- ❓ **Discussion Questions:**
    1. How many collision domains are present in each scenario?
    2. Why does performance improve when using a switch?

## 📝 Task 02 - Broadcast Domains and Inter-Network Communication

- 🖥️ **Equipment and Connections:**
    - 🌐 01 router (connected to SW0 and SW1), e.g., model 2960.
    - 🌐 02 switches: SW0 (connected to PC0) and SW1 (connected to PC1), e.g., model 2911.
    - 🖳 02 PCs.
- 🔧 **Configurations:**
    - **Network 1:** PC0 and SW0.
        - PC0: `192.168.10.10/24`.
        - Gateway: `192.168.10.1`.
    - **Network 2:** PC1 and SW1.
        - PC1: `192.168.20.10/24`
        - Gateway: `192.168.20.1`.
    - **Router Interfaces:**
        - G0/0: `192.168.10.1/24`.
        - G0/1: `192.168.20.1/24`.
        - Use the commands `ip address` and `no shutdown` to enable the interfaces.
- 📋 **Procedures:**
    1. Assemble the topology using the specified equipment.
    2. Assign the indicated IP addresses to each PC.
    3. Configure the router interfaces with the corresponding subnet IP addresses.
    4. In **Simulation Mode**, from PC0, send a ping to the local broadcast address: `ping 192.168.10.255`.
    5. Observe the following:
        - The broadcast packet is delivered only within Network 1's domain.
        - PC1 does not receive the broadcast originating from Network 1.
- ❓ **Discussion Questions:**
    1. Did the broadcast sent by PC0 reach PC1? Why or why not?
    2. If another PC were added to Network 1, would it receive the broadcast? Explain.
    3. What would happen if the router were replaced with a switch?
    4. Why are excessively large broadcast domains detrimental to network performance?





