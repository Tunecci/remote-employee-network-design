# Network Design Documentation

## 1. Introduction

This document explains the network architecture designed for a remote employee who needs secure access to company resources.

The design separates remote access, public-facing services, and private internal resources into different network areas.

The main security components are a VPN, firewall, DMZ, and internal network segmentation.

## 2. Network Zones

The network is divided into three main areas.

### Remote Network

The remote employee uses a laptop connected to a home Wi-Fi router.

The home network connects to the public internet. The employee uses a VPN to establish a secure connection to the company network.

### DMZ

The DMZ (Demilitarized Zone) contains the public-facing web server.

The purpose of the DMZ is to isolate systems that may receive external traffic from the organization's private internal network.

Example network:

`192.168.20.0/24`

### Internal Network

The internal network contains private company resources such as employee computers, internal servers, and wireless network access.

Example network:

`192.168.10.0/24`

These are example private network ranges used for the architecture.

## 3. Traffic Flow

The expected traffic flow for the remote employee is:

```text
Remote Laptop
      ↓
Home Wi-Fi Router
      ↓
Internet
      ↓
Encrypted VPN Tunnel
      ↓
Company Firewall
      ↓
Authorized Internal Resources
```

External users accessing the company's public-facing service follow a different path:

```text
Internet
   ↓
Firewall
   ↓
DMZ
   ↓
Web Server
```

The internal network is kept separate from the DMZ.

## 4. Firewall

The firewall acts as the main security boundary in the architecture.

Potential firewall responsibilities include:

* Filtering inbound and outbound traffic
* Controlling traffic between network zones
* Restricting access to internal resources
* Supporting VPN connections
* Blocking unauthorized connections
* Applying security policies

The firewall helps prevent unrestricted communication between the internet, DMZ, and internal network.

## 5. VPN

The VPN provides an encrypted connection for the remote employee.

The VPN connection helps protect traffic as it travels across the public internet.

A production environment could also use additional controls such as:

* Multi-factor authentication
* Strong authentication policies
* Device verification
* Access restrictions
* VPN activity logging

## 6. DMZ Security

The web server is placed in the DMZ because it may need to receive requests from external users.

The DMZ provides an additional security boundary between the public-facing web server and private internal systems.

The web server should not have unrestricted access to the internal network.

Only specifically authorized communication should be permitted between the DMZ and internal network.

## 7. Internal Network

The internal network contains private organizational resources.

These include:

* Employee PCs
* Internal server
* Network switch
* Wireless access point

Internal resources should only be accessible to authorized users and systems.

Additional controls could include network access control, endpoint security, authentication, and monitoring.

## 8. Network Connections

### Wi-Fi

The remote laptop connects to the home router using Wi-Fi.

The wireless access point in the company network can provide wireless connectivity for authorized devices.

### Ethernet

The internal switch provides wired connectivity to devices such as:

* Employee PCs
* Internal servers
* Wireless access points

### VPN

The VPN provides an encrypted remote connection between the employee and the company's VPN endpoint.

## 9. Example Protocols

| Protocol / Technology | Purpose                      |
| --------------------- | ---------------------------- |
| HTTPS                 | Secure web communication     |
| VPN                   | Secure remote network access |
| Ethernet              | Wired network connectivity   |
| Wi-Fi                 | Wireless connectivity        |
| IPv4                  | Network addressing           |
| TCP/IP                | Network communication        |

## 10. Security Considerations

The following security practices could strengthen the architecture:

* Use strong VPN authentication
* Enable multi-factor authentication
* Apply least-privilege access
* Keep servers and network devices patched
* Monitor network activity
* Maintain firewall logs
* Restrict communication between network zones
* Protect wireless networks with modern security standards
* Regularly review firewall and VPN access rules

## 11. Limitations

This project is a conceptual network design and does not represent a production network implementation.

The IP addresses, firewall rules, servers, and security controls shown are examples used to demonstrate networking and cybersecurity concepts.

No real company network or production system was accessed during this project.

## 12. Conclusion

The design demonstrates how a remote employee can connect to company resources through a controlled and segmented network architecture.

The use of a VPN, firewall, DMZ, and internal network segmentation provides multiple security boundaries and demonstrates fundamental principles of secure network design.
