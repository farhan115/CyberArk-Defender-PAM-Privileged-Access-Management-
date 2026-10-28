# CyberArk Defender-PAM | Configure and Manage Passwords

## Overview

This project covers the configuration and management of privileged account passwords using CyberArk Privileged Access Management (PAM).

The objective is to understand how CyberArk protects privileged credentials through access controls, approval workflows, password verification, automatic password changes, reconciliation, and secure account management.

**Certification:** CyberArk Defender-PAM  
**Exam Domain:** Configure and Manage Passwords  
**Study Guide:** CyberArk Defender-PAM Certification Study Guide (2023)

---

## Learning Objectives

- Configure privileged account request and approval workflows.
- Understand non-repudiation and credential theft prevention.
- Configure logon and reconcile accounts.
- Manage service account platforms.
- Configure Safe retention and access restrictions.
- Provision Safes and manage permissions.
- Configure and duplicate platforms.
- Automate password and SSH key management.

---

## Topic 1: Configure a Request/Approval Process

CyberArk can require approval before users access privileged accounts.

### Key Concepts

- Dual-control authorization
- Access requests
- Authorized approvers
- Request justification
- Time-limited access

### Example Workflow

1. A user requests access to a privileged account.
2. The user provides a business justification.
3. An authorized approver reviews the request.
4. The request is approved or rejected.
5. The user accesses the account within the permitted time.
6. Access activity is recorded for auditing.

**Security Benefit:** Prevents unauthorized privileged access and improves accountability.

---

## Topic 2: Configure Workflows for Non-Repudiation

Non-repudiation helps ensure that privileged actions can be attributed to the responsible user.

### Important Controls

- Individual user authentication
- Access request tracking
- Session recording
- Audit logs
- Approval history
- User accountability

**Example:** An administrator connects to a production server through PSM. CyberArk records relevant session activity for auditing and investigation.

---

## Topic 3: Configure Logon and Reconcile Accounts

### Logon Account

A logon account provides credentials used to establish a connection to a target system when required by the platform.

### Reconcile Account

A reconcile account has the permissions needed to reset or recover a managed account's password.

### Example

| Account | Purpose |
|---|---|
| `admin01` | Managed privileged account |
| `logon_user` | Establishes the required connection |
| `reconcile_admin` | Resets the managed account password |

### Practice Objectives

1. Identify a managed account.
2. Determine whether a logon account is required.
3. Configure an appropriate reconcile account.
4. Associate the required accounts with the managed account or platform.
5. Verify password reconciliation behavior.

---

## Topic 4: Configure Service Account Platforms

Service accounts are used by applications, services, and automated processes.

### Key Concepts

- Service account dependencies
- Target account platforms
- Password rotation
- Credential synchronization
- Service availability

### Example

A Windows service runs using a managed service account.

When its password changes, dependent service configurations may need to be updated to prevent authentication failures.

**Security Benefit:** Reduces long-lived privileged credentials while maintaining application availability.

---

## Topic 5: Configure Workflows to Reduce Credential Theft

CyberArk provides controls designed to reduce unnecessary exposure of privileged credentials.

### Security Controls

- Privileged session isolation
- Restricted password retrieval
- Access approval
- Credential rotation
- Least-privilege permissions
- Audit logging

### Example

Instead of revealing a privileged password, an authorized user launches a controlled PSM session.

**Security Benefit:** Reduces direct exposure of privileged passwords.

---

## Topic 6: Configure Safe Retention, Time Restrictions, and CPM Assignment

### Safe Data Retention

Determine how long retained Safe data is preserved according to organizational requirements and supported configuration options.

### Time of Use Restrictions

Restrict privileged access to approved time windows where applicable.

### CPM Assignment

Assign an appropriate Central Policy Manager to manage credentials associated with a Safe.

### Practice Objectives

1. Review Safe configuration.
2. Identify applicable retention requirements.
3. Review permitted access windows.
4. Identify the assigned CPM.
5. Verify credential management functionality.

---

## Topic 7: Loosely Connected Devices

Loosely connected devices may have intermittent connectivity to the PAM infrastructure.

### Examples

- Remote systems
- Occasionally connected servers
- Isolated network devices
- Systems with restricted network connectivity

### Study Objective

Understand when a loosely connected device configuration may be appropriate and how connectivity limitations affect credential management.

---

## Topic 8: Manage Passwords of Supported Usages

A credential may be referenced by multiple applications or services.

### Examples

- Windows services
- Scheduled tasks
- Application dependencies
- Other supported credential usages

### Key Concept

When a managed password changes, associated usages may require coordinated updates.

**Security Benefit:** Helps prevent service disruptions caused by outdated credentials.

---

## Topic 9: Provision a Safe

A CyberArk Safe is a logical secure container used to store and control access to privileged account information.

### Example Workflow

1. Identify the business purpose.
2. Determine the Safe name.
3. Create the Safe.
4. Configure appropriate Safe settings.
5. Assign authorized users or groups.
6. Configure required permissions.
7. Associate the appropriate credential management settings.
8. Verify access.

---

## Topic 10: Safe Naming Conventions

Consistent Safe naming improves administration, organization, and auditing.

### Example Naming Convention

`ENVIRONMENT-SYSTEM-ACCOUNT-TYPE`

Examples:

- `PROD-WINDOWS-ADMINS`
- `DEV-LINUX-ROOT`
- `PROD-DATABASE-ADMINS`
- `TEST-APPLICATION-SERVICE`

These are illustrative naming conventions, not mandatory CyberArk formats.

---

## Topic 11: Duplicate a Platform

Platforms define how CyberArk manages particular account types.

### Practice Workflow

1. Identify an existing platform.
2. Review its configuration.
3. Duplicate the platform.
4. Assign a unique name.
5. Modify the required settings.
6. Review password management policies.
7. Test the configuration.

**Example:** Create a customized Windows platform based on an existing supported platform.

---

## Topic 12: Add Users or Groups to a Safe

Safe permissions control which users can access and manage stored credentials.

### Example Permissions

| Permission | Purpose |
|---|---|
| List accounts | View account listings |
| Retrieve accounts | Retrieve permitted account credentials |
| Use accounts | Use accounts for authorized access |
| Add accounts | Add new managed accounts |
| Update account properties | Modify permitted account settings |
| Manage Safe members | Administer Safe membership |

### Security Best Practices

- Follow least privilege.
- Prefer group-based permissions when appropriate.
- Separate administrative responsibilities.
- Review Safe membership regularly.

---

## Topic 13: Use an Out-of-the-Box Platform

CyberArk provides supported platforms for managing different account types.

### Examples

- Windows accounts
- UNIX/Linux accounts
- Database accounts
- Network device accounts

### Practice Objectives

1. Identify the target system.
2. Select a compatible platform.
3. Configure the managed account.
4. Review platform settings.
5. Test credential verification and management.

---

## Topic 14: Import a Custom Platform from the Marketplace

CyberArk Marketplace provides integration resources and platform packages.

### General Workflow

1. Identify the required integration.
2. Review compatibility and prerequisites.
3. Obtain the approved package.
4. Import it using the supported procedure.
5. Configure required settings.
6. Test in a non-production environment.
7. Document the results.

**Security Consideration:** Review platform packages and follow organizational change-management procedures before deployment.

---

## Topic 15: Configure Automatic Password and SSH Key Management

CyberArk CPM supports automated credential management for compatible platforms.

### Password Verification

Checks whether managed credentials remain valid.

### Password Change

Updates a managed account's password according to configured policies.

### Password Reconciliation

Resets or recovers a managed password using an appropriately authorized reconcile account.

### SSH Key Management

Supports management of SSH credentials where compatible platforms and configurations are available.

### Example Workflow

1. Configure the account platform.
2. Enable supported credential management operations.
3. Configure verification settings.
4. Configure password change policies.
5. Configure reconciliation when required.
6. Test the operations.
7. Review logs and results.

---

## Topic 16: Security Value of Managing Credentials

CyberArk PAM helps organizations reduce risks associated with unmanaged privileged credentials.

### Key Benefits

- Reduces password reuse.
- Supports automated credential rotation.
- Limits privileged credential exposure.
- Improves accountability.
- Supports access control policies.
- Enables centralized credential management.
- Provides audit evidence.
- Reduces reliance on manual password administration.

---

## Suggested Hands-On Labs

| Lab | Practice Objective |
|---|---|
| Lab 1 | Configure a privileged access approval workflow |
| Lab 2 | Review non-repudiation controls |
| Lab 3 | Configure logon and reconcile accounts |
| Lab 4 | Review service account platform dependencies |
| Lab 5 | Configure Safe settings and CPM assignment |
| Lab 6 | Create a Safe and define naming conventions |
| Lab 7 | Assign Safe permissions to users and groups |
| Lab 8 | Duplicate an existing platform |
| Lab 9 | Review a supported Marketplace platform |
| Lab 10 | Configure password verification |
| Lab 11 | Configure password changes and reconciliation |
| Lab 12 | Explore SSH key management |
| Lab 13 | Troubleshoot a simulated password rotation failure |
| Lab 14 | Document credential management security controls |

These are suggested exercises for an authorized lab environment, not claims of completed hands-on work.

---

## Key CyberArk Components

| Component | Function |
|---|---|
| Digital Vault | Securely stores privileged credentials |
| PVWA | Provides account and policy administration |
| CPM | Automates password verification, change, and reconciliation |
| PSM | Provides controlled and monitored privileged sessions |
| Safe | Organizes credentials and enforces access permissions |
| Platform | Defines credential management behavior |

---

## Expected Learning Outcomes

After completing this study domain, learners should understand how to:

- Configure approval and accountability workflows.
- Manage privileged passwords securely.
- Configure Safe permissions.
- Provision and organize Safes.
- Manage credential platforms.
- Understand password verification, changes, and reconciliation.
- Identify credential management security benefits.

---

## References

- CyberArk Defender-PAM Certification Study Guide (2023)
- [CyberArk Product Documentation](https://docs.cyberark.com/)
- [CyberArk Training](https://training.cyberark.com/)

## Disclaimer

This repository is intended for educational purposes and certification preparation. The exam objectives are based on the 2023 CyberArk Defender-PAM Study Guide. Explanations, examples, and suggested labs are supplementary learning materials. Actual procedures and available settings depend on the CyberArk product, deployment model, and version.
