# UFSM00741 - Exercise List 04

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Exercise 01 - Packaging Station Control with Counter

- 👷 **Control Logic Description:**
    - A sensor counts the passage of products on a conveyor.
    - Every 10 products, a packaging piston is activated for 2 seconds to push the products into the package.
    - After this, the counter is reset and the process restarts.
    - A reset button allows the counter to be manually reset at any time.
    - An emergency stop button must halt the entire process, disabling both the piston activation and product counting.
- 🏷️ **Minimum Requirements:**
    - Sensor: `Sensor` (type: `BOOL`).
    - Reset button: `Reset` (type: `BOOL`).
    - Emergency stop button: `Emergency` (type: `BOOL`).
    - Packaging piston: `Piston` (type: `BOOL`).
    - Counter: `Counter` (type: `CTU`).
    - Timer: `Timer` (type: `TON`).
    - Process state: `State` (type: `INT`).
- 📋 **Instructions:**
    - The control system must be implemented using structured text (ST).

## 📝 Exercise 02 - Conveyor System with Size-Based Sorting

- 👷 **Control Logic Description:**
    - A conveyor belt transports metal parts to an inspection station. A distance sensor detects the size of each part (classified as small or large). Based on the measured size:
        - 📦 Small parts are routed to Bin A.
        - 📦 Large parts are routed to Bin B.
    - The sorting mechanism consists of an actuator with two discrete positions: one directing parts to Bin A, and the other to Bin B.
- 🏷️ **Minimum Requirements:**
    - Presence sensor: `Sensor` (type: `BOOL`).
    - Part height: `PartHeight` (type: `REAL`).
    - Conveyor activation: `Conveyor` (type: `BOOL`).
    - Routing to Bin A: `RouteToA` (type: `BOOL`).
    - Routing to Bin B: `RouteToB` (type: `BOOL`).
- 📋 **Instructions:**
    - The system must be controlled using function block diagram (FBD).
        - 👉 One function block in ladder diagram (LD) shall be used to control the conveyor.
        - 👉 Onde function block in structured text (ST) shall be used to classify the parts.

## 📝 Exercise 03 - Direct Start of an Electric Motor

- 🏷️ **Minimum Requirements:**
    - Start button: `Start` (type: `BOOL`).
    - Stop button: `Stop` (type: `REAL`).
    - Overcurrent protection: `Overcurrent` (type: `BOOL`).
    - Motor: `Motor` (type: `BOOL`).
- 📋 **Instructions:**
    - The control system must be programmed using instruction list (IL).