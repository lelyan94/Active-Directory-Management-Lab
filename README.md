# 🖧 Active Directory Management Lab

This project simulates a small enterprise network using **VMware Workstation**, built for learning and demonstrating key infrastructure concepts: Active Directory, DNS, NAT, and DHCP. It includes a **Windows Server**, a **Linux DHCP server**, and **two Windows clients**.

![Image](https://github.com/user-attachments/assets/79020814-f4ca-4502-acfb-956722cccb68)


---

## 🛠️ Tools Used

- VMware Workstation
- Windows Server (Domain Controller, DNS, NAT)
- Ubuntu Server (DHCP)
- Windows 10 Clients

---

## 🧩 Project Structure

| Component          | Description                                                     |
|--------------------|-----------------------------------------------------------------|
| Windows Server     | AD, DNS setup, RRAS NAT for internet access                     |
| Linux DHCP Server  | Static IP, DHCP configuration, internal internet access         |
| Windows Clients    | DHCP address acquisition, domain join, connectivity testing     |

---

## 🖥️ VMware Network Topology

Each VM is configured with appropriate NICs in VMware Workstation. The layout shows:
- Network adapter types
- Internal and external routing through NAT

- **Windows Server**
![Windows Server](https://github.com/user-attachments/assets/2b407740-301a-41a0-ba19-5ee00ffb537f)

- **Linux DHCP Server**
![Linux DHCP Server](https://github.com/user-attachments/assets/a43f8287-5a49-4365-8488-8beba85a1d2a)

- **Windows Client 1**
![Windows Client 1](https://github.com/user-attachments/assets/08e8a965-ea86-4ecc-b2d7-d226945c686f)

- **Windows Client 2**
![Windows Client 2](https://github.com/user-attachments/assets/2b407740-301a-41a0-ba19-5ee00ffb537f)

---

## 🪟 Windows Server Configuration

### 🔹 Active Directory Setup

The server is configured as a Domain Controller. These screenshots show:
- Two Windows clients added to the domain
- Five user accounts created

![Clients in AD](https://github.com/user-attachments/assets/23479f25-ee90-4c0b-a995-f9a739f2a74f)
![Users in AD](https://github.com/user-attachments/assets/e286a9dd-d448-4844-947d-dba291bf0d23)

### 🔹 DNS Configuration

Configured Forward Lookup Zone to resolve internal domain names. A records were added for each device.

![DNS Zone](https://github.com/user-attachments/assets/7b89139c-eb07-4806-a024-2dfc82acd872)

### 🔹 RRAS NAT Setup

The Windows Server is configured with RRAS to provide internet access for internal machines through NAT.

![RRAS NAT](https://github.com/user-attachments/assets/37ec644a-be30-45ba-a56a-779ad7b4c846)

### 🔹 Server Network Configuration

`ipconfig /all` confirms static IP, correct DNS and gateway setup.

![Server IP Config](https://github.com/user-attachments/assets/a654cd9a-7409-43e5-a4a0-0f6c7ff7f6c2)

---

## 🐧 Linux DHCP Server Configuration

### 🔹 Static IP and System Info

Commands executed:
- `ip add` to show network interface configuration
- `ip route` to verify routing table
- `hostname` to confirm system name
- `cat /etc/resolv.conf` to show DNS settings

This confirms static IP setup and internal communication.

![ip add](https://github.com/user-attachments/assets/1cbe1ab1-d548-42aa-9922-3cef836915fc)
![ip route](https://github.com/user-attachments/assets/ea23a4de-51c2-4145-8969-4dc49bcabde6)
![hostname](https://github.com/user-attachments/assets/1b3ca73d-3a85-44db-821c-de59d245776b)
![resolv.conf](https://github.com/user-attachments/assets/95b5d8ad-bed3-45a8-a847-6d5675bdfeed)

### 🔹 Internet Connectivity Test

Proves that the Linux server can access the internet through the NAT-configured Windows Server.

![Internet Ping 1](https://github.com/user-attachments/assets/4ca03bc0-aeb8-4f75-8961-d908f3fdc6b6)
![Internet Ping 2](https://github.com/user-attachments/assets/3c3487c2-6c22-4816-bf93-b11d5c0087f2)

### 🔹 DHCP Scope

Shows the DHCP configuration range used to assign IPs to Windows clients.

![DHCP Scope](https://github.com/user-attachments/assets/b4f07681-53e8-4128-b653-5b5a67be9ab1)

---

## 💻 Windows Client 1

### 🔹 DHCP Lease & Domain Info

Shows that Client 1 received an IP from the DHCP server and joined the domain.

![Client1 IPConfig](https://github.com/user-attachments/assets/6fc5909f-7ff1-49d5-864f-22211293e23b)

### 🔹 Hostname Resolution

Tests ping to other domain devices by hostname — validating DNS.

![Ping by Hostname](https://github.com/user-attachments/assets/ce039072-f27f-49e3-9aa3-bad83d97fd37)

### 🔹 Mapped Network Drive

Verifies mapped drive appears after domain login — proof of applied group policy or login script.

![Mapped Drive](https://github.com/user-attachments/assets/b5317564-54b3-4475-b1a3-006635926868)

---

## 💻 Windows Client 2

### 🔹 Hostname Resolution

Pings to Linux DHCP server and Client 1 — confirming name resolution works both ways.

![Client2 Ping 1](https://github.com/user-attachments/assets/6c62eb8e-47e1-4c9a-a494-316ff9e567fe)
![Client2 Ping 2](https://github.com/user-attachments/assets/fd482a54-d6c2-4825-ad94-3bf9b09ecff2)

### 🔹 Internet Access

Client 2 can reach the internet through the NAT-enabled Windows Server.

![Client2 Internet](https://github.com/user-attachments/assets/4e14073b-13d0-4330-bf10-3cf09d784ec6)

### 🔹 Domain User Login Verification

Using `whoami` to confirm a different domain user is logged in, verifying centralized domain authentication.

![whoami](https://github.com/user-attachments/assets/67af7ff8-2a2d-4a33-856b-47d8c6ba3947)

---

## 📌 Summary

This lab successfully simulates a domain-based network with:

- ✔️ Active Directory and centralized user management
- ✔️ Internal DNS resolution
- ✔️ NAT internet access via RRAS
- ✔️ DHCP services on a separate Linux server
- ✔️ Mapped drives and hostname resolution
- ✔️ Domain login from multiple clients

All services are configured and tested inside an isolated VMware Workstation environment, making this a complete self-contained infrastructure lab.

---

