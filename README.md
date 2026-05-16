<<<<<<< HEAD
# nci-k-network-design
NCI-K Hierarchical Network Design — Cisco Packet Tracer | VLANs, IPSec VPN, QoS, Dual Subnet
=======
\# NCI-K Hierarchical Network Design



\*\*Institution:\*\* National Cancer Institute of Kenya — Ministry of Health  

\*\*Designed by:\*\* Wayne Adwera | ICT Support Officer  

\*\*Tool:\*\* Cisco Packet Tracer 8.x  

\*\*GitHub:\*\* github.com/waywill14  



\## Overview



World-class hierarchical network design for NCI-K addressing QoS,

Availability, Security and Reliability. Solves the documented bottleneck

where ISP-delivered 700 Mbps degraded to 30-50 Mbps at end devices.



\## Physical Devices Used



| Device | Model in PT | Role |

|--------|-------------|------|

| ISP Router | Cisco 2911 | Simulated ISP handoff |

| Edge Router | Cisco 2911 | NAT, CBWFQ QoS, IPSec VPN |

| Firewall | Cisco ASA 5506-X | Zone ACLs, IPS, guest isolation |

| Core Router | Cisco 2911 | Inter-VLAN routing, dual subnet bridge |

| Meraki Switch | Cisco 3650-24PS | Single 10G switch, all end-device VLANs |

| Huawei Switch | Cisco 3560-24PS | Server farm only, VLAN 60 |



\## VLAN Plan



| VLAN | Name | Subnet |

|------|------|--------|

| 10 | Management | 10.118.10.0/24 |

| 20 | Clinical | 10.118.20.0/24 |

| 30 | DG-Office | 10.118.30.0/24 |

| 31 | Finance | 10.118.31.0/24 |

| 32 | Research | 10.118.32.0/24 |

| 33 | ICT | 10.118.33.0/24 |

| 40 | Admin | 10.118.40.0/24 |

| 50 | Guest-WiFi | 10.118.50.0/24 |

| 51 | Boardroom | 10.118.51.0/24 |

| 60 | Servers | 10.118.60.0/24 |

| 70 | VoIP | 10.118.70.0/24 |

| 200 | VPN-Pool | 10.118.200.0/24 |



\## Key Features



\- \*\*Bottleneck fix:\*\* CBWFQ guarantees VoIP 70 Mbps, Clinical 200 Mbps,

&#x20; Directorates 150 Mbps. RSTP replaces legacy STP — convergence under 2 seconds.

\- \*\*Dual subnet:\*\* New 10.118.x.x production network + legacy 10.10.20.0/24

&#x20; retained via dedicated Core Router Gi0/2 cable interface.

\- \*\*IPSec VPN:\*\* AES-256/SHA256. Remote clients reach both new and legacy

&#x20; subnets through a single encrypted tunnel.

\- \*\*VoIP:\*\* Cisco 7960 IP phones on VLAN 70. DHCP option 150 for TFTP.

&#x20; DSCP EF strict priority on all phone switch ports.

\- \*\*Directorate segmentation:\*\* Per-directorate VLANs enforce KDPA 2019

&#x20; compliance — Finance, Research, DG-Office and ICT are isolated from each other.

\- \*\*Wireless:\*\* 8 access points with WPA2-PSK, one per department zone.

\- \*\*Server security:\*\* Sticky MAC port-security on all Huawei switch ports.



\## Server Farm



| Server | IP | Role |

|--------|----|------|

| SERVER-WEB | 10.118.60.10 | ncikenya.go.ke |

| SERVER-DNS | 10.118.60.11 | DNS |

| SERVER-ERP | 10.118.60.12 | ERP / erplive |

| SERVER-DB | 10.118.60.13 | NaCaRe Database |

| SERVER-EMR | 10.118.60.14 | Electronic Medical Records |



\## Standards Met



\- ISO/IEC 27001 — Access control, change management

\- Kenya Data Protection Act 2019 — Directorate VLAN isolation

\- QoS — CBWFQ + DSCP end-to-end marking

\- RSTP — Sub-2-second convergence

\- IPSec IKEv1 — AES-256 SHA256 Group 5



\## How to Open



1\. Install Cisco Packet Tracer 8.x from netacad.com

2\. Open `NCI-K-Hierarchical-Network.pkt`

3\. All configurations are pre-loaded on every device



>>>>>>> 5373fb6 (feat: initial commit — NCI-K hierarchical network design with VoIP, VPN, dual subnet and directorate VLANs)
