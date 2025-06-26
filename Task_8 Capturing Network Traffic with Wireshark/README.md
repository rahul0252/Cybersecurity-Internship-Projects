
# 🛡️ Network Traffic Analysis with Wireshark

## 🎯 Objective

The goal of this project is to **capture and analyze network traffic** using **Wireshark**, a powerful packet analyzer. This is a fundamental skill in cybersecurity, network troubleshooting, and digital forensics.

---

## 🧰 Tools Used

- **Wireshark**: Open-source network protocol analyzer used to inspect packets in real-time or from saved capture files.

---

## 📝 Steps Performed

### 1. 🔧 Installation of Wireshark
Wireshark was installed on the local machine. You can install it using the following:
- On **Windows/macOS**: [Download from official website](https://www.wireshark.org/download.html)
- On **Linux**:
  ```bash
  sudo apt update
  sudo apt install wireshark
  ```

### 2. 📡 Capturing Network Traffic
- Wireshark was launched with administrator/root privileges.
- A network interface was selected (typically `eth0`, `wlan0`, or similar).
- Live packet capture was started during common browsing activities.

### 3. 🔍 Filtering HTTP Traffic
- A display filter was applied to focus on **HTTP packets**:
  ```bash
  http
  ```
- Inspected GET and POST requests, hostnames, user agents, and other headers.

### 4. 📁 Saving the Capture
- The network capture was saved as a `.pcap` file for further analysis and submission.

---

## 📂 Project Files

- `wireshark_capture.pcap`: Packet capture file containing HTTP traffic data.
- `README.md`: Documentation explaining the capture and analysis process.

---

## 📊 Observations

- Detected several **HTTP GET requests** to external domains.
- Examined response status codes (e.g., `200 OK`, `301 Moved Permanently`).
- Identified metadata such as `User-Agent`, `Host`, and `Referer`.
- Observed potential plaintext data, emphasizing the lack of encryption in HTTP.

---

## 🚨 Security Insight

This analysis highlights how **unsecured HTTP traffic** can expose sensitive data (like login information or browsing activity). It's a reminder of the importance of **HTTPS** and **network encryption**.

---

## 📌 Disclaimer

All traffic was captured on a **private and permitted network** for educational purposes only. No unauthorized access or packet sniffing was conducted.

---

## ✅ Conclusion

Wireshark is a crucial tool for network professionals and cybersecurity analysts. This project demonstrated how to effectively capture and analyze real-world HTTP traffic to gain valuable insights.
