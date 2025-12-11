# DHCP-Attack-Mitigation-with-AAA-SSH-and-ZPF-on-EVE-NG
DHCP SECURITY LAB ON EVE-NG
**1. OVERVIEW**
This project focuses on building a complete security laboratory environment on EVE-NG to study DHCP-related attacks and defensive mechanisms.
The lab simulates common Layer 2 attacks such as DHCP Starvation and Rogue DHCP Server, and evaluates the effectiveness of enterprise-grade security features including DHCP Snooping, AAA, SSH hardening, and Zone-Based Policy Firewall (ZPF).
The repository includes network diagrams, router/switch configurations, attack scripts, packet captures, and full experiment reports.

**2. OBJECTIVES**
Build a security-focused testbed simulating a Small to Medium Business (SMB) network using EVE-NG.
Implement core security technologies including DHCP Snooping, SSH, AAA authentication, and ZPF.
Simulate DHCP Starvation and Rogue DHCP Server attacks.
Compare the effectiveness of ACL-based filtering versus ZPF under identical attack conditions.
Analyze packet captures using Wireshark to understand attack behavior and defensive mechanisms.

**3. LAB ARCHITECTURE**
The lab topology includes:
Cisco IOS routers and switches
Attacker nodes running DHCP attack scripts
Legitimate DHCP server
End-user clients
AAA server (local or external)
ZPF applied on edge router
Traffic capture nodes for Wireshark analysis
Diagrams of the full network architecture are located in the diagrams/ folder.

**4. FEATURES AND IMPLEMENTATION**
**4.1 Security Mechanisms**
DHCP Snooping configuration for trusted/untrusted ports
Binding table verification and DHCP message validation
SSH secure remote access with v2 protocol
AAA local authentication for administrative access
Zone-Based Policy Firewall (ZPF) for stateful inspection
ACL baseline filtering for comparison

**4.2 Attack Simulation**
DHCP Starvation attack using scripted MAC address flooding
Rogue DHCP Server emulation to distribute fake IP addressing
Packet capture (.pcap) for both attack and defense scenarios
Attack scripts are stored in the attacks/ folder.

**5. TEST PROCEDURE**
Deploy the EVE-NG topology and configure all network devices.
Enable DHCP Snooping, AAA, SSH, and ZPF on the appropriate nodes.
Launch DHCP Starvation attack and observe:
DHCP pool exhaustion
CPU/RAM behavior
Packet traces
Launch Rogue DHCP Server attack and verify:
Unauthorized DHCP lease assignment
Effectiveness of Snooping trust boundaries
Compare ACL vs ZPF performance under identical traffic patterns.
Save packet captures for analysis.

**6. RESULTS AND ANALYSIS**
DHCP Snooping successfully blocks DHCP offers/acks from untrusted ports.
Rogue DHCP Server is prevented from issuing IP leases when Snooping is active.
ZPF provides higher visibility and control compared to traditional ACLs.
DHCP Starvation attack impact is significantly reduced when Snooping rate-limiting is enabled.
Packet captures show clear differentiation between allowed and dropped DHCP messages.
Detailed experiment reports are available in the reports/ folder.

**7. REPOSITORY STRUCTURE**
DHCP-Security-Lab-EVE-NG
 ┣ diagrams/          Network topology diagrams
 ┣ configs/           Cisco router, switch, AAA, and ZPF configurations
 ┣ attacks/           DHCP Starvation and Rogue DHCP scripts
 ┣ captures/          Wireshark packet capture files (.pcap)
 ┣ reports/           Documentation and analysis reports (PDF)
 ┣ eve-ng-project/    EVE-NG project files (.unl, topology)
 ┗ README.md

**8. REQUIREMENTS**
EVE-NG Community or Professional Edition
Cisco IOS images (supported versions)
Wireshark
Linux environment for running attack scripts
Basic knowledge of L2/L3 networking and security

**9. FUTURE DEVELOPMENT**
Add Dynamic ARP Inspection (DAI) testing
Implement IP Source Guard (IPSG)
Integrate external AAA (RADIUS/TACACS+)
Automate attack simulation with Python
Expand analysis with additional threat scenarios

**10. CONTACT**
Author: Phan Minh Trí
Field: Networking, SMB Network Security, Cisco Technologies
Purpose: Undergraduate Research Project (NCKH)
