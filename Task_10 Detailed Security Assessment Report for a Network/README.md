# 📡 Network Traffic Capture with Wireshark

## 🎯 Objective

The goal of this project is to demonstrate how to capture and analyze network traffic using Wireshark. The focus is on capturing HTTP traffic, identifying patterns, and interpreting packet-level details.

---

## 🛠️ Tools and Technologies Used

- **Wireshark** – Network protocol analyzer
- **Local web browser** – To generate HTTP traffic
- **Operating System** – Windows, Linux, or macOS

---

## ⚙️ Setup Instructions

### 1. Install Wireshark

- Download and install from [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)

### 2. Configure Capture

- Open Wireshark
- Select the network interface (e.g., `eth0`, `wlan0`, or `en0`) you want to monitor
- Click **Start Capturing Packets**

### 3. Generate HTTP Traffic

- Open a web browser
- Visit a few non-HTTPS websites (e.g., `http://example.com`) to generate HTTP traffic

### 4. Filter HTTP Traffic

Use the filter bar in Wireshark and type: HTTP

This will isolate all HTTP packets in the capture.

### 5. Save the Capture

- Stop the capture after a few minutes
- Go to **File → Save As** and save the file as `wireshark_capture.pcap`

---

## 🔍 Packet Analysis Example

Here are some of the things to look for in your capture:

- **GET / POST Requests**:
  View HTTP request lines to see what resources were requested.

- **Host Header**:
  Look for the `Host:` header to identify the destination server.

- **User-Agent**:
  This string identifies the browser making the request.

- **Response Status Codes**:
  Look at the response to check if it’s `200 OK`, `404 Not Found`, etc.

- **Source and Destination IPs**:
  Identify client and server IP addresses for each request.

---

## 📁 GitHub Deliverables

| File                    | Description                                      |
|-------------------------|--------------------------------------------------|
| `wireshark_capture.pcap`| Packet capture file                             |
| `README.md`             | This documentation file                         |

---

## 🎥 Demo Video Idea

**Title**: "How to Capture Network Traffic with Wireshark"

**Outline**:
1. Introduction to Wireshark
2. Installing Wireshark on your system
3. Selecting the correct network interface
4. Starting and stopping capture
5. Filtering HTTP traffic
6. Analyzing packets (GET, Host, User-Agent)
7. Saving the capture as `.pcap` file

---

## 📚 References

- [Wireshark Official Documentation](https://www.wireshark.org/docs/)
- [HTTP Protocol Overview - MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- [Packet Analysis with Wireshark](https://www.geeksforgeeks.org/wireshark-packet-analysis/)

---

## 🛑 Disclaimer

> This capture was done on a private network with full permission. Do not capture or inspect network traffic without authorization as it may be illegal and unethical.

---

## 👨‍💻 Author

- **Name**: Rahul Prasad  


