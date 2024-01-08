# Incident Response Documentation on Findings
![Sentinal Findings](https://github.com/asuleman-cyber/Security-Incident-Response/assets/43348989/d2fa887b-1f8a-4f62-b80e-de8b0762ecd5)

## Introduction
During the Azure HoneyNet simulation, I acted as the Cyber Incident Responder in my SOC, diligently investigating and responding to four security incidents. This report is a reflection of my learning experience and demonstrates the effectiveness of the incident response procedures I employed to mitigate potential threats.

## Scope
The document includes summaries, impact assessments, response actions, and classifications (where applicable) for the following incidents:

* Incident ID: 125 - Brute Force ATTEMPT - Windows
* Incident ID: 9 - Possible Privilege Escalation (Azure Key Vault Critical Credential Retrieval or Update)
* Incident ID: 101 - Brute Force ATTEMPT - Linux Syslog
* Incident ID: 6 - Malware Detected



## Incident ID: 125 - Brute Force ATTEMPT - Windows

![Brute Force](https://github.com/asuleman-cyber/Security-Incident-Response/assets/43348989/1578131e-bf43-4595-85bb-b8d1b9f1c2a6)
![Brute Force](https://github.com/asuleman-cyber/Security-Incident-Response/assets/43348989/23bd10e0-6a1a-4298-aabf-1934b44a113c)

**Incident Summary**

On May 13, 2023, at 20:36:48 UTC, Azure Sentinel detected a brute force attack attempt on a Windows system named "windows-vm". The attacker, identified as IP address 125.166.23.61, made over 700 login attempts with no success. The incident suggests a deliberate attempt to gain unauthorized access and elevate privileges on the targeted system.

**Impact Assessment**

The incident has been classified as a confirmed security breach due to the large number of brute force login attempts and multiple alerts triggered.

**Initial Response Actions**

1. Verify the authenticity of the alert.
2. Immediately isolate the "windows-vm" system and change the passwords of all affected user accounts.
3. Identify the origin and nature of the attack.
4. Determine the timeframe and method of the attack.
5. Check other Network Security Groups (NSGs) to assess if they are being targeted as well.
6. Conduct a comprehensive review of logs for any other suspicious activities.
7. Review user accounts with elevated privileges and verify the integrity of sensitive data stored on the system.

**Containment and Recovery**

1. Implement temporary network segmentation to prevent the attacker from accessing other systems.
2. Adjust the NSG rules to restrict unnecessary traffic to the "windows-vm" system.
3. Reset the passwords for affected user accounts and enforce strong password policies.
4. Enable multi-factor authentication (MFA) for all user accounts to enhance security.
5. Conduct a full virus scan on the "windows-vm" system to check for malware infections.
6. Monitor the system for any further unusual activity to ensure it remains secure.


## Incident ID: 9 Custom - Possible Privilege Escalation (Azure Key Vault Critical Credential Retrieval or Update) 
![Privilege Escalation](https://github.com/asuleman-cyber/Security-Incident-Response/assets/43348989/4f3f773c-57b2-4fa2-8037-8dd07df44f6b)

**Incident Summary**

On May 13, 2023, at 17:22:15 UTC, Azure Sentinel detected a potential privilege escalation incident related to Azure Key Vault credential retrieval or update. User "Adam Suleman" was involved in multiple instances of accessing critical credentials and was also connected to other incidents involving excessive password resets and global admin role assignments.

**Impact Assessment**

As this was a simulated scenario for testing and educational purposes, no actual impact occurred. However, the incident raises concerns about potential privilege escalation and unauthorized access to sensitive information.

**Recommendations**

1. Investigate User's access to the Azure Key Vault and other sensitive resources to determine if any unauthorized access occurred.
2. Review and update access control policies to prevent similar incidents in the future.
3. Consider resetting critical credentials and rotating them frequently to limit potential damage in case of a real compromise.
4. Monitor User's activity closely and revoke their access to sensitive resources if necessary.

**Classification**

This incident is classified as a potential privilege escalation incident according to the NIST 800-61 framework. The severity of the incident will depend on the level of access obtained by the user and the sensitivity of the information accessed.

## Incident ID: 101 - Brute Force ATTEMPT - Linux Syslog

**Incident Summary**

On May 15, 2023, at 17:55:12 UTC, Azure Sentinel detected a brute force attack attempt on a Linux system with IP address 114.132.168.163. This IP address has been involved in several incidents, triggering multiple alerts.

**Impact Assessment**

The account targeted by the brute force attack was local to the Linux machine.

**Initial Response Actions**

1. Verify the authenticity of the alerts and reports.
2. Reset the password for the compromised user account.
3. Lock down Network Security Groups (NSGs) to prevent further unauthorized access.
4. Investigate other incidents triggered by IP address 114.132.168.163 to assess the scope of the attack.

**Containment and Recovery**

1. Quarantine the infected workstation and any other systems that may have been impacted.
2. Restore the infected workstation to a known clean state.
3. Conduct a thorough review of logs and security measures to prevent similar incidents.

## Incident ID: 6 - Malware Detected

**Incident Summary**

On May 15, 2023, at 18:05:12 UTC, Malware has been detected on a workstation, potentially compromising the confidentiality, integrity, availability of the system and data.

**Initial Response Actions**

1. Verify the authenticity of the alert or report.
2. Identify the primary user account of the affected system, if applicable.
3. Notify affected stakeholders and provide guidance on how to protect themselves.
4. Run a full system scan using an up-to-date antivirus software to identify and remove the malware.
5. If the malware cannot be removed or significant damage is suspected, shut down the workstation and disconnect it from the network.

**Containment and Recovery**

1. Quarantine the infected workstation and any other potentially impacted systems.
2. Restore the workstation to a known clean state through system imaging or clean installation.
3. Strengthen security measures to prevent future malware incidents.
