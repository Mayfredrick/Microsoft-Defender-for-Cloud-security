
# Week 6 Day 2 – Microsoft Defender for Cloud Recommendation Remediation

## Objective

The objective of this lab was to investigate and remediate a Microsoft Defender for Cloud recommendation related to an exposed management port on an Azure virtual machine. I used a Network Security Group (NSG) to restrict RDP access to a specific public IP address and then tested the connection.

## Lab Environment

 Azure Resource Group: Homelab-RG
 Virtual Machine: Homelab-VM01
 Private IP: 10.10.1.4
 RDP Port: TCP 3389
 Network Security Group: Homelab-NSG
 Security Tool: Microsoft Defender for Cloud

## Security Recommendation Investigated

The recommendation I investigated was related to an exposed management port on a virtual machine. The recommendation identified that the management port should not be broadly accessible from the Internet.

The affected resource was:

Homelab-VM01

The management port involved was:

RDP – TCP 3389

Microsoft identifies unrestricted Internet access to management ports such as RDP as a security concern because attackers can scan exposed cloud systems and attempt unauthorized access.

## Original NSG Configuration

The original inbound rule allowed RDP from:

Source: Any

This meant that RDP traffic from any public IP address could potentially reach the management port if the traffic otherwise matched the rule.

## Remediation

I changed the source restriction from:

Any

to:

216.169.136.205/32

The /32 restricts the rule to that single public IP address.

The destination remained:

Any

The protocol remained:

TCP

The destination port remained:

3389

Microsoft recommends using a specific source IP or appropriate IP range when Internet-based RDP access is required rather than allowing RDP from any source.

## Testing the Remediation

I tested the RDP connection after changing the NSG rule.

The results were:

 RDP connection from 216.169.136.205 — Successful
 RDP connection from a different public IP — Denied

This confirmed that the NSG rule was restricting RDP access to the intended source address.

## Security Benefit

Restricting the source range reduces the attack surface by limiting which public IP addresses can reach the RDP management port.

It also prevents random Internet sources from connecting to TCP 3389 when they are not included in the allowed source range.

## Potential Impact

Restricting the source range too much can prevent legitimate administrators from accessing the VM. For example, if the allowed public IP changes or the administrator connects from another network, RDP access could be denied.

This is why the source IP should be verified and documented before implementing the change.

## What I Would Do If RDP Stopped Working

If RDP stopped working after the change, I would first verify the current public IP of the management system and review the NSG rule, rule priority, and effective security rules.

I would then update the source range to the appropriate trusted address rather than immediately reopening RDP to all Internet sources.

Azure recommends using effective security rules and IP flow verification when troubleshooting NSG-related connectivity problems.

## Why Testing Is Important

NSG changes should be tested before being applied to production systems. Testing helps confirm that the security control works as intended without accidentally blocking legitimate administrative access or other required traffic.

## Defender for Cloud and NSGs

Using Defender for Cloud recommendations together with NSGs helps identify and address network security weaknesses.

In this lab, Defender for Cloud identified the exposed management port, while the NSG provided the control needed to restrict access to the specific source IP.

This combination helped narrow the security issue and apply a targeted remediation. Microsoft describes Defender for Cloud as providing recommendations for overly permissive inbound traffic and other network security weaknesses.

## What I Learned

I learned how to use a Defender for Cloud recommendation to identify a network security issue and then use an NSG to apply a targeted security control.

I also learned that restricting RDP to a specific public IP can reduce unnecessary exposure while still allowing legitimate administrative access.

Most importantly, I learned that security remediation should be tested after implementation to verify that the intended access still works.

## Challenges

The main challenge was determining which source IP should be used for the NSG rule. My VMware Windows 11 system had a private IP address, but Azure needed the public source IP for the Internet-based RDP connection.

After testing, I confirmed that 216.169.136.205/32 allowed the intended RDP connection while other public IP addresses were denied.

## Screenshots

1. Defender for Cloud management-port recommendation
2. Recommendation details
3. NSG rule before remediation
4. NSG rule with 216.169.136.205/32
5. Successful RDP connection
6. Failed/blocked connection from a different public IP
7. Defender for Cloud recommendation status after remediation

## Key Takeaways

 Defender for Cloud can identify overly permissive network access.
 RDP uses TCP port 3389.
 Allowing RDP from any source increases Internet exposure.
 An NSG can restrict RDP to a specific source IP or range.
 /32 represents one IPv4 address.
 Security changes should be tested after implementation.
 Restricting access too much can prevent legitimate administrators from connecting.
 Defender for Cloud recommendations and NSGs can work together to identify and address network security weaknesses.

## Lab Status

Completed – Remediation successfully tested
