
# Network Security Assessment Report

**Prepared By:** [Your Name]  
**Date:** [Insert Date]  
**Tools Used:** Nmap, Wireshark  

---

## 1. Introduction

This document presents the results of a comprehensive network security assessment performed on a local test network. The primary objective was to identify any vulnerabilities, misconfigurations, or suspicious network activities that could expose the network to security threats.

---

## 2. Scope of Assessment

- **Target Network:** Local Test Network (192.168.1.0/24)
- **Tools Used:**
  - **Nmap:** For active network scanning and service enumeration.
  - **Wireshark:** For network traffic capture and analysis.

---

## 3. Nmap Scan Results

**Scan Command Used:**

```bash
nmap -sS -sV -O 192.168.1.0/24
```

**Objective of Scan:**

- Identify live hosts on the network.
- Detect open ports and running services.
- Determine operating system information.

**Summary of Findings:**

| IP Address     | Open Ports               | Services                   | OS Detected        |
|----------------|--------------------------|----------------------------|--------------------|
| 192.168.1.1    | 80/tcp (HTTP), 23/tcp (Telnet) | Apache HTTPD, Telnet Server | Linux (Router)     |
| 192.168.1.5    | 22/tcp (SSH), 80/tcp (HTTP) | OpenSSH, Apache HTTPD       | Ubuntu Linux       |
| 192.168.1.10   | 445/tcp (SMB), 139/tcp (NetBIOS) | Windows SMB Service        | Windows 10         |

**Vulnerabilities Identified from Nmap Results:**

- **Telnet Service Detected (192.168.1.1):**  
  Telnet transmits data in plaintext, making it vulnerable to sniffing and credential theft.

- **SMB Service (192.168.1.10):**  
  Older SMB versions are known for vulnerabilities like EternalBlue. Needs patch verification.

- **Unnecessary Open Ports:**  
  Some systems were running services that are not essential and could be attack surfaces.

*Full Nmap output file:* See `nmap_results.txt` for detailed scan output.

---

## 4. Wireshark Traffic Capture Analysis

**Capture Duration:** 15 minutes  
**Traffic Captured File:** `wireshark_capture.pcap`

**Key Observations:**

| Observation | Details |
|------------ | ------- |
| Unencrypted Protocols | Detected HTTP, Telnet traffic transmitting sensitive data in plaintext. |
| ARP Spoofing Signs | Multiple ARP requests/replies with mismatched MAC addresses. Possible ARP spoofing attack in progress. |
| DNS Queries | Some DNS queries resolved to external suspicious IPs, suggesting possible malware communication. |
| High Broadcast Traffic | Noticed excessive broadcast/multicast packets, potentially indicating misconfigured devices or network scanning tools in use. |

**Potential Risks Identified:**

1. **Plaintext Credential Leakage:**  
   Observed usernames/passwords in Telnet and HTTP sessions.

2. **Man-in-the-Middle (MITM) Risks:**  
   Presence of ARP spoofing patterns can lead to MITM attacks.

3. **Malicious External Communication:**  
   Suspicious DNS resolution patterns should be investigated further.

---

## 5. Security Recommendations

| Issue                          | Recommendation |
|--------------------------------|----------------|
| Use of Telnet                  | Replace with SSH for encrypted remote access. |
| SMB Vulnerabilities             | Patch Windows hosts with latest updates; disable SMBv1 if still enabled. |
| Unnecessary Open Ports          | Disable unused services and restrict access using firewall rules. |
| Plaintext Protocols (HTTP)      | Use HTTPS instead of HTTP to secure web traffic. |
| ARP Spoofing Detection          | Implement dynamic ARP inspection (DAI) on switches or use ARP monitoring tools. |
| Suspicious External Traffic     | Review internal DNS logs and block known malicious IPs/domains at the firewall level. |
| Network Segmentation            | Isolate sensitive devices/services into separate VLANs to limit attack spread. |

---

## 6. Conclusion

The assessment revealed several potential security weaknesses within the test network, including the use of insecure services (Telnet, HTTP), legacy protocols (SMBv1), and signs of possible ARP spoofing or malware-related activity.

**Immediate Action Items:**

- Disable and replace insecure protocols.
- Patch all vulnerable hosts.
- Monitor traffic continuously for suspicious activity.
- Conduct periodic vulnerability scans and traffic analysis.

By addressing the identified issues and implementing the above recommendations, the overall network security posture can be significantly improved.

---

## 7. Attachments in Repository:

- `nmap_results.txt` – Full Nmap scan results.
- `wireshark_capture.pcap` – Full Wireshark capture file.

---

**End of Report**
