# Milestone 5

## Backup Policy
#### Data retention
    - Define retention periods for different data types (e.g., configurations, financial, marketing, sales, etc.)
    - Ensure retention meets legal, compliance, and operational requirements     

#### Frequency of backups
    - Critical servers and databases
    - Workstations and less critical systems

#### Backup Types
    - Full backups, incremental backups, and differential backups
    - Choose type based on recovery objectives and storage efficiency

#### Storage Media
    - Local disks, NAS, SAN, or cloud storage
    - Ensure redundancy across multiple storage locations

#### Off-site Backups
    - Maintain off-site copies for disaster recovery

#### Encryption and Security 
    - Encrpyt all backup files in transit and at rest
    - Restrict access using role-based access controls


Basic configurations will be kept indefinitely in case a system needs to be rebuilt quickly. Financial data will be kept for varying amounts of time. Tax data will be kept for at least seven years to ensure our ability to comply with IRS auditing of the last three years. Data such as bank statements will be kept for one year.
Full backups will be made once every six months. Incremental backups will be made once each month. Differential backups will be made once each week. Critical servers and databases will be backed up no less than twice per month. Workstations will be backed up no less than once per month. 
We have an NAS on a physical machine that will act as our on-site backup. Our file server is also a NAS, however, it is hosted on a virutal machine. The active system, on-site, and off-site backups ensure that we have three copies of our system for redundancy. 
To ensure the security of backup files at rest, we will use cryptography and asynchronous encryption. The encryption keys will be stored separately from the data at rest. Crypto-shredding will be used at the end of a hardware cycle to ensure that old keys are no longer usable. Executives and the IT manager will be the only users with access to the backup, whether in transit or at rest.


#### Testing and Verification
    - Peridically restore backups to verify integrity and functionality
    - Document the success/failure of test restores
#### Backup Automation
    - Automate backup tasks using scripts or management tools
    - Ensure logs are maintained and reviewed regularly
#### Monitoring and Alerts
    - Generate notifications for backup completion, failures, or errors
   - Maintain audit trails for compliance
#### Documentation and Review
    - Record backup schedules, storage locations, encryption methods, and retention policies
    - Update documentation regularly
#### Scalability and Growth
    - Ensure backup infrastructure can scale with increasing data volume
    - Regularly review storage capacity and upgrade as needed
#### Compliance and Regulatory Requirements
    - Align backups with industry-specific standards (e.g., HIPAA, GDPR, SOX)
#### Disaster Recovery Planning
    - Integrate backups with disaster recovery procedures
    - Define recovery point objectives (RPO) and recovery time objectives (RTO)
#### Regular Review and Testing
    - Schedule periodic reviews of the backup policy
    - Conduct simulation tests to validate procedures 

## Disaster Recovery Policy

#### Risk Assessment and Business Impact Analysis (BIA)

The following systems are critical for operations: DNS, Active Directory, Web Server, and File Server. There are virtually infinite threats to our IT systems. These include attacks on Active Directory which could lead to access to most of our systems. Some other examples would be attacks on the web server such as Denial of Service, Cross Site Scripting, and SQL Injection. Another threat would be unauthorized access to our file server, leading to disclosure of information. In addition, an attacker may target our workstations and servers and then attempt to escalate their privileges giving them access to additional systems and information. These attacks could lead to breaches of confidentiality, integrity, and availability.

#### Recovery Objectives and Priorities
Below are the Recovery Time Objectives (RTO) and Recovery Point Objectives (RPO) for each of our systems:

| System |  RTO | RPO |
|---|---|---|
| DNS Server | 1 Hour | 30 Minutes |
| Active Directory | 1 Hour | 15 Minutes |
| Database Server | 1 Hour | 15 Minutes |
| Web Server | 2 Hours | 30 Minutes |
| File Server | 2 Hours | 15 Minutes |
| Workstations | 4 Hours | 24 Hours |
| VPN Server | 1 Hour | 30 Minutes |
| DHCP Server | 1 Hour | 30 Minutes |
| SIEM Server | 4 Hours | 1 Hour |
| Vulnerability Scanner | 24 Hours | 1 Hour |

#### Roles and Responsibilities
In case of an event requiring recovery, the following individuals constitute the "Disaster Recovery" team and will have specific responsibilities to execute: 

| Name | Responsibility
|---|---|
| Emily Brown | Contact the DR team and coordinate the recovery. Notify Director of Fried Chicken and keep them up to date. |
| Karen Taylor | Notify customers, partners, and the public as needed. |
| Albert Tay | Advise on relevant legal and complience action. |
| Alex Patel | Coordinate with IT staff to restore AD, Database, Web Server, File Server, Workstations, SIEM, Vulnerability Scanner. Document the DR process. |
| Eric Nguyen | Restore network insfrastructure, DNS, DHCP, VPN. |

#### Contact Information
| Name | Contact | Role |
|---|---|---|
| Emily Brown | emilybrown@cluck.com | CTO |
| Albert Tay | alberttat@cluck.com | Director of Fried Chicken |
| Rachel Nguyen | rachelnguyen@cluck.com | HR Manager |
| Alex Patel | alexpatel@cluck.com | IT Manager |
| Karen Taylor | karen.taylor@cluck.com | Customer Service Manager |
| Jessica Rodriguez | jessicarodriguez@cluck.com | Content Writer |
| Ryan Lee | ryanlee@cluck.com | Graphic Designer |
| Ben Anderson | benanderson@cluck.com | Sales Representative |
| Olivia Davis | oliviadavis@cluck.com | Data Analyst |
| Eric Nguyen | ericnguyen@cluck.com | Network Administrator |
| Emergency Dispatch | 911 | Emergency Only |
| OPNSense | https://docs.opnsense.org/support.html | Router, Firewall, VPN, DHCP |
| Wazuh | https://wazuh.com/services/professional-support/ | SIEM |
| Apache | https://httpd.apache.org/support.html | Web Server |
| TrueNAS | https://www.truenas.com/support/ | File Server |
    
#### Data Backup and Restoration Procedures
Backup and Restoration Policies and Procedures can be found in MS2 Backup, MS3 AD & LDAP Setup, MS3 Firewall Rules, MS4 Backup & Recovery Procedures.

#### Disaster Recovery Site
If the Spicy Cluck Co. building is not availiable, the DR team will meet at the BYU Crabtree CSRL. They may use the server room equiptment, networking, and any IT Surplus devices in the room. If laptops are needed for use as workstations, student laptops may be taken. As all used software is free or open source, it may be downloaded from each vendor's site.

#### Hardware and Software Inventory
    - Maintain an inventory of servers, networking devices, workstations, and applications
    - Ensure compatible replacement equipment is available
#### Network Infrastructure
    - Document network topology, VPN access, firewall rules, and routing
    - Include procedures to restore connectivity after an outage
#### Application Recovery Procedures
    - List critical applications and dependencies
    - Provide instructions for reinstalling or restoring application data
#### Testing and Maintenance
    - Conduct scheduled DR drills and tabletop exercises
    - Update DR plans based on test results
#### Training and Awareness
    - Educate staff on their roles during a disaster
    - Conduct periodic refresher training
#### Vendor and Supplier Contingency Plans
    - Ensure third-party vendors have recovery capabilities
    - Include service-level agreements (SLAs) for critical services
#### Financial and Legal Considerations
    - Include insurance, compliance obligations, and potential financial impact
#### Emergency Response Procedures
    - Define immediate actions to take during incidents (power failure, cyberattack, natural disaster)
#### Incident Reporting and Escalation
    - Establish reporting channels and escalation steps for serious incidents
#### Communication Plan
    - Outline internal and external communication strategies
    - Ensure stakeholders are informed throughout recovery
#### Post-Recovery Evaluation
    - Conduct a review after disaster events or drills
#### Identify lessons learned and update policies accordingly    