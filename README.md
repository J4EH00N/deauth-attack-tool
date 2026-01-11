# 📡 802.11 Deauth Attack Tool

![Language](https://img.shields.io/badge/language-C-blue)
![Platform](https://img.shields.io/badge/platform-Linux-black)
![License](https://img.shields.io/badge/license-MIT-green)

A lightweight C-based tool to perform **Wi-Fi Deauthentication attacks** using the `libpcap` library. This project demonstrates raw 802.11 packet injection and management frame manipulation for educational and research purposes.

## ⚠️ Disclaimer

> **This tool is for educational and security research purposes only.**
>
> Usage of this tool for attacking targets without prior mutual consent is illegal. It is the end user's responsibility to obey all applicable local, state, and federal laws. Developers assume no liability and are not responsible for any misuse or damage caused by this program.

## 🛠️ Features

- **Raw Packet Injection**: Constructs and sends 802.11 management frames from scratch.
- **Auto Channel Hopping**: Automatically switches the wireless interface to the target AP's channel.
- **Targeted & Broadcast Attacks**: Supports deauthenticating specific clients or the entire network (Broadcast).
- **Lightweight**: Written in pure C with minimal dependencies (`libpcap`).

## 📦 Prerequisites

- **Kali Linux** (or any Linux distro with wireless support)
- **Wi-Fi Adapter** supporting **Monitor Mode** and **Packet Injection**.
- `libpcap` library.

```bash
sudo apt-get update
sudo apt-get install libpcap-dev
```

## 🚀 Installation & Build

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/deauth-attack-tool.git
   cd deauth-attack-tool
   ```

2. Compile the source code:
   ```bash
   # Using GCC directly
   gcc -o deauth deauth.c -pcap

   # Or using Make (if Makefile is present)
   make
   ```

## 📖 Usage

Run the tool with root privileges:

```bash
sudo ./deauth
```

Follow the interactive prompts:
1. Enter your interface name (e.g., `wlan0mon`).
2. Enter the Target AP's MAC address.
3. Enter the Target Station's MAC address (or `broadcast`).
4. Enter the channel number.

### Monitor Mode Setup
Before running the tool, ensure your interface is in monitor mode:

```bash
sudo airmon-ng start wlan0
# Your interface will likely change to wlan0mon
```

## 📝 Code Structure

- **`deauth.c`**: Main source code containing packet structures and injection logic.
- **`Radiotap Header`**: Metadata for the kernel to handle wireless transmission.
- **`802.11 Header`**: MAC header definition for Management Frames.
- **`Deauth Body`**: Payload containing the Reason Code (7).

## 🔗 Blog Post
For a detailed explanation of the code and packet structure, check out my blog post:
[[https://sjh4ck3r.tistory.com/60]]
---
*Created by SJH4CK3R*
