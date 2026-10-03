# Week 6 – Day 5: Defender for Cloud Storage Network Remediation

## Objective

The objective of this lab was to remediate a Microsoft Defender for Cloud recommendation related to Azure Storage network access, test the change, and verify that authorized and unauthorized sources were handled correctly.

The recommendation focused on restricting network access to the storage account using virtual network rules instead of relying broadly on public IP-based filtering.

## Recommendation Selected
Storage accounts should restrict network access using virtual network rules.

Affected Resource:
Homelabstorage-01

Security Concern:
The recommendation identified the use of IP-based filtering as a potential security concern and recommended using virtual network rules as a preferred method for restricting access.

Microsoft explains that virtual network rules can be used to restrict storage access to approved virtual networks and subnets.

## Analyst Questions and Answers

- 1. Which Defender for Cloud recommendation did you remediate?

I remediated the recommendation:

Storage accounts should restrict network access using virtual network rules.

- 2. Which Azure resource was affected?

The affected resource was:

Homelabstorage-01

- 3. What security problem did the recommendation identify?

The recommendation was related to network access to the storage account and the use of IP-based filtering.

Restricting access to approved networks helps reduce unnecessary public network exposure and limits which sources can reach the storage account. Microsoft recommends virtual network rules as a preferred method for this recommendation.

- 4. What remediation did Defender for Cloud recommend?

Defender for Cloud recommended restricting network access by using virtual network rules and limiting access to approved network sources.

- 5. Why does this remediation improve security?

This remediation improves security by limiting access to Homelabstorage-01 to approved network sources instead of allowing broad access.

Restricting network access reduces the potential attack surface and helps protect storage resources from unauthorized access.

- 6. What potential impact could the remediation have on the resource?

The change could prevent legitimate administrators, applications, or users from accessing the storage account if their network source is not included in the allowed configuration.

Microsoft also warns that changing storage network rules can affect an application's ability to connect to the storage account.

- 7. What did you do before applying the change?

Before applying the change, I researched the remediation and made sure I understood its purpose and potential impact.

I also considered whether the change was consistent with organizational security policies and whether it could cause downtime or interrupt access to the storage resource.

- 8. How did you test the resource after remediation?

I tested access from two different IP addresses.

One IP address was allowed, while the other IP address was not authorized.

The unauthorized IP address was unable to access the storage resource.

- 9. Did the resource continue working after the change?
Yes.

The storage resource continued to work for the allowed source, while access from the unauthorized source was blocked.

This demonstrated that the network restriction was working as expected.

- 10. Did Defender for Cloud recognize the remediation?

Immediately after performing the change, Defender for Cloud had not yet updated the recommendation.

I considered this potentially a timing issue because Defender for Cloud processes recommendation and Secure Score information separately. Microsoft states that recommendation status can take several minutes to update after remediation.

- 11. Did your Secure Score change?
Yes.
My Secure Score changed from:
Previous score: 18%
to:
Current score: 42%
However, I cannot attribute the entire increase from 18% to 42% to this single storage-network remediation.
Defender for Cloud calculates Secure Score using security controls and their associated recommendations, so multiple changes or evaluation updates can affect the overall score.

- 12. What did you learn about safely remediating security recommendations?

I learned that it is important to research and understand a remediation before applying it to a production environment.
A security change should be evaluated for its potential effect on users, applications, network access, and resource availability. Testing the change before applying it broadly can help identify problems and prevent unnecessary service disruption.

## Technical Validation

The remediation was tested using two different IP addresses:

- Test                    - Result
                  
- Authorized IP address   - Access allowed          
- Unauthorized IP address - Access denied           
- Storage resource        - Continued to function   
- Defender recommendation - Not immediately updated 
- Previous Secure Score   - 18%                     
- Current Secure Score    - 42%                     


## Key Takeaways

- Azure Storage network access should be restricted to approved sources.
- Microsoft recommends virtual network rules as a preferred method for this Defender for Cloud recommendation.
- Network restrictions can reduce the attack surface of storage resources.
- Security changes can unintentionally block legitimate users or applications.
- Testing from both an authorized and unauthorized source helped verify the network restriction.
- Defender for Cloud recommendations may not update immediately after remediation.
- Secure Score can change as security controls and recommendations are evaluated.
- A Secure Score increase should not automatically be attributed to one remediation without verifying the underlying score changes.

## Lab Result
This lab helped me understand how network restrictions can protect Azure Storage resources. I also learned the importance of validating security changes from both authorized and unauthorized sources and reviewing the potential impact before applying similar changes to production resources.

