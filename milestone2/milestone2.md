# Milestone 2

## Updates Only

## Network Design
### Physical Diagram
![Alt text](physical_network.png "Physical Diagram")
### Logical Diagram
![Alt text](logical_network.png "Logical Diagram")

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



## Router

## Firewall Rules

### DNS Resolution

![Alt text](milestone2/alpha1DNS.png "VLAN 200 DNS")
![Alt text](milestone2/alpha5DNS.png "VLAN 201 DNS")
![Alt text](milestone2/beta3DNS.png "VLAN 202 DNS")
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

* Total Storage: XXXXXXXXXXX
    * 4 workstations: 64GB each
    * Linux1: 64GB
    * Linux2: 128GB
    * Linux3: 64GB
    * Win1: 128GB
    * Win2: 1TB
    * Additional storage: 512GB

#### Networking 
* 1 gigabit switch with minimum 12 ports
* 15 ethernet cables
* Label maker or tape & pen

#### Backup
* Main backup server is Win2 as noted above
* 1 Server or larger desktop with high drive capacity
* Offsite backup (another location in CSRL, but connected over WAN)

#### VM Tagging and Pooling Strategy

## Assumptions & Justifications
