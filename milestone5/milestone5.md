# Milestone 5

## Backup Policy

#### Data retention

Basic configurations will be kept indefinitely in case a system needs to be rebuilt quickly. Financial data will be kept for varying amounts of time. Tax data will be kept for at least seven years to ensure our ability to comply with IRS auditing of the last three years. Data such as bank statements will be kept for one year.   

#### Frequency of backups

Full backups will be made once every six months. Incremental backups will be made once each month. Differential backups will be made once each week. Critical servers and databases will be backed up no less than twice per month. Workstations will be backed up no less than once per month. 

#### Backup Types, Storage Media, and Off-Site Backups

We have an NAS on a physical machine that will act as our on-site backup. Our file server is also a NAS, however, it is hosted on a virutal machine. The active system, on-site, and off-site backups ensure that we have three copies of our system for redundancy. 

#### Encryption and Security 

To ensure the security of backup files at rest, we will use cryptography and asynchronous encryption. The encryption keys will be stored separately from the data at rest. Crypto-shredding will be used at the end of a hardware cycle to ensure that old keys are no longer usable. Executives and the IT manager will be the only users with access to the backup, whether in transit or at rest.


#### Testing and Verification

 The organization will perform periodic test restores on a scheduled basis to confirm the integrity, completeness, and functionality of backup data. These tests will include both file-level and system-level restorations, depending on the criticality of the workload. All test restore activities must be documented, including the date of the test, systems involved, results, and any remediation required. Repeated test failures must be escalated to leadership and addressed through root-cause analysis.

#### Backup Automation

Wherever feasible, backup processes will be automated using enterprise backup platforms, scripts, orchestration tools, or system-native scheduling utilities. Automation reduces human error and ensures consistency across all protected systems. Backup logs will be automatically generated and retained, and responsible personnel must review these logs on a defined schedule (e.g., daily for production systems). Any anomalies, failures, or irregularities detected during log reviews must be remediated promptly.

#### Monitoring and Alerts

The backup environment must be continuously monitored to provide real-time or near-real-time visibility into the success or failure of backup operations. Automated alerts will be configured to notify administrators of completion statuses, errors, missed backups, or backup infrastructure failures. Audit trails documenting all backup activities, administrative actions, and system events will be maintained in accordance with the organization's security and compliance requirements. These audit trails must remain tamper-evident and readily accessible for internal or external review.

#### Documentation and Review

Complete and accurate documentation is critical to maintain clarity and governance over the backup program. Documentation will include backup schedules, data classification tiers, storage repositories, encryption implementations, retention periods, and restoration procedures. This documentation will be reviewed and updated on a recurring basis or whenever significant changes occur in infrastructure, applications, regulatory requirements, or business processes. All updates must be version-controlled and approved by designated stakeholders.

#### Scalability and Growth

IT teams will regularly review storage capacity, network throughput, and backup window performance to ensure that the backup environment remains efficient and scalable. As business data increases or new systems are introduced, the organization will expand storage capacity, adjust backup schedules, or upgrade hardware/software as required.

#### Compliance and Regulatory Requirements

All backup, recovery, and data-handling processes at Spicy Cluck Co. must comply with applicable regulatory and industry requirements, including the General Data Protection Regulation (GDPR) for EU operations and U.S. state privacy laws such as the Utah Consumer Privacy Act (UCPA) and the California Consumer Privacy Act (CCPA/CPRA), ensuring that personal data in backups is encrypted, access-controlled, retained only as necessary, and handled in accordance with regional data-protection rules; if payment card information is processed through the company’s website or retail systems, backup and logging activities must also meet PCI DSS requirements by preventing unnecessary storage of cardholder data and enforcing segmentation, encryption, and monitoring; and, to strengthen overall compliance readiness, the organization will align its practices with recognized security frameworks such as the NIST Cybersecurity Framework, CIS Benchmarks, and ISO 27001, ensuring secure configurations, proper auditing, retention management, and resilience across all systems involved in data storage, monitoring, and recovery.

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
Spicy Cluck Co. will maintain a comprehensive and continuously updated inventory of all hardware and software assets that support business operations. This inventory includes servers, networking devices, workstations, operating systems, licensed applications, configuration details, and vendor support information. To ensure rapid restoration during a disaster, compatible replacement hardware will either be maintained in stock or made quickly accessible through pre-arranged vendor agreements. Inventory records will be reviewed regularly to ensure accuracy and alignment with current system configurations.

#### Network Infrastructure
Spicy Cluck Co. will maintain detailed documentation describing the organization’s network architecture. This documentation includes network topology diagrams, VPN access configurations, firewall rules, routing tables, and VLAN assignments. Disaster recovery procedures will outline the specific actions required to restore secure network connectivity, validate segmentation, reapply firewall rules, and re-establish remote access services. These procedures will be tested on a recurring basis to ensure network recovery steps can be executed efficiently and without errors.

#### Application Recovery Procedures
Each critical application will have clearly defined recovery procedures that describe installation requirements, dependencies, configuration settings, storage locations, and the necessary steps to restore application data. These procedures will also describe how to verify that a restored application is operating correctly. Applications will be prioritized based on business impact and the organization’s recovery objectives. High-impact applications must have thoroughly validated and repeatable recovery processes capable of meeting Spicy Cluck Co.’s required RTO and RPO thresholds.

#### Testing and Maintenance
Spicy Cluck Co. will conduct scheduled disaster recovery exercises to validate readiness, confirm the accuracy of recovery documentation, and identify any weaknesses in existing procedures. These exercises may include tabletop scenario walkthroughs, partial restoration tests, or full recovery simulations depending on system criticality. All test results will be documented, including successes, failures, delays, and remediation activities. Lessons learned from each exercise will be used to update and improve the disaster recovery plan, ensuring continuous refinement and operational resilience.

#### Training and Awareness
Personnel assigned disaster recovery responsibilities will receive structured training to ensure they understand their roles and are capable of performing required tasks during an incident. New team members will receive disaster recovery training during onboarding, and all relevant staff will participate in periodic refresher sessions to ensure retained proficiency. Training programs will include an overview of recovery procedures, communication expectations, escalation paths, and hands-on participation in scheduled drills whenever appropriate. Spicy Cluck Co. requires all DR participants to demonstrate competency in their assigned responsibilities.

#### Vendor and Supplier Contingency Plans
Spicy Cluck Co. will verify that all critical vendors maintain sufficient disaster recovery capabilities to meet operational requirements. This includes reviewing vendor service-level agreements, confirming contractual recovery expectations, documenting emergency contact information, and ensuring that escalation paths are clearly defined. When necessary, alternative suppliers will be identified to maintain operational consistency in the event of a vendor failure or an excessive outage. Vendor DR capabilities will be reassessed periodically to make sure they are in alignment with organizational needs.

#### Financial and Legal Considerations
The Disaster Recovery Plan for Spicy Cluck Co. incorporates all relevant financial, legal, and regulatory obligations associated with business disruptions, data loss, or extended outages. This includes identifying compliance requirements such as the California Consumer Privacy Act (CCPA/CPRA), the Utah Consumer Privacy Act (UCPA), and data-protection requirements enforced by the Federal Trade Commission (FTC), as well as documenting insurance coverage for cyber incidents, data breaches, and business interruption scenarios. Financial impact assessments will be performed periodically to evaluate potential risks and ensure adequate insurance and resource planning. All recovery efforts must adhere to applicable regulatory and legal standards, and documentation must be maintained to demonstrate compliance during audits or investigations.

#### Emergency Response Procedures
    - Define immediate actions to take during incidents (power failure, cyberattack, natural disaster)
#### Incident Reporting and Escalation
    - Establish reporting channels and escalation steps for serious incidents
#### Communication Plan
    - Outline internal and external communication strategies
    - Ensure stakeholders are informed throughout recovery
#### Post-Recovery Evaluation
    - Conduct a review after disaster events or drills
    - Identify lessons learned and update policies accordingly    
