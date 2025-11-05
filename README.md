# Milestone 2

## Updates Only
No updates to Technologies and Softwares as defined in the previous Milestone.

## Network Design
### Physical Diagram
![Alt text](milestone2/physical_network.png "Physical Diagram")
### Logical Diagram
![Alt text](milestone2/logical_network.png "Logical Diagram")
### VLAN Table
| VLAN | Name        | IP Subnet         | Hosts / Services                        |
|------|--------------|-------------------|------------------------------------------|
| 200    | Servers      | 192.168.2.0/24    | DNS, Web Server, File Server, IDS/IPS/SIEM, Metric Server, Vuln Scanner, Database, AD  |
| 201   | Backup Server   | 192.168.6.0/24   | Backup Database, Backup AD                   |
| 202   | Employee Workstations     | 192.168.10.0/24   | Employee Workstations         |
| 203   | Executives       | 192.168.100.0/24   | Executive Workstations                        |

## Hosts Inventory
| Hostname       | IP Address     | VLAN | Role              | Local Admin Account | Status   |
|----------------|----------------|------|-------------------|----------------|----------|
| alpha-0        | 172.16.40.21, 192.168.1.1  | None   | Router        | root      | Configured |
| alpha-1       | 192.168.2.2   | 200   | DNS, Web Server        | localadmin          | Installed   |
| alpha-2    | 192.168.2.3    | 200    | SIEM, Metric Server, Vulnerability Scanner       | localadmin       | Installed   |
| alpha-3       | 192.168.2.4  | 200   | File Server       | localadmin     | Installed   |
| alpha-4       | 192.168.2.5  | 200   | Database, Active Directory     | Administrator   | Installed  |
| alpha-5        | 192.168.6.2  | 201   | Backup Server        | Administrator      | Installed |
| beta-0        | 192.168.100.2  | 203   | Remote: Emily Brown        | admin      | Installed |
| beta-1        | 192.168.100.3  | 203   | Remote: Albert Tay        | admin      | Installed |
| beta-2        | 192.168.100.4  | 203   | Remote: Alex Patel        | admin      | Installed |
| beta-3        | DHCP  | 202   | Remote: Olivia Davis        | admin      | Installed |
| gamma-0        | DHCP  | 202   | Hybrid Workstation        | admin      | Installed |
| gamma-1        | DHCP  | 202   | Hybrid Workstation        | admin      | Installed |
| delta-0        | DHCP  | 202   | Rachel Nguyen        | admin      | Installed |
| delta-1        | DHCP  | 202   | Karen Taylor        |       | Installed |
| delta-2        | DHCP  | 202   | Jessica Rodriguez       | omega      | Installed |
| delta-3        | DHCP  | 202   | Ryan Lee        | omega      | Installed |
| delta-4        | DHCP  | 202   | Ben Anderson        | admin      | Installed |

### Installation Proof
#### alpha-0
![Alt Text](milestone2/alpha-0.png "alpha-0")
#### alpha-1
![Alt Text](milestone2/alpha-1.png "alpha-1")
#### alpha-2
![Alt Text](milestone2/alpha-2.png "alpha-2")
#### alpha-3
![Alt Text](milestone2/alpha-3.png "alpha-3")
#### alpha-4
![Alt Text](milestone2/alpha-4.png "alpha-4")
#### alpha-5
![Alt Text](milestone2/alpha-5.png "alpha-5")
#### beta-0
![Alt Text](milestone2/beta-0.png "beta-0")
#### beta-1
![Alt Text](milestone2/beta-1.png "beta-1")
#### beta-2
![Alt Text](milestone2/beta-2.png "beta-2")
#### beta-3
![Alt Text](milestone2/beta-3.png "beta-3")
#### gamma-0
![Alt Text](milestone2/gamma-0.png "gamma-0")
#### gamma-1
![Alt Text](milestone2/gamma-1.png "gamma-1")
#### delta-0
![Alt Text](milestone2/delta-0.png "delta-0")
#### delta-1
![Alt Text](milestone2/delta-1.png "delta-1")
#### delta-2
![Alt Text](milestone2/delta-2.png "delta-2")
#### delta-3
![Alt Text](milestone2/delta-3.png "delta-3")
#### delta-4
![Alt Text](milestone2/delta-4.png "delta-4")



## Router
* Router role:
Edge routing and DHCP relay
* WAN interface configuration: 
Static IP: 172.16.40.21/21
Gateway: 172.16.40.1
DNS: Temporarily using 8.8.8.8
* Internal interface configurations:
![Alt text](milestone2/vlans.png "VLAN configurations")
See routing table below.
* Routing protocol setup:
N/A

* NAT configuration: 
Port forwarding everything on the WAN port 80 to 192.168.2.2 port 80.  
* Connectivity test evidence:
Pinging externally -
![Alt text](milestone2/alpha1DNS.png "Pinging external")
Route table - 
![Alt text](milestone2/routetablepart1.png "First part of routing table")
![Alt text](milestone2/routetablepart2.png "Second part of routing table")

## Firewall Rules

![Alt text](milestone2/BackupsFirewallRules.png "Backup rules")
![Alt text](milestone2/ExecFirewallRules.png "Executive rules")
![Alt text](milestone2/LANFirewallRules.png "LAN rules")
![Alt text](milestone2/ServersFirewallRules.png "Server rules")
![Alt text](milestone2/WANFirewallRules.png "WAN rules")
![Alt text](milestone2/WorkstationsFirewallRules.png "Workstation rules")

### DNS Resolution

#### VLAN 200
![Alt text](milestone2/alpha1DNS.png "VLAN 200 DNS")
#### VLAN 201
![Alt text](milestone2/alpha5DNS.png "VLAN 201 DNS")
#### VLAN 202
![Alt text](milestone2/beta3DNS.png "VLAN 202 DNS")
#### VLAN 203
![Alt text](milestone2/beta0DNS.png "VLAN 203 DNS")

## Hardware Planning

#### Physical Workstations & Peripherals
* 7 Desktop computers
    * 7 power cables
    * 7 Ethernet cables
    * 8GB RAM, 256GB SSD, Intel Core i5
    * Ethernet NIC
    * Micro Form Factor
    * 4 thumbdrives for OS installers

* 2 Monitors, mice, keyboards
    * 7 Display Port cables
    * 2 power cables
    * 2 1080 monitors
    * 1 KVM
    * 2 USB hubs

#### VM Specifications
* Total RAM: 176
    * alpha-0: 16GB
    * alpha-1: 16GB
    * alpha-2: 32GB
    * alpha-3: 16GB
    * alpha-4: 16GB
    * alpha-5: 16GB
    * beta-0: 16GB
    * beta-1: 16GB
    * beta-2: 16GB
    * beta-3: 16GB
    
* Total CPU Cores: 44
    * alpha-0: 4
    * alpha-1: 4
    * alpha-2: 8
    * alpha-3: 4
    * alpha-4: 4
    * alpha-5: 4
    * beta-0: 4
    * beta-1: 4
    * beta-2: 4
    * beta-3: 4

* Total Storage: 492GB
    * alpha-0: 32GB
    * alpha-1: 20GB
    * alpha-2: 20GB
    * alpha-3: 20GB
    * alpha-4: 100GB
    * alpha-5: 100GB
    * beta-0: 50GB
    * beta-1: 50GB
    * beta-2: 50GB
    * beta-3: 50GB

#### Networking 
* 48 port switch with 2 PSUs
* Console cable
* 9 ethernet cables
* Switch and cable assignments:

    |   Switch Port |   Destination    |
    |-----|-----|
    |   1,2             |   Proxmox Switch  | 
    |   37  |   delta-6 |
    |   38  |   gamma-1 |
    |   39  |   delta-0 |
    |   40  |   delta-1 |
    |   41  |   delta-2 |
    |   42  |   delta-3 |
    |   43  |   delta-4 |

#### Backup
* Main backup server is alpha-5
* Future plans for off-site backup

#### VM Tagging and Pooling Strategy
* Descriptive, role based tags: dhcp, firewall, router, vpn, backup-server, dns, web-server, active-directory, db-server, metric-server, siem, vulnerability-scanner, file-server, workstation
* 2 pools: Servers-alpha & Workstations-beta

## Assumptions & Justifications

### VLANs
* See above table for assumptions based on who is using what VLAN

### Firewall Rules
* Executives should have access to all everything
* Backup (VLAN 201) should have access to everything
* Workstations should be able to access file server
* Servers should be able to reach Executives and Workstations
