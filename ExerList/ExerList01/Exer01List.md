# UFSM00741 - Exercise List 01

![](UFSM-CT-DESP-UFSM00741.png "UFSM-CT-DESP-UFSM00741")

[![Curriculum Lattes](https://img.shields.io/badge/Lattes-white)](http://lattes.cnpq.br/8846358506427099)
[![ORCID](https://img.shields.io/badge/ORCID-grey)](https://orcid.org/0000-0002-6254-7306)
[![SciProfiles](https://img.shields.io/badge/SciProfiles-black)](https://sciprofiles.com/profile/lffreitas-gutierres)
[![Scopus](https://img.shields.io/badge/Scopus-white)](https://www.scopus.com/authid/detail.uri?authorId=57195542368)
[![Web of Science](https://img.shields.io/badge/ResearcherID-grey)](https://www.webofscience.com/wos/author/record/Q-8444-2016)
[![substationworm](https://img.shields.io/badge/substationworm-black)](https://github.com/substationworm)
[![LFFreitasGutierres](https://img.shields.io/badge/LFFreitasGutierres-white)](https://github.com/LFFreitas-Gutierres)

## 📝 Exercise 01 - HTTP `GET` in Wireshark

- 🛠 **Procedures:**
    1. 🌐 Launch a web browser (e.g., Firefox).
    2. 🌐 Navigate to [http://httpforever.com](http://httpforever.com).
    3. 🦈 Start packet capture in Wireshark using the `http` filter.
    4. 🌐 Reload the website [http://httpforever.com](http://httpforever.com).
    5. 🦈 Wait for one minute.
    6. ⌨️ In a terminal, execute the following command: `curl -i http://httpforever.com`.
    7. 🦈 Wait for another minute and then stop the packet capture in Wireshark.
    8. 💾 Two types of messages should have been captured:
        - Two `GET` messages (from the browser to the [http://httpforever.com](http://httpforever.com) server).
        - Two response messages from the server to the browser and the `curl` command:
            - `HTTP/1.1 304 Not Modified`.
            - `HTTP/1.1 200 OK (text/html)`.
- ❓ **Questions:**
    1. Which version of HTTP (1.0 or 1.1) is used by the web browser?
    2. Which version of HTTP (1.0 or 1.1) is used by the server?
    3. What languages does the browser prefer to receive in the response?
    4. What is the IP address of the computer?
    5. What is the IP address of the server?
    6. What status code was returned by the server to the web browser?
    7. What status code was returned by the server to the `curl` command?
    8. What is the difference between these status codes?
    9. When was the HTML file obtained during the capture last modified?
    10. How many content bytes were returned via the `curl` command?
    11. What are the two user agents involved in this activity?
- 📋 **Supplementary Discussion Topic:**
    - 👉 Check whether the HTTP `If-Modified-Since` header appears in any `GET` request. When was it used? What did it verify? And how did the server respond?

## 📝 Exercise 02 - `nslookup`, `whois`, and Other Useful Commands
- ❓ **Questions:**
    1. List the following information about your machine:
        - Hostname.
        - IP address (mesmo que seja privado).
        - DNS.
        - MAC address.
    2. Provide an IPv4 address for [google.com](google.com).
    3. Provide an IPv6 address for [google.com](google.com).
    4. What is the name and IP address of the local DNS server provided by your Internet service provider (ISP)?
    5. Identify the domain name registrar of [ufsm.br](ufsm.br).
    6. Create a hypothetical domain name and determine its annual cost.

## 📝 Exercise 03 - ICMP in Wireshark

- 🛠 **Procedures:**
    1. 🦈 In Wireshark, open the file `Exer03.pcapng`.
    2. 🔍 Observe that ICMP packets do not contain source and destination port numbers, as the protocol is designed to communicate network-layer information between hosts and routers.
    3. 🔍 Analyze the captured traffic and respond to the questions below.
- ❓ **Questions:**
    1. The Internet control message protocol (ICMP) operates at which layer of the OSI model?
    2. What are the type and code values of the ICMP packet recorded in frame 345?
    3. What are the type and code values of the ICMP packet recorded in frame 346?
    4. What is the size (in bits) of the checksum field in an ICMP message? What is its purpose?
    5. Compare the identifier and sequence number fields between ICMP requests and their corresponding replies. Did any changes occur throughout the packet capture?
    6. What are the IP addresses of the host computer and the destinations targeted by the `ping` command?

## 📝 Exercise 04 - TCP no Wireshark

- 🛠 **Procedures:**
    1. 🌐 Launch a web browser (e.g., Firefox).
    2. 🌐 Access the website [http://www.textfiles.com/computers/anetwork.txt](http://www.textfiles.com/computers/anetwork.txt) and download the TXT file.
    3. 🦈 Start packet capture in Wireshark using the filter `tcp.port == 80`.
    4. 🌐 Perform an HTTP `POST` request to [http://httpbin.org/post](http://httpbin.org/post), uploading the TXT file using the following `curl` command: `curl -v -F "file=@anetwork.txt" http://httpbin.org/post`.
    5. 🦈 Wait for one minute, then stop the packet capture in Wireshark.
    8. 💾 A series of TCP and HTTP messages between your computer and [http://httpbin.org/post](http://httpbin.org/post) should have been captured. Notably, you should observe an HTTP `POST` request.
- ❓ **Questions:**
    1. What is the IP address and TCP source port number used by the client to transfer the file?
    2. What is the IP address and TCP destination port number used by the server to receive the file?
    3. What is the TCP sequence number of the `SYN` segment que inicia a conexão entre o cliente e o servidor? segment that initiates the connection between the client and the server? What identifies the segment as a `SYN` segment?
    4. What is the sequence number of the `SYN, ACK` segment sent by the server in response to the client's `SYN`? What is the value of the `ACK` field in this segment? What identifies this segment as a `SYN, ACK`?
    5. What is the sequence number of the `ACK` segment sent by the client in response to the `SYN, ACK`? What are the values of the `SYN` and `ACK` flags in this segment? What identifies the segment as an `ACK`?
    6. Are there any segments marked as `PSH, ACK`? What is their significance?
    7. How do the client and server terminate the connection? What types of segments are used?