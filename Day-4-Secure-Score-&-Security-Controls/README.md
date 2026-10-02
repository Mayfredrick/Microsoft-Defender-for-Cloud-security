# Week 6 – Day 4: Microsoft Defender for Cloud Security Controls and Secure Score

## Objective

The objective of this lab was to understand Microsoft Defender for Cloud security controls, review recommendations associated with those controls, and understand how they relate to Secure Score.

## Analyst Questions and Answers

1. What are security controls?
Security controls are measures and practices designed to protect cloud resources and data from security threats.
In Defender for Cloud, security controls group related security recommendations that address a particular security area.

2. What was your current Secure Score?
My current Secure Score was: 18%

3. Did your Secure Score change from the previous lab?
No. My Secure Score remained at 18%.

4. What three security controls did you review?
I reviewed:
- Network security
- Cloud security
- Regulatory compliance
The controls and recommendations displayed can vary depending on the environment and the security standards being assessed.

5. What recommendations did you find?
Some of the recommendations I reviewed included:
- All network ports should be restricted on network security groups associated with virtual machines.
- Storage accounts should use a private link connection.
- Management ports should be closed on virtual machines.
These recommendations address different areas of network and resource security.

6. What did you find under "Apply system updates"?

Under Apply system updates, I found that Azure provides a Fix option for some recommendations that can simplify remediation. Azure Update Manager can also be used to manage and deploy updates to machines.
The Fix option can provide a quick way to remediate supported recommendations, while Update Manager provides capabilities for managing machine updates.

7. What did you find under "Secure management ports"?
I found that Defender for Cloud provides recommendations for protecting management ports. One option is Just-in-Time (JIT) VM access.
JIT access can restrict inbound traffic to management ports and allow access only when it is needed. This reduces the amount of time that management ports are exposed.
I also observed that recommendation status can take time to update after changes are made.

8. What was the potential score increase for one recommendation?
There was no single potential score increase that I could identify for just one recommendation because I had multiple security controls and recommendations that still required attention.
I therefore did not record a specific score increase for one recommendation.

9. How are security recommendations related to security controls?
Security recommendations are grouped into security controls.
A security control represents a broader security area, while individual recommendations provide specific actions that can be taken to improve that area.
For example:
Security Control → Secure Management Ports
can contain recommendations related to protecting management ports on virtual machines.

10. Why shouldn't administrators focus only on increasing Secure Score?
Administrators should not focus only on increasing Secure Score. They should focus on addressing the underlying security issues while considering the effect of changes on production resources and organizational policies.
Secure Score provides an overall view of security posture, but the individual recommendations provide the specific security issues that need to be reviewed and addressed.

11. Which issue would you focus on first, and why?
I would focus more on management ports because attackers can target exposed management ports such as RDP or SSH.
Reducing unnecessary exposure can reduce the attack surface. Defender for Cloud provides JIT VM access as one method of restricting management-port access when it is not needed.

12. What did you learn from today's lab?
I learned the importance of different security controls and how they relate to security recommendations.
I also learned that Secure Score provides an overall view of the security posture, while security controls and recommendations provide more detailed information about specific security issues.

## Key Takeaways
- Security controls group related security recommendations.
- Secure Score provides an overall view of cloud security posture.
- My current Secure Score remained at 18%.
- Security recommendations provide specific actions for improving security.
- Apply system updates helps address missing system updates.
- Secure management ports helps reduce exposure of management ports.
- Just-in-Time VM access can limit management-port access to when it is actually needed.
- Administrators should consider security, business requirements, production impact, and organizational policies before making changes.
- Increasing Secure Score should not be the only objective; the underlying security issues should be understood and addressed.

## Lab Result
This lab helped me better understand the relationship between security controls, security recommendations, and Secure Score. I also learned how protecting management ports can reduce the attack surface of Azure virtual machines.

