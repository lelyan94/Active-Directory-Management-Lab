# Active-Directory-Management-Lab
AD-Network-Lab-Simulation

#🖧 AD Network Lab Simulation

# Introduction
This project demonstrates a basic Active Directory and DHCP network lab using VMware Workstation. The lab includes Windows Server, Linux DHCP server, and two Windows clients, simulating a functional domain environment.

## 🛠️ Tools Used
- VMware Workstation
- Windows Server
- Ubuntu Server (DHCP)
- Windows 10 Clients

## 📁 Project Structure
- `Windows Server`: AD, DNS, NAT, and RRAS configuration
- `Linux DHCP Server`: Static IP setup, DHCP service, internet access
- `Windows Clients`: Domain joining, IP assignment, connectivity tests

## 🔧 VMware Workstation

### ➤ VMware Workstation – Network Topology

This screenshot displays the full network setup in VMware Workstation. It shows all four virtual machines: Windows Server, Linux DHCP server, and two Windows Clients. It also highlights the network adapter configuration for each VM, simulating an internal network with NAT and DHCP.

Windows SERVER 
![Image](https://github.com/user-attachments/assets/2b407740-301a-41a0-ba19-5ee00ffb537f)

Linux DHCP SERVER
![Image](https://github.com/user-attachments/assets/a43f8287-5a49-4365-8488-8beba85a1d2a)

Windows Client1
![Image](https://github.com/user-attachments/assets/08e8a965-ea86-4ecc-b2d7-d226945c686f)

Windows Client2
![Image](https://github.com/user-attachments/assets/2b407740-301a-41a0-ba19-5ee00ffb537f)


🪟 Windows Server
➤ Active Directory – Users and Computers
The Windows Server is configured as a domain controller. This screenshot shows the Active Directory Users and Computers interface, where:

- Two Windows clients have been successfully joined to the domain.
  
  ![Image](https://github.com/user-attachments/assets/23479f25-ee90-4c0b-a995-f9a739f2a74f)
  
- Five domain user accounts have been created.
  
![Image](https://github.com/user-attachments/assets/e286a9dd-d448-4844-947d-dba291bf0d23)

➤ DNS – Forward Lookup Zones
The DNS service is installed on the Windows Server. This screenshot shows the Forward Lookup Zones, which include host (A) records for internal machines. This allows domain name resolution within the local network.

![Image](https://github.com/user-attachments/assets/7b89139c-eb07-4806-a024-2dfc82acd872)

➤ RRAS – NAT Configuration
This screenshot shows the Routing and Remote Access Service (RRAS) setup. The Windows Server is configured to act as a NAT gateway, allowing internal machines (clients and Linux server) to access the internet through the server’s external NIC.

![Image](https://github.com/user-attachments/assets/37ec644a-be30-45ba-a56a-779ad7b4c846)

➤ IP Configuration of Windows Server
This screenshot shows the result of the ipconfig /all command on the Windows Server. It confirms the static IP address, DNS settings, gateway configuration, and domain details for the server.

![Image](https://github.com/user-attachments/assets/a654cd9a-7409-43e5-a4a0-0f6c7ff7f6c2)

🐧 Linux DHCP Server
➤ Static IP and Host Settings
This screenshot combines outputs from:

- ip add
- ip route
- hostname
- cat /etc/resolv.conf

It confirms that the Linux server is using a static IP address and is properly configured as a DHCP server in the local network.

![Image](https://github.com/user-attachments/assets/fd6ce034-b536-44d5-ba0e-4ed6bf4f374b)











