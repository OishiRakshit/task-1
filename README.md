🔍 Scan Your Local Network for Open Ports
## 📌 Objective

 Learn to discover open ports on devices in your local network to
 understand network exposure.
---

## 🛠️ Tools Used

- [Nmap](https://nmap.org/) – Free and powerful network scanning tool  
- [Wireshark](https://www.wireshark.org/) *(optional)* – Network protocol analyzer

---

## 📡 Task Steps

### 1. Install Nmap
Download and install Nmap from the [official website](https://nmap.org/download.html).

### 2. Find Local IP Range
Use the following command to identify your IP and subnet:
- Windows: `ipconfig`
- Linux/macOS: `ifconfig` or `ip a`

For example, if your IP is `192.168.1.5`, the typical scan range is `192.168.1.0/24`.

### 3. Run a SYN Scan
```bash
nmap -sS 192.168.1.0/24
````

This performs a TCP SYN scan on all devices in the subnet.

### 4. Analyze Results

Note:

* Active IP addresses
* Open ports
* Common services running on those ports

### 5. (Optional) Use Wireshark

Capture traffic during the scan to see TCP handshake packets and analyze how scans work at a lower level.

### 6. Research Services

Understand what services are running on open ports and what risks they might pose (e.g., SSH on port 22, HTTP on 80, Telnet on 23).

### 7. Save Results

To a text file:

```bash
nmap -sS 192.168.1.0/24 -oN scan_results.txt
```

To an HTML file:

```bash
nmap -sS 192.168.1.0/24 -oX scan.xml
xsltproc scan.xml -o scan.html
```

---

## ✅ Outcome

* Identified devices on the local network
* Discovered open TCP ports and associated services
* Learned to interpret Nmap scan output
* Understood basic security risks related to exposed services
* Gained hands-on experience with reconnaissance tools used in ethical hacking
