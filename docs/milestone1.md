### Technologies & Software


Choose the technologies & software that you will use. Several technologies you may want to consider include:


1. **Router** (OPNSense)
1. **Firewall** (OPNSense)
1. **DNS** (BIND)
1. **IDS/IPS/SIEM** (Wazuh)
1. **Web Server** (Apache)
1. **VPN** (OPNSense)
1. **File Server** (TrueNAS)
1. **Database** (MySQL)
1. **Backup and Restore Solution** (Duplicati)
1. **DHCP Server** (OPNSense)
1. **Metric Server** (Node exporter, Prometheus, Grafana)



### Network Diagram
![Alt text](physical_network.png "a title")
![Alt text](logical_network.png "a title")

We wanted to provide seperate network switches for the VMs and the physical workstations. The VLANs are based on use cases such as servers, IT and Execs, and regualr employees. 



### Disaster Recovery
* We will do daily incremental backups onsite
* We will do weekly differentialy backups onsite and offsite
* We will do monthly full backups onsite and offsite
* We will do weekly VM snapshots onsite and offsite
* We have a backup AD, 



### Hardware Planning

#### Physical Workstations & Peripherals
* 7 Desktop computers
    * 7 power cables
    * Minimum 8GB RAM, 256GB SSD, i5/Ryzen 5
    * Must have ethernet NIC
    * MFF if possible

* 7 Monitors, mice, keyboards
    * 7 Display Port cables
    * 7 power cables
    * 1080 or higher resolution
    * (For the sake of the class, we will be using KVMs and less monitors, mice, and keyboards. Number will depend on availiable KVM solution)

#### VM Specifications
* Total RAM: 64
    * 4 workstations: 4GB each
    * Linux1: 8GB
    * Linux2: 16GB
    * Linux3: 8GB
    * Win1: 8GB
    * Win2: 8GB
* Total CPU Cores: 24
    * 4 workstations: 2 each
    * Linux1: 2
    * Linux2: 6
    * Linux3: 2
    * Win1: 2
    * Win2: 4
* Total Storage: 1.5TB
    * 4 workstations: 64GB each
    * Linux1: 64GB
    * Linux2: 128GB
    * Linux3: 64GB
    * Win1: 128GB
    * Win2: 1TB


NOT DONE YET...

List all Physical Workstations & Peripherals.
Total RAM, CPU, and storage needed for all VMs.
Switches, routers, access points, and patch cables.
On-site backup storage capacity and redundancy.
Plan for offsite backup if required for compliance or disaster recovery.

Other like thumb drives for installers, our own laptops for interfacing?




Physical Workstations & Peripherals:
Include monitors, keyboard/mouse, power, and network cables.
Ensure cables are properly terminated and tested.
VM Host Resources:
Total RAM, CPU, and storage needed for all VMs.
Include overhead for snapshots, backups, and monitoring.
Adjust according to available server resources.
Networking Hardware:
Switches, routers, access points, and patch cables.
Ensure proper VLAN configuration and separation of management traffic.
Include labeling for ports and cable runs for maintainability.
Backup and Recovery Hardware:
On-site backup storage capacity and redundancy.
Plan for offsite backup if required for compliance or disaster recovery.

add ethernet cables