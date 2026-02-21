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
Successfully activating the SharePoint Administrator role through PIM shows controlled privileged access management in Microsoft Entra ID. By adding approval workflows and audit logging, the environment now enforces stronger governance and reduces exposure to security risks from permanently elevated roles.
