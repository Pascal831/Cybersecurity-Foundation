# 📡 Tcpdump – Capture Your First Packet

## 🎯 Scenario

You’re a **network analyst** using `tcpdump` to capture and analyze live network traffic on a **Linux VM**. This lab simulates a packet analysis task using CLI tools and a sample `.pcap` file.

---

## 🧰 Step-by-Step Instructions

### 1️⃣ Identify Network Interfaces

List available interfaces:
```bash
ifconfig
```

Use `tcpdump` to list interfaces available for capture:
```bash
tcpdump -D
```

---

### 2️⃣ Inspect Live Network Traffic with `tcpdump`

Capture and inspect packets in detail:
```bash
sudo tcpdump -i eth0 -v -c5
```

| Option       | Description                                |
|--------------|--------------------------------------------|
| `-i eth0`    | Specifies the interface (`eth0`)           |
| `-v`         | Verbose mode – display more packet details |
| `-c5`        | Capture 5 packets                          |

---

### 3️⃣ Capture Packets to a File

Capture HTTP traffic (port 80) and write it to a `.pcap` file:
```bash
sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &
```

| Option          | Description                                                            |
|-----------------|------------------------------------------------------------------------|
| `-nn`           | No name resolution (IP/port)                                           |
| `port 80`       | Filters only HTTP traffic                                              |
| `-w capture.pcap` | Save output to a capture file                                       |
| `&`             | Run process in background                                              |

Generate traffic for capture using:
```bash
curl opensource.google.com
```

Verify the file:
```bash
ls -l capture.pcap
```

---

### 4️⃣ Analyze Captured Packets

#### 📄 View Packet Headers
```bash
sudo tcpdump -nn -r capture.pcap -v
```

| Option | Description                                |
|--------|--------------------------------------------|
| `-r`   | Read from capture file                     |
| `-nn`  | Disable name lookups                       |
| `-v`   | Verbose output                             |

#### 🔍 View Hexadecimal and ASCII Format
```bash
sudo tcpdump -nn -r capture.pcap -X
```

| Option | Description                                                                 |
|--------|-----------------------------------------------------------------------------|
| `-X`   | Displays packets in both hex and ASCII format for in-depth analysis         |

> 💡 Analysts use `-X` output to identify signatures, malware, or unusual payload patterns in raw data.

---

## ✅ Summary

| Task                        | Command Example                                          |
|-----------------------------|----------------------------------------------------------|
| List interfaces             | `ifconfig`, `tcpdump -D`                                 |
| Capture live packets        | `sudo tcpdump -i eth0 -v -c5`                            |
| Save capture to file        | `sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &` |
| Generate HTTP traffic       | `curl opensource.google.com`                             |
| Review packet data          | `sudo tcpdump -nn -r capture.pcap -v`                    |
| Deep dive in hex/ASCII view | `sudo tcpdump -nn -r capture.pcap -X`                    |

---

Tcpdump is a **powerful network diagnostic tool** for real-time capture and post-capture analysis. It’s especially useful in incident response, traffic auditing, and threat hunting.

