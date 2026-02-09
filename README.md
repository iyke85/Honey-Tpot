# # Enterprise Identity Governance & Access Control Implementation
![Cloud Honeynet / SOC](https://i.imgur.com/qAj7OLS.png)

## Introduction
 This project focused on automating identity provisioning, enforcing strict access control policies, and establishing governance workflows to secure the entire user lifecycle — from onboarding through termination, including incident response and privileged access management. Through hands-on experience and self-led security projects, I’ve built identity infrastructures, strengthened access policies, and explored threat detection techniques to enhance enterprise security. I’m eager to continue growing in IAM/PAM and connect with professionals in the field!

- Automated new hire onboarding workflows for seamless account provisioning and secure app access.
- contractor access lifecycle policies with time-bound permissions and restricted access scopes.
-  automated offboarding procedures for immediate account deactivation and resource cleanup upon employee termination.
- Deployed privileged access governance controls, leveraging just-in-time (JIT) elevation workflows with approval processes.
- Automated Office 365 User Onboarding with Okta Workflows

##  Automated new hire onboarding workflows for seamless account provisioning and secure app access.
![Architecture Diagram](https://i.imgur.com/q1qv8S4.png)
![Architecture Diagram](https://i.imgur.com/S5tbBJF.png)
[![Architecture Diagram](https://i.imgur.com/fT6QcfH.png)
[![Architecture Diagram](https://i.imgur.com/mkUDaPi.png)

 Automated identity onboarding solution using Okta Workflows to provision Office 365 access for newly created users. The workflow assigns users to the appropriate Office 365 access group and sends real-time email notifications to IT for visibility and audit tracking.
 
# Tools & Technologies
- Okta Identity Cloud
- Okta Workflows
- Microsoft Office 365
- Office 365 Mail Connector
- Group-based access provisioning

  # Workflow Logic
- Triggered when a user is created in Okta
- Retrieves user profile attributes
- Validates user status to ensure the account is active
- Automatically assigns the user to the Office 365 access group
- Provisions Office 365 applications via group assignment
- Sends an automated email notification confirming access provisioning
# Business Impact
- Eliminated manual Office 365 license assignment
- Improved onboarding speed and consistency
- Increased visibility through automated notifications
- Reduced risk of missed or incorrect access assignments
- Strengthened IAM governance and audit readiness

## Automated User Suspension Handling and Notification with Okta Workflows
![Architecture Diagram](https://i.imgur.com/EbtToBc.png)
Designed and implemented an automated identity governance workflow using Okta Workflows to handle user suspension events. The workflow ensures suspended users are immediately added to a dedicated security group and triggers an automated email notification, improving visibility, audit readiness, and response time during account lifecycle events.

# Tools & Technologies
- Okta Identity Cloud
- Okta Workflows
- Microsoft Office 365 Mail Connector
- Group-based access management
  ![Architecture Diagram](https://i.imgur.com/gzMnZyK.png)
  ![Architecture Diagram](https://i.imgur.com/lej1MN9.png)
  ![Architecture Diagram](https://i.imgur.com/ytfLCQo.png)
  # Workflow Logic
- Triggered automatically when a user account is suspended in Okta
- Retrieves the suspended user’s profile details for context and logging
- Adds the user to a predefined Suspended Users group for centralized tracking
- Sends an automated email notification to IT/Security via Office 365
- Logs the workflow execution for audit and troubleshooting purposes
  # Business Impact
- Ensured immediate and consistent handling of suspended accounts
- Eliminated manual tracking of suspended users
- Improved security visibility through real-time notifications
- Supported audit and compliance requirements by maintaining group-based records
- Reduced risk of delayed response during security or HR-driven suspensions
 # Key Skills Demonstrated
- Identity lifecycle automation
- Security-focused workflow design
- Okta event-based triggers
- Group-based access control
- Automated notification and audit workflows
  

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic with the exception of my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint

## Attack Maps Before Hardening / Security Controls
![NSG Allowed Inbound Malicious Flows](https://i.imgur.com/1qvswSX.png)<br>
![Linux Syslog Auth Failures](https://i.imgur.com/G1YgZt6.png)<br>
![Windows RDP/SMB Auth Failures](https://i.imgur.com/ESr9Dlv.png)<br>

## Metrics Before Hardening / Security Controls

The following table shows the metrics we measured in our insecure environment for 24 hours:
Start Time 2023-03-15 17:04:29
Stop Time 2023-03-16 17:04:29

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 19470
| Syslog                   | 3028
| SecurityAlert            | 10
| SecurityIncident         | 348
| AzureNetworkAnalytics_CL | 843

## Attack Maps Before Hardening / Security Controls

```All map queries actually returned no results due to no instances of malicious activity for the 24 hour period after hardening.```

## Metrics After Hardening / Security Controls

The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:
Start Time 2023-03-18 15:37
Stop Time	2023-03-19 15:37

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 8778
| Syslog                   | 25
| SecurityAlert            | 0
| SecurityIncident         | 0
| AzureNetworkAnalytics_CL | 0

## Conclusion

In this project, a mini honeynet was constructed in Microsoft Azure and log sources were integrated into a Log Analytics workspace. Microsoft Sentinel was employed to trigger alerts and create incidents based on the ingested logs. Additionally, metrics were measured in the insecure environment before security controls were applied, and then again after implementing security measures. It is noteworthy that the number of security events and incidents were drastically reduced after the security controls were applied, demonstrating their effectiveness.

It is worth noting that if the resources within the network were heavily utilized by regular users, it is likely that more security events and alerts may have been generated within the 24-hour period following the implementation of the security controls.
