## Microsoft Defender for Cloud – Security Posture Assessment

### Lab Objective

The objective of this lab was to perform a baseline security posture assessment of the Azure environment using Microsoft Defender for Cloud. The assessment focused on reviewing the current Secure Score, security recommendations, security alerts, attack paths, affected resources, and available remediation options.

The purpose of a security posture assessment is to help an administrator understand where the security of cloud resources currently stands compared with the organization's security baseline.

## Azure Environment

| Resource                  | Value               |
| ------------------------- | ------------------- |
| Resource Group            | Homelab-RG        |
| Virtual Machine           | Homelab-VM01      |
| Storage Account           | homelabstorage-01 |
| Secure Score              | 38%             |
| Remaining Recommendations | 17              |
| Security Alerts           | 0               |
| Attack Paths              | 0               |

The 17 remaining recommendations affected different parts of the Azure environment, including the Azure subscription, Homelab-VM01, and homelabstorage-01.

# Security Posture Assessment

### 1. Purpose of a Security Posture Assessment

A security posture assessment helps an administrator understand where the security of cloud resources stands compared with the established security baseline.

It allows administrators to identify security weaknesses and determine which issues may require further investigation or remediation.

### 2. Current Secure Score

The current Secure Score was: 38%

The Secure Score provides an overall view of identified security findings. Microsoft describes the score as an aggregated measure of security findings, where a higher score represents a lower identified risk level.

### 3. Remaining Recommendations

There were 17 recommendations

The recommendations affected the Azure subscription, Homelab-VM01, and homelabstorage-01.

Recommendations provide specific guidance for improving the security posture of affected resources. Microsoft recommends reviewing the details of a recommendation before resolving it.

### 4. Security Alerts

There were no active security alerts in the environment at the time of the assessment.

### 5. Attack Paths

There were no attack paths identified in this lab.

# Highest-Priority Recommendation Reviewed

The recommendation selected for further investigation was:

Microsoft Defender for Resource Manager should be enabled on the Azure subscription.

This recommendation affects the Azure subscription rather than a specific virtual machine or storage account.

## Risk

The primary concern is reduced visibility into suspicious resource-management activity if the Defender for Resource Manager plan is not enabled.

Microsoft Defender for Resource Manager monitors resource-management operations performed through the Azure portal, Azure REST APIs, Azure CLI, and other programmatic clients. It uses security analytics to detect suspicious activity and generate alerts.

If the recommendation is ignored, the administrator would have less security monitoring and detection capability for suspicious resource-management operations covered by this plan.

## Internet Exposure

There were no resources identified as exposed to the Internet during this assessment.

## Attack Path

There was no attack path associated with this recommendation.

# Recommended Remediation

Defender for Cloud recommended enabling the Microsoft Defender for Resource Manager plan.

Microsoft's documented process is:

Microsoft Defender for Cloud → Environment settings → Select subscription → Defender plans → Resource Manager → On → Save

The Resource Manager plan provides monitoring of resource-management operations and security analytics for suspicious activity.

# Remediation Decision

### Decision: DEFER

I decided to defer the remediation.

The primary reason was the cost of upgrading/enabling the additional Defender capability within the available lab budget.

This was an important part of the assessment because a security recommendation should not automatically be enabled without considering cost, organizational requirements, and the value of the additional protection.

Microsoft documents that Defender for Cloud plans have different pricing structures, so cost should be considered when enabling additional protection plans.

# Potential Impact

If the recommendation remains unaddressed, the environment will not receive the additional monitoring and threat-detection capabilities provided by Defender for Resource Manager.

If the plan is enabled, administrators may receive additional security alerts related to suspicious resource-management activity. These alerts would need to be reviewed and investigated appropriately rather than automatically treated as confirmed attacks.

Microsoft documents examples of Resource Manager detections involving suspicious resource creation activity, demonstrating the type of activity this protection can help identify.

# Analyst Decision

| Assessment Area            | Result                                    |
| -------------------------- | ----------------------------------------- |
| Secure Score               | 38%                                       |
| Recommendations            | 17                                        |
| Security Alerts            | 0                                         |
| Attack Paths               | 0                                         |
| Internet-Exposed Resources | None identified                           |
| Selected Recommendation    | Enable Defender for Resource Manager      |
| Decision                   | Defer                                 |
| Reason                     | Additional cost / available lab resources |

The recommendation was deferred rather than ignored. The issue was identified, investigated, and documented for possible future remediation.

# What I Learned

Today I learned that Defender for Cloud provides additional security capabilities that can help administrators monitor and secure Azure environments.

I also learned that security recommendations do not always need to be remediated immediately. An administrator should first understand the purpose of the recommendation, the security benefit, the affected resources, possible operational impact, and cost.

I also learned about additional Defender capabilities, including Microsoft Defender for Servers, that can provide additional monitoring and protection for workloads.

# Errors and Challenges

No errors were encountered during this lab.

The main decision point was determining whether the additional Defender capability should be enabled. Because of the additional cost involved, I decided to defer the recommendation rather than enable it without considering the budget.

# Security Analyst Takeaway

This lab reinforced the importance of making security decisions based on risk, business impact, available resources, and cost.

A security administrator should not simply enable every available security feature. The administrator should understand what each feature protects, determine whether the protection is needed, and then make an informed decision about remediation.

Status: Completed – No errors encountered

