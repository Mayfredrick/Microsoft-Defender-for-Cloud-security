# Week 6 – Day 6: Microsoft Defender for Cloud Security Posture Validation

## Objective

The objective of this lab was to review and validate the overall security posture of my Azure environment after completing several security reviews and remediation activities during Week 6.
The lab focused on reviewing Secure Score, remaining recommendations, previous remediation activities, security alerts, and attack paths.

## Analyst Questions and Answers

### 1. What is your current Secure Score?

My current Microsoft Defender for Cloud Secure Score is: 38%

### 2. How does it compare with the 18% score recorded at the beginning of Week 6?

My Secure Score increased from 18% to 38%.

This represents a 20-percentage-point increase.

However, I cannot conclude that the increase was caused by one specific remediation. Defender for Cloud calculates Secure Score using multiple security controls and recommendations. Microsoft also states that security controls are recalculated every eight hours, while recommendations within a control can update more frequently.

### 3. How many security recommendations remain?

I currently have: 17 recommendations remaining.

These recommendations will require further review to determine which should be remediated, investigated, or monitored.

### 4. Which remaining recommendation do you consider important to investigate next?

One recommendation I would investigate next is: Storage accounts should use a private link connection.

### 5. Why did you select this recommendation?

I selected this recommendation because using a private connection can help reduce public network exposure to Azure resources.

Private Link can provide private connectivity to supported Azure services, which can help reduce exposure through public network access. Defender for Cloud includes Private Link-related recommendations under network security controls.

Before implementing the recommendation, I would investigate the current storage architecture, application dependencies, and organizational requirements.

### 6. Did Defender for Cloud recognize your management-port remediation?
No Defender for Cloud did not recognize my management-port remediation at the time I performed this review.

I would continue monitoring the recommendation because recommendation status and security-control calculations are not necessarily updated at the same time. Microsoft states that recommendation status can take several minutes after remediation, while security controls are calculated every eight hours.

### 7. Did Defender for Cloud recognize your storage-network remediation?
No Defender for Cloud had not recognized my storage-network remediation at the time of this review.

I would continue monitoring the recommendation and verify the configuration independently rather than assuming that the remediation failed.

### 8. How many active security alerts are currently present?
There were 0 active security alerts in my lab environment.

### 9. How many attack paths are currently present?
There were no attack paths present in this lab.

### 10. Which remaining recommendations would you classify as Remediate, Investigate, or Monitor?
Most of the remaining recommendations in my Azure subscription would first be classified as Investigate. I want to understand how each recommendation can improve the security posture, what resources are affected, and whether remediation could affect production resources.
After investigation, individual recommendations can be classified as Remediate or Monitor based on their risk and business impact.

### 11. What security improvements did you make during Week 6?
During this lab, I did not make a new security improvement.
Most of the remaining recommendations require additional investigation, and some security capabilities may require subscription features or licensing that are not available in my current lab environment.
However, earlier in Week 6 I performed security remediation activities involving:
* Management-port restrictions on Homelab-VM01
* Network access restrictions for Homelabstorage-01

I also tested the storage network restriction from authorized and unauthorized IP addresses.

### 12. What did you learn about reviewing and validating cloud security posture?

I learned that reviewing and validating cloud security posture helps administrators investigate security issues more deeply before applying remediation.

It is important to understand the problem, determine the appropriate remediation, evaluate its impact, and verify the result after making a change.

This process helps prevent unnecessary changes and allows security issues to be addressed without unnecessarily affecting resources.

## Week 6 Security Posture Summary

| Item                               | Result                                                |
| ---------------------------------- | -------------------------------------------------- |
| Beginning Secure Score             | 18%                                                   |
| Current Secure Score               | 38%                                                   |
| Score change                       | +20 percentage points                                 |
| Remaining recommendations          | 17                                                    |
| Active security alerts             | 0                                                     |
| Attack paths                       | Not recorded in this review                           |
| Management-port remediation        | Not yet recognized by Defender for Cloud              |
| Storage-network remediation        | Not yet recognized by Defender for Cloud              |
| Next recommendation to investigate | Storage accounts should use a private link connection |

## Key Takeaways

* Secure Score provides an overall view of cloud security posture.
* My Secure Score increased from **18% to 38%** during Week 6.
* I currently have **17 recommendations** remaining.
* A change in Secure Score should not automatically be attributed to one remediation.
* Defender for Cloud security controls and individual recommendations can update on different schedules.
* There were no active security alerts in my lab environment.
* Remaining recommendations should be investigated before remediation.
* Private Link can help reduce public network exposure for supported Azure services.
* Security validation is important because a remediation should be verified rather than assumed to be successful.
* Some Defender for Cloud capabilities depend on the subscription, configuration, or available licensing.

## Lab Result
This lab helped me understand that cloud security is an ongoing process. Reviewing recommendations, validating remediation, monitoring Secure Score, and investigating remaining issues are important parts of maintaining a secure cloud environment.

