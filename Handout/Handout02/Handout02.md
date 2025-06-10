# UFSM00741 - Handout 02

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📑 Table of Contents

- [🏭 Fundamental Principles of Industrial Cybersecurity](#-fundamental-principles-of-industrial-cybersecurity).
- [🏭 Case Studies of Cyber Incidents in OT-ICS](#-case-studies-of-cyber-incidents-in-ot-ics).

## 🏭 Fundamental Principles of Industrial Cybersecurity

- Industrial control systems (ICS) are susceptible to threats posed by adversarial entities, commonly referred to as **threat actors**. According to the Guide to Operational Technology (OT) Security ([NIST SP 800-82 Rev. 3][nist-sp-800-82r3]) issued by the [National Institute of Standards and Technology (NIST)][nist], the primary categories of threat sources include:
  - 🏴‍☠️ **Adversarial**.
    - Hacktivists — 🔗 [2023 Cyber Av3ngers Targeting Israel-Made OT Devices][adversarial01].
    - Insiders — 🔗 [The 2000 Maroochy Shire Cyber Incident][adversarial02].
    - Nation-state actors — 🤔🔗 [Cyberattack on Irish Utility Cuts Off Water Supply for Two Days][adversarial03].
    - Botnets — 🔗 [Botnet Clusters Exploiting OT Default Credentials and Wiping Data Directories][adversarial04].
  - 🤦 **Accidental**.
    - General users.
    - Privileged users or administrators.
    - 🔗 [Dispatcher Error Triggered 30-Minute Power Outage in Palo Alto][accidental].
  - 🔧 **Structural**.
    - Hardware failure.
    - Software failure.
    - Failure of environmental controls (e.g., temperature or humidity regulation).
    - Communication degradation (e.g., disruptions in wired or wireless networks).
    - 🔗 [2024 CrowdStrike-Related Information Technology (IT) Outages][crowdstrike].
  - 🌪️ **Environmental**.
    - Natural or human-caused disaster.
    - Failures in critical infrastructure (e.g., telecommunications, electric power, transportation, or water/wastewater systems).
    - 🔗 [Nova Santa Rita Substation Preventively Shut Down][novasantarita].
- These threat actors leverage various **attack vectors** to execute malicious activities targeting ICS environments.
  - **Compromised and weak credentials** refer to usernames and passwords that have been exposed—whether through data breaches or insecure handling. This remains one of the most common attack vectors leveraged by cybercriminals. Lost or stolen credentials allow malicious actors to access corporate systems as if they were legitimate users, enabling lateral movement and privilege escalation within the victim's network.
    - 🔗 https://haveibeenpwned.com
    - To mitigate this threat, organizations should:
      1. Promote the use of strong passwords.
      2. Encourage the adoption of password managers.
      3. Foster a cybersecurity-conscious culture through regular training and simulated phishing exercises.
    - Additionally, implementing **multi-factor authentication (MFA)** is essential to verify user identities and reduce unauthorized access.
    - 👉 Refer to [Issue 04, 2024][indcybersecletters-2024issue04] of the [Ind.Cyber.Sec Letters][indcybersecletters], titled Weak Passwords and Poor Security Practices Persist After Six Years of NordPass Research.
    - 🚨 A typical example of a cyberattack in this category is **password spraying**, in which an adversary attempts to access multiple accounts within the same organization using a dictionary of commonly used passwords. The goal is to gain unauthorized access through a **trial-and-error** approach.
  - **Missing or weak encryption** can enable the transmission of sensitive data in plaintext, leaving it vulnerable to interception. Encryption protects digital information by converting it into a secure format—known as ciphertext—which ensures that the data cannot be read by unauthorized actors.
    - 🚨 **Modbus/TCP**, a widely adopted protocol in OT-ICS systems, transmits data without encryption or authentication mechanisms. This allows any actor with access to the network to intercept, manipulate, or inject commands in plaintext.
    - The newer **Modbus/TCP Security** introduces transport layer security (TLS) to address long-standing vulnerabilities by enabling encryption, authentication, and data integrity.
  - **Unpatched applications or services** pose a significant risk to organizations, as cybercriminals continuously scan for open ports and exploitable vulnerabilities in software or network services. Moreover, there is sustained effort by threat actors to discover and exploit **zero-day vulnerabilities**. Given this context, both organizations and users must ensure that their software, operating systems, and applications are properly **patched**, including regular updates and the application of security fixes.
    - 🚨 In OT environments, patching is particularly challenging due to strict uptime requirements, limited maintenance windows, and the potential for compatibility issues with legacy systems—**factors that often delay or prevent timely security updates**.
  - **Distributed denial-of-service (DDoS)** is a malicious technique used to flood a network or service with illegitimate requests in order to disrupt normal operations. Victim servers can become overloaded by a high volume of requests originating from multiple compromised devices controlled by cybercriminals—a formation commonly referred to as a **botnet**.
    - 🚨 In OT-ICS environments, there is a growing risk that firewalls, industrial Internet of things (IIoT) devices, or other perimeter components may be compromised and **co-opted into botnets**, turning the organization into an unintentional participant in a DDoS campaign.
  - 🦠 **Malware** refers to malicious software or code intentionally developed to harm IT assets and, increasingly, OT-ICS environments. The term encompasses a wide range of threats, including **viruses**, **worms**, **ransomware**, **keyloggers**, **trojans**, **spyware**, and other variants designed to compromise confidentiality, integrity, or availability (CIA) of systems and data.
    - Malware specifically designed for OT-ICS environments—such as [Stuxnet][stuxnet], [Industroyer][industroyer], and [TRITON][triton]—demonstrates the growing sophistication of threats targeting industrial systems, often aiming to disrupt physical processes, damage critical infrastructure, or compromise operator safety.
    - 👉 Refer to [Issue 03, 2024][indcybersecletters-2024issue03] of the [Ind.Cyber.Sec Letters][indcybersecletters], titled Financial Impacts of Ransomware Can Reach Up to US$1 Million in Critical Infrastructure.
  - 🎣 **Phishing** is a widely used technique by cybercriminals to distribute malware, conduct financial fraud, and gain unauthorized access to systems. It involves a form of **social engineering**, typically executed through fraudulent emails, text messages, phone calls, or spoofed web pages. The primary objective is to deceive individuals by impersonating trusted entities. At its core, phishing attacks are often successful due to human error and behavioral vulnerabilities.
    - 🚨 In the [2015 Ukraine power grid cyberattack][ukraine], threat actors used a targeted phishing campaign to deliver the [BlackEnergy][blackenergy] malware to employees of regional electric distribution companies. Once initial access was gained through malicious email attachments, the attackers moved laterally within the IT environment, eventually reaching and manipulating supervisory control and data acquisition (SCADA) systems, leading to widespread power outages that affected more than 230,000 residents.
- During a cyber incident, OT assets may:
  - 💣 Be corrupted in a way that causes the system to execute preprogrammed actions incorrectly, produce erroneous outputs, or result in data loss.
  - 💣 Be subjected to cyber espionage.
  - 💣 Become unavailable or operate with significantly degraded performance, potentially rendering real-time control systems impractical (an especially critical concern for time-sensitive operations).
  - 💥 Sustain physical damage as a consequence of the cyberattack ([physical consequences in OT environments][waterfall]).

## 🏭 Case Studies of Cyber Incidents in OT-ICS

- 📰 [Issue 01, 2024][indcybersecletters-2024issue01] of the [Ind.Cyber.Sec Letters][indcybersecletters], titled Threat Actors Continue to Exploit OT/ICS through Unsophisticated Means.
- 📰 [Issue 02, 2024][indcybersecletters-2024issue02] of the [Ind.Cyber.Sec Letters][indcybersecletters], titled OpenAI Identifies Threat Actors Using Its AI Models Against Operational Technologies.
- 📰 [Issue 02, 2025][indcybersecletters-2025issue02] of the [Ind.Cyber.Sec Letters][indcybersecletters], titled Insights from Waterfall-ICS STRIVE Threat Reports and the Cyber Sabotage at Iranian Steel Plants in 2022.

## 🔖 Nomenclature

- CIA: Confidentiality, integrity, or availability.
- DDoS: Distributed denial of service.
- ICS: Industrial control system.
- IIoT: Industrial Internet of things.
- IT: Information technology.
- MFA: Multi-factor authentication.
- OT: Operational technology.
- SCADA: Supervisory control and data acquisition.
- TLS: Transport layer security.

<!-- Links -->
[accidental]: https://web.archive.org/web/20231130002837/https://www.paloaltoonline.com/news/2022/09/08/dispatcher-error-triggered-tuesday-power-out-in-palo-alto
[adversarial01]: https://web.archive.org/web/20250410003335/https://www.dragos.com/blog/cyber-av3ngers-hacktivist-group-targeting-israel-made-ot-devices
[adversarial02]: https://web.archive.org/web/20250519081156/https://www.mitre.org/sites/default/files/pdf/08_1145.pdf
[adversarial03]: https://web.archive.org/web/20250419215816/https://www.securityweek.com/cyberattack-on-irish-utility-cuts-off-water-supply-for-two-days
[adversarial04]: https://www.forescout.com/blog/targeting-ot-security-ics-threats-malware
[blackenergy]: https://attack.mitre.org/software/S0089
[crowdstrike]: https://www.forbes.com/sites/kateoflahertyuk/2024/08/07/crowdstrike-reveals-what-happened-why-and-whats-changed
[indcybersecletters]: https://github.com/substationworm/IndCyberSecLetters
[indcybersecletters-2024issue01]: https://github.com/substationworm/IndCyberSecLetters/blob/main/2024/Issue01/Issue01.md
[indcybersecletters-2024issue02]: https://github.com/substationworm/IndCyberSecLetters/blob/main/2024/Issue02/Issue02.md
[indcybersecletters-2024issue03]: https://github.com/substationworm/IndCyberSecLetters/blob/main/2024/Issue03/Issue03.md
[indcybersecletters-2024issue04]: https://github.com/substationworm/IndCyberSecLetters/blob/main/2024/Issue04/Issue04.md
[indcybersecletters-2025issue02]: https://github.com/substationworm/IndCyberSecLetters/blob/main/2025/Issue02/Issue02.md
[industroyer]: https://web.archive.org/web/20250515185237/https://www.welivesecurity.com/2017/06/12/industroyer-biggest-threat-industrial-control-systems-since-stuxnet
[novasantarita]: https://web.archive.org/web/20240830191057/https://www.jornaldocomercio.com/economia/2024/05/1152798-subestacao-nova-santa-rita-e-desligada-preventivamente.html
[nist]: https://www.nist.gov
[nist-sp-800-82r3]: https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r3.pdf
[stuxnet]: https://web.archive.org/web/20250607133612/https://www.wired.com/2014/11/countdown-to-zero-day-stuxnet
[triton]: https://web.archive.org/web/20250406165117/https://www.technologyreview.com/2019/03/05/103328/cybersecurity-critical-infrastructure-triton-malware
[ukraine]: https://web.archive.org/web/20250501212315/https://www.wired.com/2016/03/inside-cunning-unprecedented-hack-ukraines-power-grid
[waterfall]: https://waterfall-security.com/ot-insights-center/ot-cybersecurity-insights-center/2025-threat-report-ot-cyberattacks-with-physical-consequences