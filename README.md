# Network Walks Internship – Week 2

**Intern Name:** Avinash Chilamathuru  
**Internship:** Network Walks  
**Week:** 2  
**Selected Elective:** PM1 – Footprinting  
**Essential Modules:** PM5 – Zenmap Network Scanning and PM-FINAL – Detailed Report

---

## 1. Introduction

During Week 2 of the Network Walks internship, I worked on basic footprinting techniques and network discovery using Kali Linux.

The main objective was to understand how information about a domain can be collected using different command-line tools and how live devices can be identified in a controlled network environment.

I completed the PM1 footprinting practical and performed a ping scan using Zenmap for PM5.

## 2. Environment and Tools Used

**Operating System:** Kali Linux  
**Virtualization:** Oracle VirtualBox

**Tools used:**
- WHOIS
- WhatWeb
- NSLookup
- cURL
- WAFW00F
- DNSRecon
- Nmap
- Zenmap

---

# 3. PM1 – Footprinting

## Objective

The objective of this practical was to understand the basic information-gathering process using different footprinting tools available in Kali Linux.

The domain used for the assigned practical was `networkwalks.com`.

## Tools and Practical Work

### 3.1 WHOIS

WHOIS was used to collect domain registration information, including registrar details, creation date, expiry date and name servers.

**Observation:** The domain was registered through GoDaddy.com, LLC. The creation date shown was 6 November 2019, and the expiry date was 6 November 2027.

**Screenshot:** <img width="1917" height="597" alt="whois" src="https://github.com/user-attachments/assets/4d54d28c-2412-459f-b2b2-5c5ce8708249" />
<img width="1917" height="1078" alt="whois1" src="https://github.com/user-attachments/assets/48169f3a-5157-469e-b0a4-e6631108bef9" />
<img width="1917" height="1070" alt="whois2" src="https://github.com/user-attachments/assets/0678626e-bfdc-4a9f-b371-0edf6abdbcfe" />

### 3.2 WhatWeb

WhatWeb was used to identify technologies and information visible on the website.

**Observation:** The scan identified Apache, WordPress 7.1.4, jQuery 3.7.1 and the website title Networkwalks Academy.

**Screenshot:** <img width="1917" height="1078" alt="whatweb" src="https://github.com/user-attachments/assets/602bc6af-c60e-4b47-8a63-1214f45dfbe0" />

### 3.3 NSLookup

NSLookup was used to check the DNS resolution of the domain.

**Observation:** The domain resolved to `192.232.216.135` using the configured DNS resolver `8.8.8.8`.

**Screenshot:** <img width="1177" height="537" alt="nslookup" src="https://github.com/user-attachments/assets/c2c43b02-306d-4d87-bb33-8033add6c55a" />

### 3.4 cURL

The cURL command was used to retrieve the HTTP response headers.

**Observation:** The website returned an HTTP/2 200 response. The headers also showed information about the web server, content type, caching and security-related policies.

**Screenshot:** <img width="1917" height="1078" alt="curl" src="https://github.com/user-attachments/assets/a9dddd1f-dedb-4857-af91-a8b90b8c8c12" />

### 3.5 WAFW00F

WAFW00F was used to identify whether a web application firewall could be detected.

**Observation:** The tool detected ModSecurity (SpiderLabs).

**Screenshot:** <img width="1415" height="802" alt="wafw00f" src="https://github.com/user-attachments/assets/e5e49d67-991d-4399-b3d1-d1414782dcc7" />

### 3.6 DNSRecon

DNSRecon was used to collect DNS records associated with the domain.

**Observation:** The output included SOA, NS, MX, A, TXT and SRV records. The DNS enumeration completed with eight records reported by the tool.

**Screenshot:** <img width="1917" height="971" alt="dnsrecon" src="https://github.com/user-attachments/assets/52e486b5-1ce1-4581-9bdc-442b8a075022" />

## PM1 – Learning Outcome

By completing this practical, I learned how different tools can collect different types of publicly available domain and website information. I also understood the importance of checking DNS records, HTTP headers, website technologies and firewall detection.

---

# 4. PM5 – Zenmap Network Scanning

## Objective

The objective of this practical was to identify live hosts in a controlled network using Zenmap and understand the basic network discovery process.

## Network Environment

- Network range: `10.0.0.0/24`
- Kali Linux IP: `10.0.0.2`
- Gateway: `10.0.0.1`
- Scan profile: Ping Scan
- Command: `nmap -sn 10.0.0.0/24`

## Practical Work

I opened Zenmap in Kali Linux and selected the Ping Scan profile. I used the CyberLab virtual network range for host discovery.

The scan checked 256 IP addresses and identified two live hosts.

## Results

| Finding | Result |
|---|---|
| Network range | 10.0.0.0/24 |
| Total addresses scanned | 256 |
| Live hosts found | 2 |
| First host | 10.0.0.1 |
| Second host | 10.0.0.2 |
| First host MAC | 52:54:00:12:35:00 |
| First host vendor | QEMU virtual NIC |
| Scan duration | Approximately 3 seconds |

The first live host was identified as a QEMU virtual NIC. The second live host was my Kali Linux virtual machine.

The scan used the `-sn` option, which performs host discovery without performing a port scan.

## Screenshots

**01 – Zenmap Configuration**

<img width="1682" height="587" alt="zenmap" src="https://github.com/user-attachments/assets/5b98ce69-83ec-4028-8a9a-803e05d9f4d7" />

**02 – Ping Scan Results**

<img width="1917" height="822" alt="ping scan" src="https://github.com/user-attachments/assets/f1506be2-ea21-4a79-8923-8cd8668bdf3c" />

**03 – Network Topology**

<img width="1916" height="1037" alt="topology" src="https://github.com/user-attachments/assets/1ce638b5-d875-4be8-a0b2-8d4d8a4a644c" />

The topology PDF and text output are included in the PM5 Outputs folder.

## PM5 – Learning Outcome

Through this practical, I understood how to configure a ping scan in Zenmap, identify live hosts and view the discovered network topology. I also learned the difference between host discovery and port scanning.

---

# 5. Challenges and Troubleshooting

During the practical work, I faced a few minor issues:

1. The `pdfinfo` command was not initially available in Kali Linux. I installed the `poppler-utils` package to inspect the exported topology PDF.
2. The initial DNSRecon output file was empty because the command output was being sent to the error stream. I corrected this by using `2>&1` with `tee`.
3. I organized the practical outputs into separate folders so that the results could be referred to easily while preparing the report.

These issues helped me understand basic Linux package installation, command output redirection and file organization.

---

# 6. Ethical Considerations

All practical activities were carried out within the scope of the assigned internship exercises and the authorized lab environment.

The PM5 network discovery was restricted to my CyberLab virtual network. No exploitation or unauthorized access attempts were performed.

---

# 7. Conclusion

In Week 2, I gained practical experience with six footprinting tools and learned how to perform basic network discovery using Zenmap.

I understood how to collect domain information, identify website technologies, examine DNS records, inspect HTTP headers and detect a web application firewall. I also learned how to identify live hosts in a virtual network and export network topology information.

Overall, these practical exercises helped me improve my familiarity with Kali Linux and understand the initial stages of information gathering and network reconnaissance.

---

**End of Week 2 Practical Work**
