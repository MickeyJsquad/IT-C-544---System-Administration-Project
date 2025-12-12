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

Spicy Cluck Co. integrates its backup strategy directly into all disaster recovery procedures to ensure that critical systems and data can be restored quickly and accurately following a disruption. Restoring systems from backups helps meet company Recovery Point Objectives (RPO) and Recovery Time Objectives (RTO) more efficiently. RPOs and RTOs are assigned based on priority of mission-critical systems. Mission-critical services require an RTO of 1–4 hours and an RPO of 15 minutes to one hour, ensuring minimal disruption and data loss. Important business systems target an RTO of 4–12 hours and an RPO of 4–12 hours, while non-critical systems have an RTO of 24–72 hours and an RPO of up to 24 hours.

#### Regular Review and Testing

Spicy Cluck Co. conducts periodic reviews of the Backup Policy to ensure ongoing alignment with operational requirements, technological changes, and regulatory compliance. The policy is reviewed annually, with additional reviews triggered by significant infrastructure changes, audit findings, or updates to business continuity requirements. In conjunction with these reviews, the IT department performs structured simulation tests, such as file-level restores and full system recoveries each quarter to validate the accuracy, integrity, and reliability of backup and recovery procedures. Test results are documented and used to refine backup schedules and configurations. 

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
Immediate response to an emergency depends on the nature of the incident, though in all cases employees must report incidents up through established reporting channels. In case of power failure, staff must ensure the safe shutdown of nonessential systems and confirm that critical infrastructure transitions to UPS or generator power. In case of cyberattack, the IT department will immediately isolate affected systems from the network and preserves relevant logs for forensic analysis. In case of natural disaster, employees must prioritize their own safety by immediately evacuating and taking shelter in a secure location. 

#### Incident Reporting and Escalation
Spicy Cluck Co. maintains clearly defined reporting channels to ensure that serious incidents are communicated promptly and escalated to the appropriate authorities for coordinated response. All employees must report suspected or confirmed incidents up through their direct supervisor. Incidents relating to power failure or cyberattack must be reported to the IT department as well. Natural disaster emergencies must also be reported to Emergency Dispatch. IT employees or emergency dispatch responders assesses severity and classifies the incident according to established impact levels. Depending on scope and regulatory requirements, external parties such as cloud service providers or regulatory bodies may also be engaged. Escalation steps must be documented at each stage to ensure traceability, enable timely decision-making, and support activation of the disaster recovery procedures if warranted.

#### Communication Plan
The company maintains a structured communication plan to ensure that all internal and external stakeholders receive timely, accurate, and consistent information throughout a disruptive incident and the subsequent recovery process. Internally, department supervisors relay communication between their respective departments and the executive leadership. These communications provide status updates, action items, service availability information, and expected timelines for restoration. Externally, Spicy Cluck Co. will communicate with customers, vendors, regulatory bodies, cloud and service providers, and other relevant third parties through authorized representatives designated by the executive leadership. All messaging is aligned to prevent misinformation and to maintain compliance with contractual, and regulatory obligations. Communication continues at regular intervals for the duration of the incident, ensuring that stakeholders remain informed of progress, recovery milestones, and the eventual return to normal operations.

#### Post-Recovery Evaluation
Spicy Cluck Co. is committed to improving its recovery posture against preventable incidents. Thus after an emergency incident is resolved, the company conducts a formal post-recovery evaluation to assess the effectiveness of recovery procedures, whether RTO and RPO objectives were met, and overall incident management performance of employees. Lessons learned are documented and evaluated by supervisors for each department, then presented to the executive leadership and relevant external stakeholders. Based on these insights, the company updates disaster recovery policies, backup procedures, and response protocols to strengthen future resilience.
