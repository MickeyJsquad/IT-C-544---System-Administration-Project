# Milestone 4

## File Server Configuration
#### Folder structure and mapping to groups
We are using TrueNAS on a VM in Proxmox for our file server. There is a secondary virtual drive other than the boot drive which has a pool called "general." Under general there are directories mapped to our three groups: executives (exec), IT (it), and Employees (empl). There is an SMB share for each of these directories.


screenshot from web gui...

#### Access rights per folder
The TrueNAS file server is joined to AD for access control. The shares can only be mapped by the appropriate individuals. Additionally, acess can be set as read, change, and full (we do not currently have any that are read-only). Below is the access allowed for each share:

exec
	-Executives: change
	-Alex Patel: full

it
	-IT: full

empl
	-IT: full
	-Executives: change
	-Employees: change


ACL For Executive Share
![ACL For Executive Share](m4_screenshots/smb_acl/exec_acl.PNG)

ACL For IT Share
![ACL For IT Share](m4_screenshots/smb_acl/it_acl.PNG)

ACL For Employee Share
![ACL For Employee Share](m4_screenshots/smb_acl/empl_acl.PNG)

Example: Alex Patel can access all three shares
![Alex Patel can access all three shares](m4_screenshots/smb_proof/alex_has_all_3.PNG)

Example: Ben Anderson can access Employee share but is denied connecting to IT share
![Ben Anderson can access Employee share but is denied connecting to IT share](m4_screenshots/smb_proof/ben_has_empl_but_denied_it.PNG)

#### Backup schedules and locations

!!!!!!!!!!!!!!!!EITHER FILL THIS OUT OR DELETE IT!!!!!!!!!!!!!!!!!11

#### Troubleshooting tips
When using TrueNAS in Proxmox and adding a pool on a virtual drive, you must assign the virtual drive a serial number. This can be done by adding ```serial=<make up a serial>``` to the end of the line in the config file for the drive on the host's shell.

We also had some trouble with joining the TrueNAS server to the domain. This turned out to be due to a time difference between the domain controller and TrueNAS machine. 

## Vulnerability Scanning
* Tool setup and configuration
* Scan results and screenshots
* Risk assessment updates
* Mitigation strategies

## VPN Server
* Iinstallation steps and configuration
* Authentication methods
* Connection instructions for remote users
* Firewall and port forwarding configuration
* Test results and troubleshootign steps

## SIEM & Endpoint Protection
* Deployment steps for SIEM and endpoint tools
* Devicdes monitored and log sources
* Alert rules and examples
* Screenshots of SIEM dashboards and alerts

## Configuration Files
* VPN
* File Server
* SIEM
* Endpoint Protection
