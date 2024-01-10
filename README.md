# Incident Response Documentation on Findings: Security Analyst

<p align="center">
<img src="https://i.imgur.com/PlfjJKH.png" height="80%" width="80%" alt="9"/><br />

## Introduction
Throughout the Azure HoneyNet simulation, I assumed the role of Cyber Incident Responder within my Security Operations Center (SOC), conscientiously examining and addressing four security incidents. This document serves as a recapitulation of my educational journey, illustrating the success of the incident response protocols I implemented to counteract potential threats.

## Scope
The document comprises overviews, evaluations of consequences, responsive measures, and categorizations (if relevant) for the incidents listed below:
- Incident ID: 29 - Brute Force ATTEMPT - Windows
- Incident ID: 10 - Possible Privilege Escalation (Azure Key Vault Critical Credential Retrieval or Update)
- Incident ID: 82 - Brute Force ATTEMPT - Linux Syslog
- Incident ID: 9 - Malware Detected



## Incident ID: 29 - Brute Force ATTEMPT - Windows

<p align="center">
<img src="https://imgur.com/umCFfK8.png" height="80%" width="80%" alt="9"/><br />
  <p align="center">
<img src="https://imgur.com/WqIQn0e.png" height="30%" width="30%" alt="9"/><br />

**Incident Summary**

On January 6, 2024, at 11:25:48 UTC, Azure Sentinel detected a brute force attack attempt on a Windows system named "windows-vm01". The attacker, identified as IP address 14.192.144.254, made around 15,000 login attempts with no success. The incident suggests a deliberate attempt to gain unauthorized access and elevate privileges on the targeted system.

**Impact Assessment**

The occurrence has been categorized as a verified security breach because of the substantial volume of brute force login attempts and the activation of multiple alerts.

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


## Incident ID: 10 - Possible Privilege Escalation (Azure Key Vault Critical Credential Retrieval or Update) 
<p align="center">
<img src="https://imgur.com/74NTNSs.png" height="70%" width="70%" alt="9"/><br />

**Incident Summary**

On January 5, 2024 at 23:13:41 UTC, Azure Sentinel identified a potential privilege escalation incident linked to the retrieval or modification of Azure Key Vault credentials. "Josh Smith" was implicated in numerous occurrences of accessing crucial credentials and was additionally linked to other incidents, including an unusually high number of password resets and assignments to global admin roles.

**Impact Assessment**

Given that this was a simulated scenario intended for testing and educational purposes, no real impact took place. Nevertheless, the incident raises apprehensions regarding potential privilege escalation and unauthorized access to sensitive information.

**Recommendations**

1. Investigate User's access to the Azure Key Vault and other sensitive resources to determine if any unauthorized access occurred.
2. Review and update access control policies to prevent similar incidents in the future.
3. Consider resetting critical credentials and rotating them frequently to limit potential damage in case of a real compromise.
4. Monitor User's activity closely and revoke their access to sensitive resources if necessary.

**Classification**

This incident is classified as a potential privilege escalation incident according to the NIST 800-61 framework. The severity of the incident will depend on the level of access obtained by the user and the sensitivity of the information accessed.

## Incident ID: 82 - Brute Force ATTEMPT - Linux Syslog
<p align="center">
<img src="https://imgur.com/9jD6v1h.png" height="70%" width="70%" alt="9"/><br />

**Incident Summary**

On January 6, 2023, at 20:55:35 UTC, Azure Sentinel detected a brute force attack attempt on a Linux system with IP address 61.177.172.160. This IP address has been involved in several incidents, triggering multiple alerts.

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

## Incident ID: 9 - Malware Detected

**Incident Summary**

On January 5, 2024, at 18:05:12 UTC, Malware was detected on workstation “windows-vm01”, potentially compromising the confidentiality, integrity, availability of the system and data.

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
