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
  

## Contractor Access Control Using Attribute-Based Grouping and Adaptive Policies in Okta

Built a secure contractor access model in Okta using attribute-based group rules and targeted authentication policies. The solution automatically classifies contractor accounts, enforces stronger password requirements, and applies multi-factor authentication to reduce risk associated with non-employee access.
# Tools & Technologies
- Okta Identity Cloud
- Okta Universal Directory
- Okta Group Rules
- Okta Password Policies
- Okta Enrollment and Authentication Policies
## Contractor Password Policy
- Created a dedicated password policy for contractors
- Enforced a minimum 12-character password length
- Applied stricter password standards to contractor accounts to reduce credential-based risk

## Attribute-Based Group Assignment and Password Policy
![Architecture Diagram](https://i.imgur.com/xqXWlvm.png)
![Architecture Diagram](https://i.imgur.com/ki6X0mU.png)
![Architecture Diagram](https://i.imgur.com/Mz6qUJ4.png)

## Implementation Details
- Created a Contractor group in Okta
- Implemented a group rule that automatically adds users to the Contractor group when the department attribute equals contractor
- Ensured dynamic, scalable group membership without manual intervention
![Architecture Diagram](https://i.imgur.com/zWWVuxg.png)
![Architecture Diagram](https://i.imgur.com/MJ0i6Bd.png)
![Architecture Diagram](https://i.imgur.com/Mz6qUJ4.png)
## Authentication and Enrollment Policy
- Configured a contractor-specific enrollment and authentication policy
- Required authentication using:
- Password
- Okta Verify as an additional factor
- Restricted authentication methods to prevent weaker or unsupported MFA options
![Architecture Diagram](https://i.imgur.com/NvZTaNo.png)
## Business Impact
- Automated contractor classification and policy enforcement
- Reduced manual effort in managing non-employee access
- Improved security posture for third-party and temporary users
- Ensured consistent application of stronger authentication controls
- Supported least-privilege and zero-trust identity principles
## Key Skills Demonstrated
- Attribute-based access control (ABAC)
- Identity lifecycle management
- Secure authentication policy design
- MFA enforcement and factor restrictions
- Okta group rule configuration
## Workflow Logic Summary
- User account is created or updated
- Okta evaluates the user’s department attribute
- Users with department set to contractor are automatically added to the Contractor group
- Contractor-specific password and authentication policies are applied
- Access and authentication behavior are enforced consistently across contractor accounts

## ENTRA ID LIFECYCLE WORKFLOW JOINERS/MOVERS/LEAVERS.

Built an automated joiner-new-hire onboarding workflow in Microsoft Entra ID using Lifecycle Workflows. The solution creates user accounts, assigns group-based access, and sends onboarding communications automatically, so new employees have consistent, secure access from Day 1.
## Platform & Technologies
- Microsoft Entra ID
- Identity Governance (Lifecycle Workflows)
- Microsoft 365
- Group-based access control (RBAC)
## Workflow Trigger
The workflow is triggered when a new employee account meets the defined onboarding criteria (for example: account created or hire date reached).
## Tasks Configured
- Enable User Account
- Automatically activates the user account at the appropriate onboarding stage, ensuring access is granted only when the employee officially begins.
## Impact:
- Prevents premature access while guaranteeing Day 1 readiness.
## Add User to Groups
- Adds the new hire to predefined security groups.
## Impact:
- Grants access to required applications
- Ensures role-based access consistency
- Eliminates manual group assignment errors
## Send Welcome Email
- Automatically sends a welcome message with onboarding instructions and login guidance.
## Impact:
- Improves user experience
- Reduces helpdesk tickets
- Standardizes onboarding communication
![Architecture Diagram](https://i.imgur.com/p1DrZBC.png)
![Architecture Diagram](https://i.imgur.com/RfTXTS0.png)
![Architecture Diagram](https://i.imgur.com/13Vyrxj.png)
![Architecture Diagram](https://i.imgur.com/RU7bDE9.png)
![Architecture Diagram](https://i.imgur.com/BXgmu8q.png)
[![Architecture Diagram](https://i.imgur.com/0VKauRr.png)
## Business Value
- Reduced manual onboarding effort
- Accelerated employee productivity
- Improved security through consistent access enforcement
- Increased audit visibility for identity lifecycle events
- Standardized onboarding process across the organization
## Key Skills Demonstrated
- Identity lifecycle automation
- Microsoft Entra Lifecycle Workflows configuration
- Group-based access provisioning
- Access governance principles
- Secure onboarding process design


## Automated Role Change (Mover) Workflow Using Microsoft Entra Lifecycle Workflows

Configured an automated role change (Mover) workflow in Microsoft Entra Lifecycle Workflows to manage access transitions when employees change departments or roles. The workflow removes outdated access, assigns new role-based group memberships, and notifies the user’s manager to maintain visibility and governance during access changes.
## Platform & Technologies
- Microsoft Entra ID
- Identity Governance – Lifecycle Workflows
- Microsoft 365
- Security & Microsoft 365 Groups
- Role-based access control (RBAC)
## Workflow Trigger
The workflow is triggered when a user’s profile attributes indicate a role or department change, ensuring access updates occur automatically during internal transitions.
## Tasks Configured
- Remove User from Selected Groups
- Automatically removes the user from previous role-based or department-specific groups.
## Impact:
- Prevents privilege accumulation
- Reduces risk of excessive access
- Supports the least-privilege security model
## Add User to New Groups
- Assigns the user to new groups aligned with their updated role or department.
## Impact:
- Ensures correct application and resource access
- Maintains consistency across identity governance policies
- Eliminates manual reassignment errors
## Send Email Notification to Manager
- Automatically sends a notification to the user’s manager informing them of the access changes.
## Impact:
- Provides transparency
- Supports accountability and oversight
- Improves communication between IT and leadership
![Architecture Diagram](https://i.imgur.com/p1DrZBC.png)
![Architecture Diagram](https://i.imgur.com/RfTXTS0.png)
![Architecture Diagram](https://i.imgur.com/13Vyrxj.png)
![Architecture Diagram](https://i.imgur.com/RU7bDE9.png)
![Architecture Diagram](https://i.imgur.com/BXgmu8q.png)
[![Architecture Diagram](https://i.imgur.com/0VKauRr.png)



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


