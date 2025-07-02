# 🌐 SNMP & HTTP Network Monitoring Tool

![banner](https://upload.wikimedia.org/wikipedia/commons/thumb/5/59/Simple_Network_Management_Protocol.svg/1920px-Simple_Network_Management_Protocol.svg.png)

> Developed as part of **Computer Networks 2 (10636455)**  
> Spring 2025 — Dr. Raed Alqadi  
> Department of Computer Engineering  
> 📅 Assignment 2 — SNMP & HTTP Integration

---

## 📌 Overview

This project is a comprehensive SNMP-based monitoring system that combines **PHP for SNMP data collection** and a **Java HTTP client** for real-time access and interactivity.

The assignment is divided into two main parts:  
- **Part 1:** Web interface built with PHP to retrieve and display SNMP data.  
- **Part 2:** A Java-based desktop client using HTTP requests to fetch and display SNMP data from the PHP backend.

---

## 🧩 Features

### 🔸 PHP SNMP Manager (Part 1)
- Display full **System Group** information (except `systemServices`)  
- Editable fields: `sysContact`, `sysName`, `sysLocation`  
- Display complete **TCP connection table**  
- Display **ICMP Group** statistics using both:  
  - `snmp2_get()` (OID-based GET)  
  - `snmp2_walk()` (sequential walk)  
- Two ICMP statistics tables displayed side-by-side  
- Modern multi-page interface with navigation  

### 🔸 Java HTTP Client (Part 2)
- Three-tab GUI:  
  - 🧾 Tab 1: System Group (with editable fields)  
  - 📊 Tab 2: TCP Table  
  - 📈 Tab 3: ICMP Statistics (walk method only)  
- Each tab includes a "Fetch Data" button  
- Communicates with the PHP server using `HttpURLConnection`  
- Parses and displays the returned SNMP data in real-time  
- Seamless backend integration with PHP (reused from Part 1)  

---

## 🛠️ Technologies Used

| Component  | Technology                  |
|------------|-----------------------------|
| Web        | PHP (Pure, procedural)       |
| Backend    | SNMPv2 via `snmp2_get()` & `snmp2_walk()` |
| Web Server | XAMPP or WAMP                |
| Frontend   | HTML, JavaScript (Fetch/AJAX) |
| Client     | Java (HTTP Connection class)  |
| Protocols  | SNMP v2, HTTP                |

---

## 🚀 Getting Started

### 🔧 Prerequisites
- 🖥️ Local web server (e.g. [XAMPP](https://www.apachefriends.org/))  
- ☕ Java JDK 8+  
- Enable SNMP on your PC (Windows or Linux)  
- PHP SNMP extension installed  

---

## 🔍 How to Run

### ▶️ PHP SNMP Manager (Part 1)
1. Start Apache service from XAMPP  
2. Place the project folder in the `htdocs` directory  
3. Open your browser and navigate to `http://localhost/snmp_project/index.php`  
4. Use the navigation to switch between:  
   - System Info  
   - TCP Table  
   - ICMP Statistics (GET & WALK)  

📌 Edit SNMP values directly from the form fields  

### ▶️ Java HTTP Client (Part 2)
1. Compile and run `SNMPClient.java`  
2. Ensure the PHP server is running at `http://localhost/`  
3. Use the Java GUI tabs to fetch data from:  
   - `/system.php`  
   - `/tcp.php`  
   - `/icmp.php`  
4. Updated values will display dynamically in the Java client  



