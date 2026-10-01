# Week 6 – Day 3: Microsoft Defender for Cloud Recommendation Prioritization

# Objective

The objective of this lab was to review multiple Microsoft Defender for Cloud recommendations, compare their security concerns, identify affected resources, and determine which recommendations should be remediated, investigated, or monitored.

The main focus was on understanding why security recommendations should be prioritized instead of automatically applying every recommended change.


# Recommendations Reviewed

I reviewed the following recommendations:

1. All network ports should be restricted on network security groups associated with virtual machines
2. Machines should be configured to periodically check for missing system updates
3. Windows virtual machines should enable Azure disk encryption or Encryption at Host

# Analyst Questions and Answers

# 1. Why is it important to prioritize Defender for Cloud recommendations?

It is important to prioritize Defender for Cloud recommendations because they help administrators identify security issues that may need to be addressed. Prioritization helps administrators focus on issues that could have a greater security impact.

# 2. What three recommendations did you review?

I reviewed:

- All network ports should be restricted on network security groups associated with virtual machines.
- Machines should be configured to periodically check for missing system updates.
- Windows virtual machines should enable Azure disk encryption or Encryption at Host.

# 3. Which recommendation appeared to be the greatest concern, and what evidence supported your decision?

The recommendation concerning missing system updates appeared to be the greatest concern to me.

Keeping systems updated is important because updates can include security fixes for known vulnerabilities. Delaying security updates can leave systems exposed to vulnerabilities that attackers may exploit. Microsoft notes that software updates often contain security patches for vulnerabilities.

# 4. What resource was affected?

The affected resource was:

HomelabVM01

# 5. What risk factors were identified?

There were no specific risk factors shown for this recommendation in my lab environment.

# 6. Was the affected VM exposed to the Internet?

Based on what I observed in the recommendation details, HomelabVM01 was not shown as Internet exposed for this recommendation.

# 7. Was there an attack path associated with the recommendation?

No attack path was associated with this recommendation.

# 8. What remediation did Defender for Cloud recommend?

Defender for Cloud recommended enabling periodic assessment so the machine can automatically check for missing system updates.

Microsoft's Azure Update Manager documentation explains that periodic assessment allows Update Manager to automatically check for available updates every 24 hours.

# 9. Would you remediate, investigate, or monitor this recommendation? Why?

I would remediate this recommendation because regularly assessing the system for available updates helps identify missing security and critical updates.

However, enabling periodic assessment is different from automatically installing every update. Update Manager can assess the machine for missing updates, while update installation can be managed separately through on demand updates, scheduled patching, or other supported patching options.

# 10. What could happen if you remediate a security recommendation without understanding its impact?

Making security changes without understanding their impact could affect the availability or operation of a resource. For example, changes related to updates, networking, or encryption may require additional configuration or could affect applications running on a VM.

Security changes should therefore be reviewed and tested before being applied to important production systems.

# 11. Why should administrators avoid automatically fixing every recommendation?

Administrators should not automatically fix every recommendation because some changes can affect production resources or application compatibility.

Updates should be evaluated and tested when appropriate before being deployed to production. A controlled testing or sandbox environment can help identify compatibility problems before changes are made to production systems.

# 12. What did you learn about prioritizing security recommendations?

I learned that it is important to prioritize security recommendations based on the potential security impact and the resource affected.

Prioritizing recommendations helps administrators focus on security issues that require attention while also considering the possible impact of remediation on the environment.

# Key Technical Takeaways

- Defender for Cloud recommendations help identify potential security improvements.
- Recommendations should be reviewed and prioritized rather than automatically applied.
- Missing security updates can leave systems exposed to known vulnerabilities.
- Azure Update Manager can perform periodic update assessments.
- Periodic assessment checks for available updates approximately every 24 hours.
- Periodic assessment does not necessarily mean that every available update is immediately installed.
- Update installation can be performed through ondemand updates or scheduled patching.
- Testing changes before applying them to production can help reduce unexpected service disruptions.

# Lab Result
This lab helped me understand that security recommendations should be reviewed based on risk, affected resources, and potential operational impact. I also learned the difference between periodically assessing a VM for missing updates and actually installing those updates.
