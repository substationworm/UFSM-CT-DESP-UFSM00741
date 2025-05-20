# UFSM00741 - Exercise List 03

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Exercise 01 - Automatic Fish Reservoir Monitoring

- 👷 **Control Logic Description:**
    - The automatic monitoring system for the fish reservoir uses level sensors and pumps to maintain adequate water levels.
    - The reservoir is equipped with four water level sensors, specified as follows:
        1. Lower level sensor: `SNS_LOW = %I0.0`.
        2. Intermediate low level sensor: `SNS_INT_LOW = %I0.1`.
        3. Intermediate high level sensor: `SNS_INT_HIGH = %I0.2`.
        4. Upper level sensor: `SNS_HIGH = %I0.3`.
    - The reservoir features three pumping systems for water level control:
        1. Water inlet pump: `INLET = %Q0.0`.
        2. Lower drainage pump: `PUMP_BOTTOM = %Q0.1`.
        3. Upper drainage pump: `PUMP_TOP = %Q0.2`.
    - Operating conditions and control actions:
        1. Normal water level:
            - ✅ Active sensors: `SNS_LOW` and `SNS_INT_LOW`.
            - 💧 Action: `PUMP_BOTTOM` and `PUMP_TOP` remain deactivated.
        2. Below acceptable level:
            - ⭕ Active sensors: None.
            - 💧 Actions:
                - The pump `INLET` should be activated to increase the water level.
                - 🔴 The alarm (`ALARM`, red light) should blink to indicate a critical situation.
        3. Above normal level:
            - ✅ Active sensors: `SNS_LOW`, `SNS_INT_LOW`, and `SNS_INT_HIGH`.
            - 💧 Action: The pump `PUMP_BOTTOM` should be activated to drain excess water.
        4. Critical level (above permitted):
            - ✅ Active sensors: All sensors (`SNS_LOW`, `SNS_INT_LOW`, `SNS_INT_HIGH`, `SNS_HIGH`).
            - 💧 Actions:
                - Pumps `PUMP_BOTTOM` and `PUMP_TOP` should operate simultaneously to expedite drainage.
                - 🔴 The alarm should blink to indicate an emergency state.
    - The alarm is manually deactivated by the operator by pressing the reset button (`RESET = %Q0.4`).
    - The alarm is triggered by two alternating timers, ensuring an intermittent signal.
- 🏷️ **Additional Requirements:** 
    - 🟢 Start push-button: `START = %I0.4`.
    - ⚫ Stop push-button: `STOP = %I0.5`.
    - 🔵 Reset push-button: `RESET = %I0.6`.
    - 🔴 Visual alarm: `ALARM = %Q0.3`.
- 📋 **Instructions:**
    1. Develop the control logic using the [Twido Suite by Schneider Electric](https://www.se.com/br/pt/faqs/FA278356/).
    2. Create a human-machine interface (HMI) using [Vijeo Designer Basic by Schneider Electric](https://www.se.com/us/en/download/document/VijeoDesignerBasic/).
    3. Implement the control logic on the programmable logic controller (PLC) [Twido TWDLCDE40DRF by Schneider Electric](https://www.se.com/us/en/product/TWDLCDE40DRF/compact-base-controller-twido-24vdc-supply-compact-24-inputs-with-24vdc-16-output-relays-transparent-ready/).
    4. Establish communication between the HMI and the PLC, and perform simulation tests to verify proper system operation.