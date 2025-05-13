# UFSM00741 - Homework 02

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Task 01 - Capturing HTTPS Traffic and Analyzing TLS Sessions

- 📋 **Procedures:**
    1. 🌐 Clear the stored data from [Chromium](https://www.chromium.org/Home/) or [Firefox](https://www.mozilla.org/firefox/) related to the website http://ufsm.br.
    2. ⌨️ Use the `nslookup` command to find the IPv6 address of http://ufsm.br.
    3. 🦈 Start packet capture in [Wireshark](https://www.wireshark.org/) using the following filter: `ipv6.addr == <UFSM IPv6 address>`.
    4. 🌐 Access the website http://ufsm.br.
    5. 💾 Stop and save the capture after a few minutes.
- ❓ **Discussion Questions:**
    1. What is the IPv6 address of the server?
    2. What is the IPv6 address of the client?
    3. Identify the frames that initiate the three-way handshake with the server over `Port 80`.
    4. Is there any `301 Moved Permanently`redirection? What is its purpose?
    5. Identify the frames that initiate the three-way handshake with the server over `Port 443`.
    6. Analyze the frames containing TLS. What do the TLS `Application Data` frames contain?

## 📝 Task 02 - Capturing HTTPS Traffic and Analyzing Decrypted TLS Sessions

- 📋 **Procedures:**
    1. 🌐 Clear the stored data from [Chromium](https://www.chromium.org/Home/) or [Firefox](https://www.mozilla.org/firefox/) related to the website http://ufsm.br.
    2. ⌨️ Use the `nslookup` command to find the IPv6 address of http://ufsm.br.
    3. ⌨️ Run the following command in a terminal: `chromium --ssl-key-log-file=~/ssl-key.log`. If you are using [Firefox](https://www.mozilla.org/firefox/), execute:
        ```
        export SSLKEYLOGFILE=~/ssl-key.log
        firefox
        ```
    4. 🦈 Start packet capture in [Wireshark](https://www.wireshark.org/) using the following filter: `ipv6.addr == <UFSM IPv6 address>`.
    5. 🌐 Access the website http://ufsm.br.
    6. 💾 Stop and save the capture after a few minutes.
    7. 🦈 Navigate to `Protocol Preferences` 👉 `Transport Layer Security` 👉 `Open Transport Layer Security preferences...`
    8. 🦈 Configure the `ssl-key.log` file in the `(Pre)-Master-Secret log filename` field.
    9. 🔓 Analyze the decrypted data traffic.
- ❓ **Discussion Questions:**
    1. What is the IPv6 address of the server?
    2. What is the IPv6 address of the client?
    3. Identify the frames that initiate the three-way handshake with the server over `Port 80`.
    4. Identify the frames that initiate the three-way handshake with the server over `Port 443`.
    5. Evaluate the frames containing TLS and compare them with the previous task.
    6. Is it more evident this time what the TLS `Application Data` frames contain? Provide examples.

## 📝 Task 03 - Website Scanning Using `nmap`

*Note: Scanning websites or networks without proper authorization is illegal and unethical.*

- 📋 **Procedures:**
    1. ⌨️ Run the following command:
    ```
    `sudo nmap -sS -sV -p- -T4 --script http-headers,http-title scanme.nmap.org`
    ```
- ❓ **Discussion Questions:**
    1. What type of scan was performed? What are the specific steps involved in this scan?
    2. Which ports are open?
    3. What is the title of the main web page (`http-title`)?
    4. List all HTTP headers returned by the server.
    5. What is the version of the identified web server (`-sV`)?
    6. What does the `-T4` timing template enable?

## 📝 Task 04 - Automatic Liquid Mixing Control

- 👷 **Control Logic Description:**
    - The automatic mixing of liquids (A-B) takes place inside a reservoir equipped with:
        1. Lower and upper level sensors.
        2. An industrial agitator.
        3. Valves for the inlet of liquids A and B.
        4. A valve for the outlet of the resulting mixture.
    - The operator has access to three control buttons: `START`, `STOP` and emergency stop (`EMER_STOP`).
    - Liquid A should be injected (`VALVE_A`) into the reservoir upon pressing `START`, and the injection should continue (latched) until the lower level sensor (`SNS_LOW`) is activated.
    - After the lower level sensor (`SNS_LOW`) is triggered, Liquid B should be injected (`VALVE_B`), remaining latched until the upper level sensor is activated (`SNS_HIGH`).
    - The industrial agitator (`AGITATOR`) should activate only after the reservoir is completely filled and should run for 60 seconds (`TMR01`).
    - The discharge of the mixture (`VALVE_OUT`) should be latched, maintained for a timed duration of 120 seconds (`TMR02`).
- 🏷️ **Minimum Requirements:**
    - Start push-button (1x): `START = %I0.0`.
    - Stop push-button (1x): `STOP = %I0.1`.
    - Emergency stop (1x): `EMER_STOP = %I0.2`.
    - Lower level sensor (1x): `SNS_LOW = %I0.3`.
    - Upper level sensor (1x): `SNS_HIGH = %I0.4`.
    - Inlet of liquid A (1x): `VALVE_A = %Q0.0`.
    - Inlet of liquid B (1x): `VALVE_B = %Q0.1`.
    - Outlet of mixture (1x): `VALVE_OUT = %Q0.2`.
    - Control of agitator (1x): `AGITATOR = %Q0.3`.
    - Timers (2x):
        - `TMR01`, mixing duration (60 seconds).
        - `TMR02`, drainage of the mixture (120 seconds).