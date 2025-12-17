# Milestone 6

## Introduction

## Asset Inventory
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
* Main backup server is alpha-

    --more here? if not delete--

#### VM Tagging and Pooling Strategy
* Descriptive, role based tags: dhcp, firewall, router, vpn, backup-server, dns, web-server, active-directory, db-server, metric-server, siem, vulnerability-scanner, file-server, workstation
* 2 pools: Servers-alpha & Workstations-beta

## Software Inventory
* **Router:** OPNSense
* **Firewall:** OPNSense
* **DNS:** BIND
* **SIEM & Endpoint Protection:** Wazuh
* **Vulnerability Scanning:** Nessus
* **Web Server:** Apache
* **VPN:** OPNSense
* **File Server:** TrueNAS
* **Database:** MySQL
* **Backup and Restore Solution:** Duplicati
* **DHCP Server:** OPNSense
* **Directory and Authentication:** Active Directory
* **Operating Systems:** Ubuntu, Kali Purple, Debian, Fedora, Windows Pro, Windows Server, TruNAS
* **Browser:** Chrome, Edge, Firefox
* **Code Editor:** VS Code

--more here? eg did we install office anywhere (or "plan to.") if not delete--


## Network Diagrams
Physical network diagram
![physical network diagram](m6_screenshots/diagrams/physical_network.png)
Logical network diagram
![logical network diagram](m6_screenshots/diagrams/logical_network.png)

## Network Tables

## Firewall Rules
The reasoning behind our firewall rules is relatively simple. The network requires access to the internet at large, meaning we need to have ports 80, 443, 123, and 53 allowed for HTTP, HTTPS, NTP, and DNS respectively. Each machine within the system must also have access to Active Directory, requiring the inclusion of ports 88, 636, and 135 for Kerberos, Encrypted LDAP, and RPC, respectively. Each VLAN has rules allowing it a certain amount of access to other VLANs. Executives, for example, are given access to all other VLANs because of their role. Additional ports to allow traffic for the File Server were added, specifically ports 137-139 and 445. We also allowed inbound traffic on ports 1514 and 1515 for our SIEM. These ports are necessary for TrueNAS to function as intended. Each of these ports was allowed for each VLAN, and no other rules were added so that the principle of least privilege was followed as closely as possible.

Each VLAN in our system allows ports needed for basic internet access as well as access to the file server and the SIEM. However, we have also implemented a deny-by-default rule to follow secuirty best practice and to enforce least privilege access. Each VLAN can only access what is absolutely necessary, and no more.

All firewall rules can be viewed in [this config file](config.xml).

## DNS Configuration

The DNS server is configured on alpha-1 which runs BIND9 on an Ubuntu Server and has the IP Address 192.168.2.2. The Domain Controller is set as the authoritative server for the domain "sysadmin.local" whereas the DNS server is set as the primary DNS that forwards any local domain requests to the DC. The DNS server also forwards all external domain resolution to the IP addresses 1.1.1.1 and 8.8.8.8. 


The records on the DC including manually added ones and hostnames from devices connected to the domain.
![Records on the DC](m6_screenshots/DNS/AD_DNS.png)

The config that forwards all local domain resolution requests to the DC.
![named.conf.local](m6_screenshots/DNS/dns_zones.png)

The config that forwards all external domain resolution to external DNS servers.
![named.conf.options](m6_screenshots/DNS/named.conf.options.png)

The router assigns DNS servers to the devices as it gives DHCP leases. alpha-2 can see what DNS server it is using.
![alpha-2 dns server](m6_screenshots/DNS/alpha-2_dns_server.png)

alpha-2 has no problem resolving the local domain "www.sysadmin.local" and the public domain "google.com" and reaching both.
![alpha-2 pinging local and public domain](m6_screenshots/DNS/alpha-2_pings.png)


## File Server
I can do this - Chris

## Active Directory Integration

## Vulnerability Management

#### Setup and Configuration
We are using Nessus, an easy to install and intuitive vulnerability scanner, to scan the network for vulnerabilities. Nessus can be installed by going to the Downloads page and selecting the right download package for your Operating System. This can also be done via the command line using wget. Then you install the package and let it configure itself and install all of the necessary plugins. Once it is done it will deploy a web interface on port 8834. It will walk you through the steps of creating an admin account. It will eventually bring you to the login page where you can log in with the account you just created.
![Nessus login page](m6_screenshots/nessus/nessus_login.png)

Once logged in and all plugins are installed, you can click the New Scan button in the top right corner to Configure a scan of your machines.

We have a scan of all machines in our Servers VLAN along with the router that is scheduled to scan once a week.
![Nessus scheduled scan](m6_screenshots/nessus/nessus_schedule.png)

#### Scan Results
Here are the results of the scan of our main servers.
![Main Servers Scan](m6_screenshots/nessus/main_servers.png)

Windows Credentialed Scan
![Windows Creds](m6_screenshots/nessus/windows_creds.png)

Linux Credentialed Scan
![Linux Creds](m6_screenshots/nessus/linux_creds.png)

## VPN Access

## Backup & Disaster Recovery Policy


Separate Files to Include:

Switch configuration & VLAN database

DNS server configuration

Database schema in SQL format (wiki database)

Web server configuration

File server configuration:
[TrueNAS Configuration](ALPHA3-25.10.0.1-20251206184633.tar)

AD configuration

Risk assessment

Most recent vulnerability scan reports

VPN server configuration

