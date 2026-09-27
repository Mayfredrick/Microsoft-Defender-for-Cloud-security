# Week 6 Day 1 – Microsoft Defender for Cloud Security Posture Review

## Objective

The purpose of this lab was to perform a security posture review of my Azure environment using Microsoft Defender for Cloud. I reviewed the Secure Score, security recommendations, security alerts, and attack paths to identify security issues and determine how they should be investigated and remediated.

## Lab Environment

 Azure Resource Group: Homelab-RG
 Virtual Network: Homelab-VNet
 Subnet: Server-Subnet
 Virtual Machine: Homelab-VM01
 Storage Account: Homelabstorage01
 Security Tool: Microsoft Defender for Cloud
 Platform: Microsoft Azure

## Tasks Completed

During this lab, I:

 Reviewed the Defender for Cloud security posture.
 Checked the Secure Score.
 Reviewed security recommendations.
 Identified affected resources.
 Reviewed security alerts.
 Reviewed attack paths.
 Considered the risks associated with an exposed virtual machine.
 Evaluated the possible impact of remediation before making changes.

## Security Posture Review

The purpose of a security posture review is to help administrators monitor the security condition of their environment and determine whether resources are meeting expected security standards.

I used the Secure Score as one of the indicators of my environment's security posture.

My Secure Score was 18%. This indicated that there were several security improvement areas that required further investigation and remediation.

## Security Recommendation Reviewed

I reviewed a recommendation related to management ports for virtual machines.

The affected resource was:

 Homelab-VM01

The recommendation identified that remote management ports were exposed, which could increase the virtual machine's exposure to Internet-based attacks.

## Security Risk

Open remote management ports can increase the risk of unauthorized access attempts. Attackers could potentially attempt to brute-force credentials to gain access to the virtual machine.

Because Homelab-VM01 is a Windows Server virtual machine, protecting its remote management access is important.

## Recommended Remediation

The recommended remediation was to modify the inbound network security rules and restrict access to specific source IP ranges instead of allowing broad access.

This would reduce the number of systems that can directly reach the remote management service.

## Investigating Before Remediation

Before applying the recommendation, I would investigate which users, administrators, applications, or other resources require access to the virtual machine.

Restricting access to specific source ranges could unintentionally prevent legitimate users or resources from connecting if those sources were not included in the allowed ranges.

This demonstrates why security recommendations should be reviewed before changes are made.

## Security Alerts

There were no security alerts available in my lab environment during this exercise.

I documented the actual state of the environment rather than creating or simulating an alert.

## Attack Paths

There were no attack paths available in my lab environment during this exercise.

## Potential Impact if the Issue Is Ignored

If the exposed management ports remain unrestricted, the virtual machine could face increased exposure to unauthorized access attempts.

If an attacker successfully gained administrative access, the potential impact could include unauthorized access to data, loss of sensitive information, or deployment of malicious software such as ransomware.

## What I Learned

I learned how to look deeper into security recommendations before applying remediation. A recommendation should not simply be applied immediately. I need to understand the affected resource, security risk, possible impact, and access requirements before making a change.

I also learned how Secure Score can help identify areas where an Azure environment needs security improvements.

## Challenges

I did not encounter any errors during this lab.

The main consideration was determining the possible impact of restricting access to the virtual machine before applying the recommended network changes.

## Screenshots
1. Defender for Cloud Secure Score showing 18%
2. Security recommendation for management ports
3. Recommendation details showing Homelab-VM01
4. Remediation instructions
5. Security Alerts page showing no active alerts
6. Attack Paths page showing no attack paths

## Key Takeaways

 Secure Score provides an indication of the security posture of an Azure environment.
 Security recommendations identify areas that require attention.
 Exposed management ports can increase the attack surface of a virtual machine.
 Network access should be restricted to appropriate source ranges when possible.
 Security recommendations should be investigated before remediation.
 Remediation can affect legitimate users or resources if access requirements are not considered.
 Security alerts and attack paths should be reviewed as part of a broader security posture assessment.


