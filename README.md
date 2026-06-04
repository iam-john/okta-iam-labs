🔐 Okta IAM Engineering Portfolio
A hands-on lab portfolio documenting my transition into Identity and Access Management (IAM) engineering, built through the Okta Learning Grant program and independent lab work in a live Okta Identity Engine (OIE) developer org.


👤 About This Portfolio
I am currently transitioning into IAM engineering with a focus on Okta, enterprise identity, and cybersecurity. This repository documents every hands-on lab I have completed, including screenshots, configuration decisions, and key learnings.

Certifications In Progress / Completed:

✅ SC-900: Microsoft Security Fundamentals
🔄 CompTIA Security+ (SY0-701) — In Progress
🔄 Okta Certified Professional — In Progress
🎯 Okta Certified Administrator — Planned

Target Roles: IAM Engineer · Okta Administrator · Identity Architect · IAM Consultant


🗂️ Repository Structure
okta-iam-labs/

│

├── 01-account-creation/

│   ├── README.md

│   ├── 01-create-users/

│   ├── 02-custom-attributes/

│   ├── 03-admin-roles/

│   └── 04-groups-and-rules/

│

├── 02-app-integrations/

│   ├── README.md

│   ├── 01-oin-app-setup/

│   ├── 02-saml-configuration/

│   ├── 03-lifecycle-management/

│   └── 04-group-assignment/

│

├── 03-security-enforcement/

│   ├── README.md

│   ├── 01-authenticators/

│   ├── 02-enrollment-policies/

│   ├── 03-global-session-policy/

│   └── 04-authentication-policies/

│

├── 04-attribute-mapping-offboarding/

│   ├── README.md

│   ├── 01-attribute-mappings/

│   └── 02-deactivation-verification/

│

├── 05-system-log-troubleshooting/

│   ├── README.md

│   └── 01-system-log-mastery/

│

└── 06-advanced-labs/

    ├── README.md

    ├── 01-okta-rest-api/

    ├── 02-okta-workflows/

    └── 03-ad-integration/


🧪 Lab Progress Tracker
#
Lab
Category
Status
Key Skill Demonstrated
01
Create Users Manually
Account Creation
🔄 In Progress
Universal Directory, User Profiles
02
Create Custom Attributes
Account Creation
⬜ Not Started
Profile Editor, Attribute Permissions
03
Assign Admin Roles
Account Creation
⬜ Not Started
Least Privilege, Role-Based Admin
04
Create Groups and Group Rules
Account Creation
⬜ Not Started
Group Automation, Expression Language
05
Add OIN App Integration
App Setup
⬜ Not Started
OIN, SAML, SSO
06
Configure Custom SAML
App Setup
⬜ Not Started
SAML 2.0, IdP/SP Configuration
07
Set Up Provisioning
App Setup
⬜ Not Started
Lifecycle Management, SCIM
08
Group-Based App Assignment
App Setup
⬜ Not Started
Access Automation, Verification
09
Add and Remove Authenticators
Security
⬜ Not Started
MFA, Authenticator Management
10
Configure Enrollment Policies
Security
⬜ Not Started
MFA Enrollment, Policy Tiers
11
Global Session Policy Rule
Security
⬜ Not Started
Session Management, Re-auth
12
Authentication Policy and Rules
Security
⬜ Not Started
Risk-Based Access, Rule Priority
13
Attribute Mapping (Okta → App)
Offboarding
⬜ Not Started
Profile Editor, Data Mapping
14
Deactivate User + Verify
Offboarding
⬜ Not Started
Offboarding, Audit Trail
15
System Log Mastery
Troubleshooting
⬜ Not Started
Log Analysis, Incident Investigation
16
User State Transitions
Lifecycle
⬜ Not Started
User States, Access Management


Legend: ✅ Complete · 🔄 In Progress · ⬜ Not Started


🔑 Core Concepts Demonstrated
Identity and Access Management
Single Sign-On (SSO) configuration using SAML 2.0 and OIDC
IdP-initiated vs SP-initiated authentication flows
Federated identity across multiple organizations
User Lifecycle Management
Automated user provisioning and deprovisioning
Universal Directory schema management and custom attributes
Group-based access automation using Okta Expression Language
Joiner / Mover / Leaver workflow implementation
Security and Policy Configuration
Multi-factor authentication design and implementation
Risk-based authentication policies with network zone conditions
Global Session Policy configuration for session governance
MFA enrollment policy tiering by user risk group
Administration and Troubleshooting
Okta System Log interpretation and event correlation
User state management across the full lifecycle
Admin role assignment with least privilege principles
Audit trail documentation for compliance evidence


🛠️ Technical Environment
Component
Details
Platform
Okta Identity Engine (OIE)
Org Type
Developer Org (Free)
Lab Environment
developer.okta.com
API Testing
Postman
Scripting
Python 3.x with requests library
Directory
Active Directory (Azure Free Tier VM)
Documentation
Markdown + Screenshots



📸 Screenshot Standards
Every lab in this portfolio follows a four-screenshot documentation standard:

Before — The default or empty state before configuration
During — The configuration in progress showing key settings
After — The completed and saved configuration
Verified — The System Log or verification confirming it worked

This standard ensures each lab tells a complete, auditable story.


🔗 Connect
LinkedIn: [Your LinkedIn URL]
Okta Community: [Your Okta Community Profile]
Email: [Your Email]


📅 Lab Journal
Date
Activity
Notes








Updated as labs are completed



Note: All labs are performed in a personal Okta developer org. No production systems, real user data, or client environments are used or represented in this portfolio.
