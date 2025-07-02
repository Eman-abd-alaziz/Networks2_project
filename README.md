# 🌐 SNMP & HTTP Network Monitoring Tool

![banner](https://upload.wikimedia.org/wikipedia/commons/thumb/5/59/Simple_Network_Management_Protocol.svg/1920px-Simple_Network_Management_Protocol.svg.png)

> *"Keeping networks healthy, one packet at a time!"*  
> Developed for **Computer Networks 2 (10636455)**  
> Spring 2025 — Dr. Raed Alqadi  
> Department of Computer Engineering  
> 📅 Assignment 2 — SNMP & HTTP Integration

---

## 🚀 Project Overview

Imagine you’re the network administrator of a busy organization. You want to **monitor the health and status of network devices in real time**, modify system settings remotely, and gain insights about traffic and errors — all without physically accessing every device.

This project tackles exactly that challenge by leveraging **SNMP (Simple Network Management Protocol)** — a cornerstone technology in network management — combined with modern web and desktop technologies.

We built a **two-part solution**:  
- A **PHP backend** that talks SNMP to gather data from devices.  
- A **Java desktop client** that fetches this data via HTTP, presenting it in a clean, interactive GUI.

This lets you **view**, **edit**, and **track** important network metrics seamlessly.

---

## 🔍 Why SNMP & HTTP?

- **SNMP** is the universal language for network monitoring — routers, switches, servers, printers, and more all speak it.
- **PHP** makes it easy to build server-side apps that query SNMP agents and serve data over HTTP.
- **Java** offers a robust, platform-independent desktop client capable of fetching and visualizing SNMP data dynamically.
- Combining these means **no heavy or complex setups** like Tomcat or Servlets — just simple HTTP calls and pure PHP scripts.

---

## 🧩 What Does This Project Do?

### Part 1 — The PHP SNMP Manager

- **Explore the System Group:** Get core system info like name, contact, and location.  
- **Edit key fields:** Change `sysContact`, `sysName`, and `sysLocation` right from the web page, and have these changes pushed to the SNMP agent.  
- **Dive into TCP connections:** See all active TCP connections on the device.  
- **Analyze ICMP statistics:** Track network errors and messages with two methods (Get and Walk), side by side, for clear comparison.  
- **Smooth navigation:** Switch between pages effortlessly with a clean UI.

### Part 2 — The Java HTTP Client

- **Interactive GUI with tabs:**  
  - Tab 1: System Info (editable fields)  
  - Tab 2: TCP connections  
  - Tab 3: ICMP stats (walk method only)  
- **Buttons to fetch data on demand:** No polling needed, just click to update!  
- **Seamless integration:** The client requests PHP pages which respond with SNMP data — all via HTTP.  
- **Live feedback:** View data updates in real time, perfect for network troubleshooting.

---

## 🔧 How to Set Up & Run

### Prerequisites

- **XAMPP or WAMP** installed for running the PHP backend locally.  
- **Java JDK 8 or newer** to compile and run the Java client.  
- **SNMP enabled on your PC or device** to act as an SNMP agent.  
- **PHP SNMP extension** installed (usually enabled in XAMPP by default).

### Running the PHP Backend

1. Start Apache via XAMPP/WAMP control panel.  
2. Copy the PHP project files into the Apache `htdocs` directory (e.g., `C:\xampp\htdocs\snmp_project`).  
3. Open a browser and go to `http://localhost/snmp_project/index.php`.  
4. Use the navigation links to explore system info, TCP connections, and ICMP stats.  
5. Edit the system group values where allowed and submit changes to update the SNMP agent.

### Running the Java Client

1. Compile the Java source (e.g., `SNMPClient.java`) using your preferred IDE or command line.  
2. Run the Java application.  
3. Make sure the PHP backend is running and accessible (usually `http://localhost`).  
4. Use the GUI tabs and click the “Fetch Data” buttons to request the latest SNMP info.  
5. Edit system group fields on the first tab and submit changes — they will reflect back in the SNMP agent.

---

## 📂 Project Structure

```plaintext
snmp_project/
├── php/                         # PHP backend scripts
│   ├── system.php               # Handle SNMP system group data (GET/SET)
│   ├── tcp.php                  # Fetch TCP connection table
│   ├── icmp.php                 # Fetch ICMP statistics (GET and WALK)
│   ├── index.php                # Main navigation interface (optional)
│   └── assets/                  # CSS/JS files (if any)
├── java_client/                 # Java desktop application
│   ├── SNMPClient.java          # Main client source code
│   └── utils/                   # Helper classes (if applicable)
├── README.md                    # This documentation
└── LICENSE                      # (Optional) License file
