
# Phase 1 — Employee Identity Provisioning

## Business Requirement

Contoso Professional Services needs to onboard Daniel Silva,
a new Cybersecurity Analyst in the Security Operations team.

The employee requires a centrally managed identity with
appropriate business attributes and secure authentication.

## Implementation

Platform: Microsoft Entra ID

Planned configuration:
- Display name: Daniel Silva
- Department: Security Operations
- Job title: Cybersecurity Analyst
- Office location: Melbourne
- Usage location: Australia
- User type: Member
- Account status: Enabled
- Password change required at first sign-in

## Security Considerations

- Use a fictional test identity.
- Require a password change at first sign-in.
- Avoid unnecessary administrative privileges.
- Apply group-based access in subsequent phases.
- Preserve sanitised audit evidence.

## Validation

Status: Pending verification

Checks:
- User exists in Microsoft Entra ID.
- Account is enabled.
- Business attributes are correct.
- Required password-change setting is configured.

## Evidence

Add screenshots after verification:

![Sanitised user overview](../screenshots-sanitised/01-daniel-user-overview0.png)

![Sanitised user properties](../screenshots-sanitised/02-daniel-user-properties.png)



## Phase 2 — Group-Based Licence Management

### Business Requirement
Contoso requires centralised Microsoft 365 licence
management for Security Operations employees.

### Implementation
Created a Microsoft Entra security group:

- Group: SG-LIC-M365-E5-SOC
- Type: Security
- Membership: Assigned
- Intended licence: Microsoft 365 E5
- Test member: Daniel Silva

### Security Rationale
Group-based licensing simplifies onboarding,
reduces manual assignments and supports
consistent access lifecycle management.

### Validation
- Group created: Verify after implementation
- Daniel added: Verify in Members
- Licence assignment: Pending

### Licensing Limitation
At the time of testing, all 20 Microsoft 365 E5
licences were allocated.

Licence inheritance cannot be confirmed until
an available seat is obtained.

### Evidence
Sanitised group overview and membership screenshots.


## Evidence — Group-Based Licensing

### Screenshot 1: Licensing Group Overview

![Licensing Group Overview](../screenshots-sanitised/03-licensing-group-overview.png)

### Screenshot 2: Group Membership

![Daniel Silva Group Membership](../screenshots-sanitised/04-licensing-group-members.png)



# Phase 3 — MFA Security Group

## Business Requirement

Contoso Professional Services requires stronger
authentication controls for Security Operations
employees to reduce the risk of unauthorised access.

## Implementation

Platform: Microsoft Entra ID

Security group configuration:

- Group name: SG-CA-MFA-Required
- Group type: Security
- Membership type: Assigned
- Role assignable: No
- Test user: Daniel Silva

## Security Rationale

The group is designed to target authorised SOC users
with a future Conditional Access policy requiring MFA.

Using security groups supports centralised policy
targeting and simplifies identity access management.

## Validation

- Group creation: Pending verification
- Daniel Silva membership: Pending verification
- Conditional Access policy: Not yet configured
- MFA enforcement: Not yet tested

## Evidence

### MFA Security Group Overview

![MFA Group Overview](../screenshots-sanitised/05-mfa-group-overview.png)

### Group Membership

![Daniel Silva Membership](../screenshots-sanitised/06-mfa-group-members.png)

## Next Steps

1. Verify Conditional Access licensing.
2. Confirm emergency-access account protection.
3. Create the MFA Conditional Access policy.
4. Configure report-only mode.
5. Validate policy targeting using the What If tool.
6. Review sign-in logs before enforcement.



# Phase 4 — Read-Only Security Access Group

## Business Scenario

Contoso Professional Services requires its SOC analysts
to view security dashboards and investigate security
events without unnecessary administrative permissions.

## Security Objective

Implement least-privilege access using Microsoft
Entra ID role-based access control (RBAC).

## Planned Implementation

- Group: SG-Security-ReadOnly-Access
- Group type: Security
- Membership type: Assigned
- Role assignable: Yes (subject to prerequisites)
- Intended member: Daniel Silva
- Intended role: Security Reader

## Security Rationale

Using a role-assignable security group supports
centralised management of administrative role
assignments and simplifies access reviews.

## Validation

- Group creation: Pending verification
- Role-assignable setting: Pending verification
- Daniel's membership: Pending verification
- Security Reader assignment: Not yet performed
- Read-only access testing: Pending

## Evidence

![Read-Only Security Group](../screenshots-sanitised/06-read-only-security-group.png)

## Next Steps

1. Verify group creation and membership.
2. Assign the least-privileged Security Reader role.
3. Test successful read-only access.
4. Verify administrative changes are denied.
5. Review relevant audit logs.



## Group-Based Licensing — Validation

### Business Requirement
Provision Microsoft 365 E5 licensing to Daniel Silva
using centralised Microsoft Entra group membership.

### Implementation
- User: Daniel Silva
- Group: SG-LIC-M365-E5-SOC
- Product: Microsoft 365 E5 (no Teams)
- Assignment method: Group-based licensing

### Validation Results
- Licence state: Active
- Group-based inheritance: Verified
- Redundant direct assignment: NA
- Required services: NA

### Security Outcome
Group-based licensing supports consistent
licence provisioning, centralised administration
and simplified employee offboarding.

### Evidence
![Group-Based Licensing](../screenshots-sanitised/07-group-based-licensing-verified.png)



## Conditional Access Validation

### Policy
CA-Require-MFA-SOC-Users

### What If Evaluation
- Test user: Daniel Silva
- Grant control: Require multifactor authentication
- Policy state: Report-only
- Simulated policy match: Successful
- Emergency-access exclusion: myself -- Adminstrator

### Actual Sign-in Validation
- Test resource: NA
- Sign-in result: NA
- Report-only outcome: NA
- MFA enforcement: Not enabled

### Security Outcome
The What If simulation confirmed that the
MFA policy matches the selected test conditions.

Actual sign-in validation and emergency-access
exclusion testing are documented separately.

### Evidence

![What If Evaluation](../screenshots-sanitised/10-conditional-access-what-if.png)

![Sign-in Validation](../screenshots-sanitised/11-mfa-signin-validation.png)



# Phase 6 — Security Reader RBAC

## Business Scenario

Contoso requires SOC analysts to investigate
security information without granting excessive
administrative privileges.

## Security Objective

Implement least-privilege access using
Microsoft Entra ID Role-Based Access Control.

## Implementation

- Test user: Daniel Silva
- Security group: SG-Security-ReadOnly-Access
- Intended role: Security Reader
- Assignment method: Group-based RBAC

## Validation

- Group role-assignable: Pending verification
- Security Reader assignment: Pending
- Daniel's inherited role: Pending
- Read-only access: Pending
- Administrative changes denied: Pending

## Security Rationale

The Security Reader role enables appropriate
visibility into security information without
granting broad configuration permissions.

## Evidence

![Role Assignment](../screenshots-sanitised/13-security-reader-assignment.png)

![Inherited Role](../screenshots-sanitised/14-daniel-security-reader-active.png)



## Phase 7.2 – SharePoint Team Site Provisioning

### Objective

Implement identity-based access to Security Operations
resources using Microsoft Entra ID, Microsoft 365 Groups
and SharePoint Online.

### Implementation

- Verified the Microsoft 365 group-connected
  SharePoint team site.
- Confirmed the site was configured as private.
- Verified Daniel Silva's standard group membership.
- Maintained separation between administrative
  and standard user permissions.

### Security Controls

- Group-based access management
- Role-based access control (RBAC)
- Least privilege
- Centralised identity governance

### Implementation Evidence

#### SharePoint Active Sites

![Active Sites](../screenshots-sanitised/phase7-03a-active-sites.png)

#### Site Membership

![Site Membership](../screenshots-sanitised/phase7-03b-site-membership.png)

#### SharePoint Team Site

![Team Site](../screenshots-sanitised/phase7-03c-sharepoint-homepage.png)

### Security Outcome

Established a group-connected collaboration
environment for Security Operations personnel.

User access is managed centrally through Microsoft
Entra ID group membership, reducing the need for
individual permission assignments.



## Phase 7.3 – SharePoint External Sharing Restrictions

### Business Scenario (For quick understanding --- mentioned scenario on purpose AGAIN)

Daniel Silva, as a newly onboarded Cybersecurity Analyst,
requires access to confidential Security Operations
documents. However, the organisation must prevent
these documents from being shared with external
individuals through SharePoint.

### Objective

Implement site-level external sharing restrictions
to reduce unauthorised disclosure while maintaining
authorised internal collaboration.

### Implementation

1. Accessed the SharePoint Admin Center.
2. Navigated to Sites > Active sites.
3. Selected M365-Security-Operations.
4. Opened the external sharing settings.
5. Selected "Only people in your organization".
6. Saved and verified the security configuration.

### Security Configuration

| Parameter | Configuration |
|---|---|
| Target resource | M365-Security-Operations |
| Policy scope | Site level |
| External sharing | Disabled |
| Anonymous sharing | Disabled |
| External guest access | Restricted |
| Authorised internal collaboration | Permitted |

### Security Controls Demonstrated

- Identity and Access Management (IAM)
- Least Privilege Access
- Data Access Governance
- External Sharing Restrictions
- Insider Risk Mitigation
- Defence in Depth

### Implementation Evidence

#### External Sharing Configuration

![External Sharing Restrictions](../screenshots-sanitised/phase7-04b-sharing-restricted.png)

#### Configuration Verification

![Policy Verification](../screenshots-sanitised/phase7-04c-sharing-verified.png)

### Expected Security Outcome

Authorised Security Operations personnel can
collaborate internally while external sharing
through SharePoint is restricted, reducing the
risk of accidental or unauthorised data disclosure.

### Control Limitations

This configuration does not prevent users from
downloading documents and distributing them through
other channels. Additional Data Loss Prevention
(DLP) controls are required to mitigate this risk.

### Validation Status

- Administrative configuration: Verified
- End-user enforcement testing: Pending Phase 7.4






