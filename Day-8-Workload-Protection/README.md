# Week 7 – Day 2

## Microsoft Defender for Servers – Workload Protection Assessment

### Lab Objective

The objective of this lab was to investigate Microsoft Defender for Servers and understand how it can help protect Windows and Linux machines across Azure, other cloud environments, and on-premises environments.

The lab focused on comparing Defender for Servers plans, reviewing vulnerability assessment and endpoint protection capabilities, and deciding whether enabling Defender for Servers would be appropriate for the current Azure security baseline.

# Defender for Servers Overview

Microsoft Defender for Servers helps reduce security risks for Windows and Linux machines across hybrid and multicloud environments.

Its purpose is to provide additional security capabilities for servers and machines, including vulnerability assessment, security monitoring, endpoint protection, and other workload protection capabilities.

Defender for Servers can provide capabilities such as vulnerability assessment, configuration assessment, just-in-time machine access, file integrity monitoring, and agentless scanning depending on the selected plan and configuration.

# Lab Results

| Assessment               | Result                                             |
| ------------------------ |
| Defender for Servers     | **Not enabled**                                    |
| Plan 1                   | **Not enabled**                                    |
| Plan 2                   | **Not enabled**                                    |
| Endpoint information     | Not available in current configuration             |
| EDR detected             | **No**                                             |
| Vulnerability assessment | Not confirmed                                      |
| Security alerts          | No additional Defender for Servers alerts observed |
| Final decision           | **Defer**                                          |

# Plan 1 vs. Plan 2

One of the goals of this lab was to understand the difference between the two Defender for Servers plans.

Plan 1 and Plan 2 both provide vulnerability and configuration assessment capabilities, but Plan 2 provides additional capabilities.

Some capabilities available with Plan 2 include:

* Agentless scanning
* Security baseline assessment
* Additional Microsoft Defender Vulnerability Management capabilities
* File Integrity Monitoring
* Additional machine protection capabilities
* Just-in-time machine access

Microsoft documents that vulnerability assessment is supported with both Plan 1 and Plan 2, while additional capabilities are available with Plan 2.

The cost of the plans is also an important consideration when deciding which level of protection is appropriate.

# Vulnerability Assessment

I was not able to confirm whether vulnerability assessment was currently available for `Homelab-VM01`.

I also could not determine whether the vulnerabilities were directly related to the recommendations I was reviewing.

This was an important learning point because **not every Defender for Cloud recommendation represents a software vulnerability**.

Defender for Cloud recommendations can cover different categories, including:

* Misconfigurations
* Vulnerabilities
* Exposed secrets

Microsoft currently provides separate recommendation views for these categories.

For example, a recommendation about an incorrectly configured NSG is a configuration issue, while a recommendation identifying vulnerable software is a vulnerability finding.

# Agent-Based vs. Agentless Scanning

### Agent-Based Scanning

Agent-based scanning uses software or an agent on the machine to collect information needed for assessment and security monitoring.

### Agentless Scanning

Agentless scanning can assess supported machine information without requiring the same type of software agent to be installed on the machine.

Agentless scanning is one of the capabilities available with Defender for Servers Plan 2.

Understanding the difference is important because organizations may have different requirements regarding software installation, visibility, performance, and security monitoring.

# Endpoint Protection

I was not able to view endpoint protection information in the current lab configuration.

No EDR solution was detected.

This is consistent with Defender for Servers not currently being enabled in the subscription.

# Importance of EDR

Endpoint Detection and Response (EDR) helps security teams identify and investigate suspicious activity on endpoints.

EDR can provide visibility into potentially malicious behavior that may not be detected by traditional antivirus alone.

For a Windows Server, EDR can provide additional visibility into suspicious processes, activity, and potential attacks.

# Additional Defender for Servers Capabilities

During the investigation, I identified several additional capabilities that could improve server security.

Examples include:

* Just-in-time machine access
* File Integrity Monitoring
* Vulnerability assessment
* Security baseline assessment
* Agentless scanning
* Microsoft Defender Vulnerability Management capabilities

Microsoft documents just-in-time machine access as a capability that can help reduce the attack surface by restricting machine management ports until access is required. File Integrity Monitoring can help identify changes to files and registries that may indicate suspicious activity.

# Risk of Not Enabling Defender for Servers

If Defender for Servers is not enabled, the administrator may not have access to some of the additional monitoring, vulnerability assessment, and workload protection capabilities provided by the service.

This could reduce visibility into certain security issues and potentially delay the detection or investigation of threats.

However, not enabling the service does not mean that the environment has **no security protection**. Other Azure security controls and Defender for Cloud capabilities can still provide security recommendations and posture information.

# Cost Considerations

Before enabling Defender for Servers, I would consider:

1. Cost of Plan 1
2. Cost of Plan 2
3. Security capabilities provided by each plan
4. Number of machines that need protection
5. Importance of the systems being protected
6. Existing security controls
7. Whether the additional capabilities improve the organization's security baseline enough to justify the cost

The goal is not simply to purchase the plan with the most features. The goal is to select protection that matches the organization's security requirements and risk.

# Security Decision

### Decision: DEFER

I decided to defer enabling Defender for Servers.

The reason was that I need to perform additional analysis to determine which plan would provide the appropriate level of protection for the current security baseline while also considering the available budget.

I did not enable a paid security plan simply to complete the lab.

This decision allows the security administrator to evaluate the available capabilities, cost, security requirements, and potential business value before making a final decision.

# Analyst Observation

One of the most important lessons from this lab was understanding that **Defender for Cloud recommendations should not automatically be treated as vulnerabilities**.

Defender for Cloud recommendations can identify different types of security problems. Microsoft currently separates recommendations into categories such as misconfigurations, vulnerabilities, and exposed secrets.

Defender also prioritizes recommendations based on risk factors such as Internet exposure, data sensitivity, lateral movement, and attack paths.

Therefore, an administrator should open the recommendation and investigate what type of issue it represents before deciding how to respond.

# What I Learned

Today I learned that Microsoft Defender for Servers can provide additional security capabilities for Windows and Linux machines.

I learned about the difference between Plan 1 and Plan 2 and why an organization should evaluate the capabilities and cost of each plan before selecting one.

I also learned that vulnerability findings and Defender for Cloud recommendations are not always the same thing. Recommendations can represent different types of security issues, including configuration problems and vulnerabilities.

The lab also helped me understand the importance of making security decisions based on risk, security requirements, available resources, and cost.

# Challenges

The main challenge was differentiating between vulnerabilities and security recommendations.

The recommendations were presented with risk prioritization, which initially made it difficult to determine whether each recommendation represented an actual software vulnerability.

After reviewing the Defender for Cloud recommendation categories, I learned that recommendations can represent different types of findings, including misconfigurations and vulnerabilities.

# Errors

No technical errors were encountered during this lab.

The main challenge was understanding the difference between vulnerability findings and other types of Defender for Cloud recommendations.

# Final Assessment

**Defender for Servers: Not enabled

**Plan 1: Not enabled

**Plan 2: Not enabled

**Decision: Defer

**Reason: Additional analysis is needed to determine the appropriate plan based on security requirements and available budget.


