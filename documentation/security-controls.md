# Security Controls Documentation

## 1. Overview

Security controls are used in this network design to reduce unauthorized access and limit the impact of potential security incidents.

The main controls demonstrated in this project are firewall protection, VPN access, network segmentation, DMZ isolation, access control, and secure wireless connectivity.

## 2. Firewall

The firewall is positioned between the public internet and the company's network.

### Security functions

* Filters network traffic
* Controls connections between network zones
* Blocks unauthorized traffic
* Applies network access rules
* Supports VPN connectivity

The firewall provides the primary security boundary for the network.

## 3. VPN Security

The VPN provides secure remote access for employees working outside the organization.

### Security considerations

* Use strong authentication
* Require multi-factor authentication where possible
* Restrict VPN access to authorized users
* Monitor VPN activity
* Remove access when users no longer require it

The VPN prevents remote users from needing direct, unrestricted access to the internal network over the public internet.

## 4. Network Segmentation

The architecture separates the network into different security zones.

### Zones

**DMZ**

Contains public-facing services such as the web server.

**Internal Network**

Contains private company resources such as employee computers and internal servers.

Segmentation limits unnecessary communication between systems and can reduce the potential impact of a compromised system.

## 5. DMZ Security

The web server is placed inside the DMZ because it may receive traffic from external users.

Security controls should include:

* Restricting inbound traffic
* Limiting outbound connections
* Preventing unrestricted access to the internal network
* Keeping the server patched
* Monitoring server activity
* Using HTTPS for web communication

## 6. Access Control

Access to internal resources should be limited based on user roles and business requirements.

The principle of **least privilege** should be applied.

Users should only receive the access required to perform their responsibilities.

## 7. Wireless Security

The internal wireless access point should use modern wireless security standards such as WPA2 or WPA3.

Additional controls could include:

* Strong wireless passwords
* Separate guest networks
* Regular credential changes
* Access restrictions
* Monitoring connected devices

## 8. Monitoring and Logging

Security logs can help identify unusual activity and support investigations.

Potential logs include:

* Firewall logs
* VPN connection logs
* Authentication logs
* Server logs
* Network activity logs

Centralized monitoring could be added in a more advanced implementation.

## 9. Patch Management

Network devices, servers, and endpoints should be regularly updated.

Keeping systems patched helps address known vulnerabilities and reduces unnecessary security exposure.

## 10. Multi-Factor Authentication

Multi-factor authentication can provide an additional layer of protection for sensitive access points such as:

* VPN
* Administrative accounts
* Internal applications
* Cloud services

A compromised password alone would not necessarily be sufficient to access protected resources.

## 11. Security Principles Demonstrated

This project demonstrates several fundamental cybersecurity principles:

* Defense in depth
* Least privilege
* Network segmentation
* Access control
* Secure remote access
* Attack surface reduction
* Monitoring and logging

## 12. Future Security Improvements

A production implementation could be expanded with:

* IDS/IPS
* SIEM
* Endpoint Detection and Response (EDR)
* Network Access Control (NAC)
* Centralized identity management
* Vulnerability scanning
* Security monitoring
* Automated alerting
* Regular penetration testing

## 13. Conclusion

The network design combines multiple security controls rather than relying on a single security mechanism.

The firewall controls network traffic, the VPN provides secure remote access, and network segmentation separates public-facing systems from private resources.

Together, these controls demonstrate the basic principles of designing a more secure network architecture.
