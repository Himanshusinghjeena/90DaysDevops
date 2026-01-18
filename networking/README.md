# 🌟 90 Days of DevOps – 2025 Edition

## Week 1: Networking Fundamentals

Welcome to **Week 1** of my **#90DaysOfDevOps2025** journey! 🚀
This week focuses on **Networking**, the backbone of all cloud and DevOps systems.

This README is written in a **beginner-friendly** way so anyone can understand and revise quickly.

---

# 📌 What I Learned This Week

✅ OSI & TCP/IP Models
✅ Common Networking Protocols & Ports
✅ AWS EC2 & Security Groups
✅ Essential Networking Commands

---

# 1️⃣ OSI Model (7 Layers) – Detailed Explanation

The **OSI (Open Systems Interconnection)** model explains **how data moves from your device to another device over a network**. Each layer has a specific responsibility.

### 🔄 How Data Travels (Simple Flow)

When you open a website:

1. You type URL → Application layer
2. Data gets formatted → Presentation layer
3. Session is created → Session layer
4. Data is broken into packets → Transport layer
5. IP routing happens → Network layer
6. Frames created → Data Link layer
7. Bits travel through cable/wifi → Physical layer

---

| Layer | Name         | What it Does                 | Real Example       |
| ----- | ------------ | ---------------------------- | ------------------ |
| 7     | Application  | Interface for user & network | Browser using HTTP |
| 6     | Presentation | Encrypts, compresses data    | SSL, JSON format   |
| 5     | Session      | Maintains session            | Login session      |
| 4     | Transport    | Reliable delivery            | TCP/UDP            |
| 3     | Network      | Routing packets              | IP address         |
| 2     | Data Link    | MAC addressing               | Switch             |
| 1     | Physical     | Sends raw bits               | Cable, WiFi        |

---

### 🧩 Layer-by-Layer Deep Explanation

#### 🔹 Layer 7 – Application

* Closest to the user
* Provides network services
* Protocols: HTTP, HTTPS, FTP, SMTP

👉 Example:
When you open **google.com**, browser uses HTTP to request webpage.

---

#### 🔹 Layer 6 – Presentation

* Converts data format
* Encrypts/decrypts data

👉 Example:
HTTPS encrypts data before sending.

---

#### 🔹 Layer 5 – Session

* Starts & ends sessions
* Handles authentication

👉 Example:
Keeps you logged in to Gmail.

---

#### 🔹 Layer 4 – Transport

* Breaks data into packets
* Handles retransmission

Protocols:

* TCP → Reliable
* UDP → Fast

👉 Example:
Downloading file uses TCP.

---

#### 🔹 Layer 3 – Network

* Finds best route
* Uses IP addresses

👉 Example:
Router sends packet to correct network.

---

#### 🔹 Layer 2 – Data Link

* Adds MAC address
* Error detection

👉 Example:
Switch forwards data inside LAN.

---

#### 🔹 Layer 1 – Physical

* Actual transmission
* Bits move as signals

👉 Example:
Ethernet cable, fiber optics.

---

# 2️⃣ TCP/IP Model – How it Works

TCP/IP is a **practical model** used on the internet.

| Layer          | OSI Mapping | Function              |
| -------------- | ----------- | --------------------- |
| Application    | 7,6,5       | User communication    |
| Transport      | 4           | Data transfer         |
| Internet       | 3           | Routing               |
| Network Access | 2,1         | Physical transmission |

---

### 🔄 Data Transfer in TCP/IP

Example: Accessing website

1. Application Layer

   * Browser sends HTTP request

2. Transport Layer

   * TCP breaks data
   * Adds port numbers

3. Internet Layer

   * IP adds source & destination IP

4. Network Access Layer

   * Converts to frames
   * Sends through cable

---

### 🧠 OSI vs TCP/IP Connection

| OSI          | TCP/IP         |
| ------------ | -------------- |
| Application  | Application    |
| Presentation | Application    |
| Session      | Application    |
| Transport    | Transport      |
| Network      | Internet       |
| Data Link    | Network Access |
| Physical     | Network Access |

---

### 🔑 Key Difference

OSI = **Theoretical model**
TCP/IP = **Practical implementation**

---

### 📌 Real-World Flow

```
User → Browser → HTTP → TCP → IP → Router → Server
```

---

-----|------|-------------------|
| 7 | Application | HTTP, HTTPS, FTP, SMTP |
| 6 | Presentation | Data encryption, SSL |
| 5 | Session | Session management |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, Routing |
| 2 | Data Link | MAC address, Switch |
| 1 | Physical | Cables, Ethernet |

### 🔍 Example

When you open a website:

* Browser uses **HTTP (Layer 7)**
* Data moves via **TCP (Layer 4)**
* Routed using **IP (Layer 3)**

---

# 2️⃣ TCP/IP Model (4 Layers)

| Layer          | Description     |
| -------------- | --------------- |
| Application    | HTTP, FTP, SMTP |
| Transport      | TCP, UDP        |
| Internet       | IP              |
| Network Access | Ethernet        |

👉 TCP/IP is used in **real-world internet communication**.

---

# 3️⃣ Common Protocols & Ports – How They Work

Protocols are **rules for communication** between computers. Each protocol works on a **specific port** and has a unique role in DevOps.

---

| Protocol | Port | Purpose                  |
| -------- | ---- | ------------------------ |
| HTTP     | 80   | Web communication        |
| HTTPS    | 443  | Secure web communication |
| FTP      | 21   | File transfer            |
| SSH      | 22   | Secure server login      |
| DNS      | 53   | Domain name resolution   |
| SMTP     | 25   | Email sending            |

---

## 🔹 1. HTTP (Port 80)

**HyperText Transfer Protocol**

### How it works

1. Client (browser) sends HTTP request
2. Server processes request
3. Server sends HTTP response

```
Client → HTTP Request → Server
Client ← HTTP Response ← Server
```

### Example

You type: `http://example.com`

* Browser sends GET request
* Server returns HTML page

### DevOps Use

* Hosting websites
* API communication

---

## 🔹 2. HTTPS (Port 443)

**Secure version of HTTP**

### How it works

1. SSL/TLS handshake
2. Encryption keys exchanged
3. Secure data transfer

```
Client ⇄ Encrypted Tunnel ⇄ Server
```

### Example

Banking websites

### DevOps Use

* Secure deployments
* Certificates management

---

## 🔹 3. FTP (Port 21)

**File Transfer Protocol**

### How it works

1. Client connects to server
2. Authentication
3. Upload/Download files

```
Client ⇄ FTP Server
```

### DevOps Use

* Upload application files
* Backup transfer

⚠️ Not secure → SFTP preferred

---

## 🔹 4. SSH (Port 22)

**Secure Shell**

### How it works

1. Client sends connection request
2. Server verifies key/password
3. Encrypted terminal session

```
Local Machine → SSH → Remote Server
```

### Example

```bash
ssh ubuntu@server_ip
```

### DevOps Use

* Server management
* CI/CD automation

---

## 🔹 5. DNS (Port 53)

**Domain Name System**

### How it works

1. User enters domain
2. DNS server finds IP
3. Returns IP address

```
google.com → DNS → 142.xxx.xxx
```

### DevOps Use

* Load balancing
* Domain routing

---

## 🔹 6. SMTP (Port 25)

**Simple Mail Transfer Protocol**

### How it works

1. Sender mail server connects
2. Transfers email
3. Receiver server stores it

```
Sender → SMTP → Receiver
```

### DevOps Use

* Alerts
* Monitoring notifications

---

# 🎯 Summary

✔ HTTP → website communication
✔ HTTPS → secure browsing
✔ FTP → file transfer
✔ SSH → server login
✔ DNS → domain resolution
✔ SMTP → email sending

---

---------|------|--------------|
| HTTP | 80 | Web servers |
| HTTPS | 443 | Secure websites |
| FTP | 21 | File transfer |
| SSH | 22 | Server access |
| DNS | 53 | Domain resolution |
| SMTP | 25 | Email sending |

### Why DevOps Engineers Care?

* SSH → Access servers
* HTTP/HTTPS → Deploy apps
* DNS → Domain mapping

---

# 4️⃣ AWS EC2 & Security Groups

### 🔹 What is EC2?

Elastic Compute Cloud → Virtual server in AWS

### 🔹 What are Security Groups?

* Act like a **firewall**
* Control **inbound & outbound traffic**

### 📘 Steps I Followed

1. Login to AWS Console
2. Go to EC2 Dashboard
3. Launch instance
4. Create Security Group
5. Allow ports (22, 80, 443)
6. Attach to instance

### Example Rules

| Type  | Port | Purpose      |
| ----- | ---- | ------------ |
| SSH   | 22   | Remote login |
| HTTP  | 80   | Web access   |
| HTTPS | 443  | Secure web   |

---

# 5️⃣ Networking Commands Cheat Sheet

| Command    | Use                |
| ---------- | ------------------ |
| ping       | Check connectivity |
| traceroute | Trace route        |
| netstat    | Network stats      |
| curl       | API requests       |
| dig        | DNS lookup         |
| nslookup   | Domain info        |

### Example

```bash
ping google.com
curl https://api.github.com
nslookup google.com
```

---

# 🧠 Key Takeaways

✔ Networking is **core skill** for DevOps
✔ Security Groups protect servers
✔ Protocols help apps communicate
✔ Commands help debug issues

---

# 📎 Resources Used

* GeeksForGeeks
* AWS Documentation
* Cloudflare DNS Guide

---

# 🏆 My Progress

Week 1 ✅ Completed
Feeling confident in **Networking Basics** 🌐

---

# 🔗 Connect With Me

📌 LinkedIn: *Add your profile link*
📌 GitHub: *Add your repo link*

---

# 📢 Hashtags

#90DaysOfDevOps2025 #DevOps #Networking #AWS #CloudComputing

---

⭐ If you found this helpful, don't forget to **star** this repo!
