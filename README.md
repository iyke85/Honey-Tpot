# # Privileged Access Governance, Role Activation, Approval Workflow
![Privileged Access Governance, Role Activation/Approval Workflow](https://i.imgur.com/FZf9nTR.png)

## Project Overview

In this implementation, I configured Privileged Identity Management (PIM) within Microsoft Entra ID to securely manage administrative access for a SharePoint Administrator role. The objective was to enforce governance controls, reduce standing privileges, and introduce approval-based access for elevated permissions.

## Objective
To ensure privileged access to SharePoint Online is controlled, auditable, and approved through a structured workflow — minimizing security risks associated with permanent administrative assignments.
Implementation Details
## 1️⃣ PIM Activation Configuration
- Enabled Privileged Identity Management (PIM) in the Enterprise tenant.
- Selected the SharePoint Administrator Azure AD role.
- Configured the role type as Active assignment.
![Architecture Diagram](https://i.imgur.com/YPtj8Wa.png)
![Architecture Diagram](https://i.imgur.com/FhgAO99.png)
[![Architecture Diagram](https://i.imgur.com/20RobDl.png)
[![Architecture Diagram](https://i.imgur.com/d702JVk.png)

## 2️⃣ Approval Workflow Setup
- Configured approval settings requiring manager authorization.
- When the role was activated:
- An automatic email notification was sent to the user’s manager.
- The manager approved the request.
- The role was successfully assigned to the user.
## 3️⃣ Governance & Control Measures
- Enforced approval-based activation.
- Ensured role assignment was auditable via Entra logs.
- Reduced risk of unauthorized privilege escalation.
  
[![Architecture Diagram](https://i.imgur.com/d702JVk.png)
 
## Security & Compliance Impact
- Eliminates uncontrolled administrative access.
- Introduces accountability through manager approval.
- Improves audit readiness and compliance posture.
- Aligns with Zero Trust and least privilege principles.
[![Architecture Diagram](https://i.imgur.com/lmNWvd9.png)
## Outcome
The successful activation of the SharePoint Administrator role through PIM demonstrates controlled privileged access management within Microsoft Entra ID. By integrating approval workflows and audit logging, the environment now enforces stronger governance and reduces exposure to security risks associated with permanent elevated roles.
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
![Architecture Diagram](https://i.imgur.com/mxaxroh.png)
![Architecture Diagram](https://i.imgur.com/nJScDop.png)
![Architecture Diagram](https://i.imgur.com/R0FdoMQ.png)
![Architecture Diagram](https://i.imgur.com/IoQ1UVC.png)
[![Architecture Diagram](https://i.imgur.com/izfUW3Z.png)
[![Architecture Diagram](https://i.imgur.com/f0JxqwQ.png)
## Business Value
- Reduced manual access modification workload
- Strengthened governance during internal role transitions
- Prevented access sprawl and privilege creep
- Improved audit visibility of role-based access changes
- Enhanced security posture through automated enforcement
## Key Skills Demonstrated
- Identity lifecycle automation
- Access recertification principles
- Role-based access management
- Microsoft Entra Identity Governance
- Secure workflow configuration
## Automated Offboarding (Leaver) Workflow Using Microsoft Entra Lifecycle Workflows

Built an automated offboarding workflow in Microsoft Entra Lifecycle Workflows to securely manage user departures. The solution removes group memberships, revokes Microsoft Teams access, and notifies managers before the employee’s final working day to ensure a controlled and auditable exit process.
## Platform & Technologies
- Microsoft Entra ID
- Identity Governance – Lifecycle Workflows
- Microsoft 365
- Microsoft Teams
- Group-based access control
## Workflow Trigger
The workflow is triggered based on the user’s termination date or last working day attribute, ensuring offboarding actions occur at the correct time without manual intervention.
![Architecture Diagram](https://i.imgur.com/KEQuRho.png)
![Architecture Diagram](https://i.imgur.com/1RfgtHW.png)
![Architecture Diagram](https://i.imgur.com/bRAl2xP.png)
![Architecture Diagram](https://i.imgur.com/hz2B4z0.png)

## Conclusion

Through the integration of Okta and Microsoft Entra lifecycle automation, this implementation establishes a scalable and policy-driven identity management framework. The coordinated workflows improve operational efficiency, prevent privilege accumulation, and ensure timely provisioning and deprovisioning across the organization’s identity ecosystem.


