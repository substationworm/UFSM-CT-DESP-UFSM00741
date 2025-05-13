# UFSM00741 - Exercise List 02

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Exercise 01 - Set/Reset Coils

- 👷 **Control Logic Description:**
    - A hydraulic pump starts pumping water from a reservoir if:
        - The control circuit is active.
        - There is sufficient water in the reservoir, as indicated by the level sensor.
- 🏷️ **Minimum Requirements:**
    - Start button (1x): `START = %I0.0`.
    - Stop button (1x): `STOP = %I0.1`.
    - Water level dectector (1x): `WATER = %I0.2`.
    - Set/Reset outputs (2x): `PUMP_CTRL = %Q0.0 (S/R)`.
    - Memory bit for reset trigger (1x): `RST_MEM = %M0`.

## 📝 Exercise 02 - Forward-Reverse Control of a Motor

- 🏷️ **Minimum Requirements:**
    - Normally open contacts for forward-reverse control (2x):
        - `START_FWD = %I0.0`.
        - `START_REV = %I0.1`.
    - Stop push-button (1x): `STOP = %I0.2`.
    - Overcurrent protection device (1x): `PROT_OC = %I0.3`.
    - Contactors/Outputs for forward-reverse operation (2x):
        - `MOTOR_FWD = %Q0.0`.
        - `MOTOR_REV = %Q0.1`.

## 📝 Exercise 03 - Forward-Reverse Control of a Motor with Timers

- 🏷️ **Minimum Requirements:**
    - Normally open contacts for forward-reverse control (2x):
        - `START_FWD = %I0.0`.
        - `START_REV = %I0.1`.
    - Temporizadores para o forward-reverse control (2x):
        - `T01`.
        - `T02`.
    - Stop push-button (1x): `STOP = %I0.2`.
    - Overcurrent protection device (1x): `PROT_OC = %I0.3`.
    - Contactors/Outputs for forward-reverse operation (2x):
        - `MOTOR_FWD = %Q0.0`.
        - `MOTOR_REV = %Q0.1`.

## 📝 Exercise 04 - Automatic Packaging with Counter (Part 01)

- 👷 **Control Logic Description:**
    - A conveyor belt moves objects that are deposited into a package.
    - The package holds fifteen objects, counted by a sensor.
    - Once the maximum capacity is reached, the package is sealed and dispatched.
- 🏷️ **Minimum Requirements:**
    - Object sensor: `SNS = %I0.0`.
    - Packing completed status: `PKG_DONE = %Q0.0`.
    - Counter de objetos: `C01`.
    - Reset function for counter and dispatch procedure: `DISP_RST = %Q0.1`.

## 📝 Exercise 05 - Automatic Packaging with Counter (Part 02)

- 👷 **Control Logic Description:**
    - A conveyor belt moves objects that are deposited into a package.
    - The package holds fifteen objects, counted by a sensor.
    - Once the maximum capacity is reached, the package is sealed and dispatched.
    - A second counter tracks the number of dispatched packages.
    - When the total reaches 20 packages, the system stops.
- 🏷️ **Minimum Requirements:**
    - Object sensor: `SNS = %I0.0`.
    - Packing completed status: `PKG_DONE = %Q0.0`.
    - Object counter: `C01`.
    - Package counter: `C01`.
    - Reset function for counter and dispatch procedure: `DISP_RST = %Q0.1`.
    - System lock (stop function): `SYS_LOCK = %Q0.2`.

## 📝 Exercise 06 - Warehouse Product Inflow and Outflow Control

- 👷 **Control Logic Description:**
    - Product inflow and outflow are managed through a counter.
    - When the warehouse reaches maximum capacity, an alarm is triggered.
- 🏷️ **Minimum Requirements:**
    - Product inflow: `IN_FLOW = %I0.0`.
    - Product outflow: `OUT_FLOW = %I0.1`.
    - Alarm: `ALARM = %Q0.0`.
    - Counter reset: `RST = %I0.2`.
    - Counter: `C01`.