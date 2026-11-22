# Microsoft Entra ID | Identity & Access Security

### Scenario-Based Cybersecurity Implementation Project

**Project:** New Employee Onboarding & Identity Security  
**Platform:** Microsoft Entra ID | Microsoft 365 | Microsoft Defender  
**Focus Areas:** Identity & Access Management (IAM), MFA, Conditional Access, RBAC, Least Privilege  
**Status:** Implementation Planned / In Progress

---

## 1. Project Overview

This project demonstrates the implementation of a secure employee onboarding process using Microsoft Entra ID and Microsoft 365 within a controlled enterprise-style lab environment.

The objective is to simulate how an organisation securely provisions employee identities, manages access to corporate resources, enforces authentication policies, and monitors identity-related security activities.

The implementation focuses on applying industry-standard identity security principles, including **Zero Trust, least privilege, role-based access control (RBAC), and multifactor authentication (MFA).**

## 2. Business Scenario

### New Cybersecurity Analyst Onboarding

Contoso Professional Services, a fictional organisation, has recently hired **Daniel Silva** as a Cybersecurity Analyst within its Security Operations team.

As a new employee, Daniel requires access to essential Microsoft 365 productivity applications, internal collaboration resources, security dashboards, and organisational files to perform his responsibilities.

However, the organisation must ensure that Daniel receives **only the permissions necessary for his role**, without exposing sensitive administrative functions or creating unnecessary security risks.

The Security Operations team has been tasked with securely onboarding Daniel into the organisation's Microsoft cloud environment.

### Business Requirements

Daniel must be able to:

- Sign in securely using his corporate Microsoft Entra ID account.
- Register and use multifactor authentication (MFA).
- Access approved Microsoft 365 applications and services.
- Collaborate with colleagues using Microsoft Teams and SharePoint.
- Store and share organisational documents internally through OneDrive.
- View relevant security dashboards and reports.
- Perform his responsibilities without unnecessary administrative privileges.

### Security Challenges

The organisation must prevent:

- Unauthorised access resulting from weak authentication.
- Excessive privileges and unnecessary administrative access.
- Uncontrolled access to organisational resources.
- Anonymous or unapproved external file sharing.
- Inconsistent user and group permission assignments.
- Insufficient visibility into user authentication and access activities.

## 3. My Role and Responsibilities

**Role: Identity & Access Management / Cybersecurity Analyst (Simulated)**

For this project, I will act as the security professional responsible for designing, implementing, and validating the employee onboarding workflow.

My responsibilities include:

1. Creating and configuring the employee's Microsoft Entra ID identity.
2. Designing security groups and access assignments.
3. Configuring group-based Microsoft 365 licensing where supported.
4. Implementing MFA and Conditional Access security policies.
5. Applying least-privilege access using RBAC.
6. Configuring SharePoint, Microsoft Teams, and OneDrive access.
7. Reviewing authentication and audit logs.
8. Validating authorised access and denied administrative actions.
9. Documenting configuration decisions, security outcomes, and supporting evidence.

## 4. Project Objectives

The primary goal is to establish a secure, manageable, and auditable identity onboarding process.

**Key objectives:**

- Centralise identity management using Microsoft Entra ID.
- Enforce strong authentication through MFA.
- Apply Conditional Access to protect organisational resources.
- Implement role-based access following least-privilege principles.
- Control application and collaboration access through group membership.
- Monitor identity and authentication activities.
- Verify security controls through positive and negative testing.
- Produce professional technical documentation suitable for security audits.

## 5. Lab Environment & Technologies

| Technology | Purpose |
|---|---|
| Microsoft Entra ID | Identity creation and access management |
| Microsoft 365 Admin Center | User administration and licensing |
| Microsoft Entra Conditional Access | Authentication policy enforcement |
| Microsoft Authenticator | Multifactor authentication |
| Microsoft Defender Security Portal | Read-only security visibility |
| Microsoft Teams | Team collaboration |
| SharePoint Online | Organisational document access |
| OneDrive for Business | Secure file storage and sharing |
| Microsoft Entra Sign-in Logs | Authentication investigation |
| Microsoft Entra Audit Logs | Tracking identity configuration changes |

**Lab requirements:** An authorised Microsoft tenant, appropriate administrative permissions, supported licensing, fictional test identities, and a protected emergency-access account.

Features requiring additional licensing will be implemented only where supported by the lab.

## 6. Implementation Plan

### Phase 1 — Identity Provisioning

Create Daniel Silva's Microsoft Entra ID account with the following fictional business attributes:

| Attribute | Configuration |
|---|---|
| Display Name | Daniel Silva |
| Job Title | Cybersecurity Analyst |
| Department | Security Operations |
| Office Location | Melbourne |
| Usage Location | Australia |
| Account Type | Member |
| Manager | Fictional test manager |
| Initial Password | Change required at first sign-in |

**Expected outcome:** A properly configured employee identity with accurate organisational attributes.

### Phase 2 — Group-Based Access Management

Create the following groups:

| Group | Purpose |
|---|---|
| SG-LIC-M365-E5-SOC | Microsoft 365 licensing |
| SG-CA-MFA-Required | MFA Conditional Access targeting |
| M365-Security-Operations | Teams and SharePoint collaboration |
| SG-Security-ReadOnly-Access | Controlled security visibility, where supported |

Assign Daniel to the appropriate groups and document how each group grants access.

**Expected outcome:** Centralised, auditable access management using groups rather than unnecessary direct assignments.

### Phase 3 — Microsoft 365 Licensing

Configure group-based licensing using an available Microsoft 365 E5 or equivalent lab licence.

Validate access to the relevant services and document any licensing restrictions or assignment errors.

**Expected outcome:** Required services become available to Daniel through the intended licensing workflow.

### Phase 4 — MFA and Conditional Access

Create a Conditional Access policy named:

`CA-Require-MFA-SOC-Users`

Planned configuration:

- Target group: `SG-CA-MFA-Required`
- Authentication requirement: MFA
- Target resources: Approved lab resource scope
- Emergency-access exclusion: Required
- Initial policy state: Report-only
- Validation: What If tool and sign-in logs

Only consider enforcement after confirming that the policy applies to Daniel without affecting emergency access.

**Expected outcome:** Strong authentication for the intended users and resources without creating an administrator lockout risk.

### Phase 5 — Least-Privilege Access

Assign the minimum security role necessary for Daniel's responsibilities, such as Security Reader where supported.

Verify that Daniel can view appropriate security information but cannot modify administrative settings.

**Expected outcome:** Read-only security visibility without excessive privileges.

### Phase 6 — Secure Collaboration

Configure access through the Microsoft 365 Security Operations group.

Validate:

- Teams and SharePoint membership.
- Successful document collaboration.
- Restricted administrative functionality.
- Controlled OneDrive internal sharing.
- Blocked anonymous or unapproved external sharing.

**Expected outcome:** Secure collaboration with appropriate access restrictions.

### Phase 7 — Security Monitoring and Validation

Review authentication events, identity changes, policy results, and access attempts.

Perform both successful-access and denied-access tests to verify that the implemented controls work as intended.

## 7. Validation and Expected Results

The following tests will be completed during implementation.

| Security Control | Expected Result | Status |
|---|---|---|
| Employee account creation | Account successfully provisioned | Pending |
| First sign-in | Password change completed | Pending |
| MFA | Successful registration and challenge | Pending |
| Conditional Access | Correct policy application | Pending |
| Group-based licensing | Licence inherited through group | Pending |
| Microsoft 365 access | Required applications available | Pending |
| Teams / SharePoint | Collaboration access successful | Pending |
| OneDrive | Internal sharing allowed | Pending |
| Security dashboards | Read-only access successful | Pending |
| Administrative permissions | Unauthorised changes denied | Pending |
| Audit and sign-in logs | Relevant activities traceable | Pending |

*Actual results and evidence references will be recorded after testing.*

## 8. Screenshots and Technical Evidence

Each implementation phase will be supported by sanitised screenshots and technical documentation.

**Planned evidence:**

- Employee identity configuration.
- Group creation and membership.
- Microsoft 365 licence assignment.
- MFA and Conditional Access configuration.
- Conditional Access What If results.
- Read-only role assignment.
- SharePoint and Teams permissions.
- OneDrive sharing restrictions.
- Successful and denied access tests.
- Sanitised sign-in and audit-log findings.

Screenshots will be added to the `screenshots-sanitised/` directory as each phase is completed.

## 9. Security Outcomes

This project aims to demonstrate how effective identity and access management can reduce security risks through:

- Strong authentication controls.
- Centralised identity administration.
- Consistent group-based access management.
- Least-privilege permissions.
- Controlled collaboration and file sharing.
- Auditable identity and authentication activities.
- Verified enforcement of access restrictions.

Final outcomes, test failures, limitations, and remediation actions will be documented following implementation.

## 10. Skills Demonstrated

- Identity & Access Management (IAM)
- Microsoft Entra ID Administration
- Multifactor Authentication (MFA)
- Conditional Access Policy Design
- Role-Based Access Control (RBAC)
- Least-Privilege Access Management
- Microsoft 365 Security Administration
- Identity Security Monitoring
- Audit Log Analysis
- Security Control Validation
- Technical Security Documentation

## 11. Lessons Learned

This section will document implementation challenges, troubleshooting steps, licensing limitations, security observations, and recommended improvements as the project progresses.

## 12. Lab Disclaimer

This project is designed for implementation within an authorised Microsoft cloud lab environment using fictional identities.

No production systems or real organisational identities are involved.

Public documentation will exclude credentials, tenant identifiers, tokens, recovery codes, real account details, and sensitive authentication information.

---

**Portfolio:** [Cybersecurity SOC Portfolio](https://github.com/NajibREZAI/Cybersecurity-SOC-Portfolio)

**Project Type:** Hands-on Identity Security Implementation  
**Author:** Najib REZAI
