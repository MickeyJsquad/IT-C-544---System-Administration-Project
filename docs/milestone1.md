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