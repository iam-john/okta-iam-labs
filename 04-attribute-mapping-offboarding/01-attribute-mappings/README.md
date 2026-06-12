# Lab 13 — Define Attribute Mappings (Okta to App)

**Category:** Attribute Mapping and Offboarding  
**Exam Domain:** Part II — Hands-On Configuration (20%)  
**Date Completed:** June 2026  
**Status:** ✅ Complete  

---

## Objective
Configure attribute mappings to push user profile data
from Okta to connected applications, ensuring apps
receive correct user information during provisioning
and authentication.

---

## What I Configured
- Navigated to Directory → Profile Editor → Apps tab
- Located Salesforce.com mapping interface
- Identified two mapping directions:
  - Salesforce → Okta (import direction)
  - Okta → Salesforce (provisioning direction)
- Explored mapping table structure and edit options
- Discovered full SCIM mapping requires active API
  connection — documented limitation
- Located SAML attribute statements in Test SAML
  Application under Show Legacy Configuration
- Verified three attribute mappings configured in Lab 06:
  - firstName → user.firstName
  - lastName → user.lastName
  - department → user.department

---

## Key Concepts Learned

**Two Types of Attribute Mapping in Okta:**

1. SAML Attribute Statements:
   - Used with SAML SSO integrations
   - Sends user data inside the SAML assertion
   - Configured in app Sign On tab
   - Application receives data at authentication time

2. SCIM Provisioning Mappings:
   - Used with provisioning-enabled integrations
   - Pushes user data when account is created/updated
   - Configured in Profile Editor → Apps
   - Requires active API connection to the app

**Mapping Directions:**
- Okta → App (To App): pushes data to the application
  Used for: provisioning, keeping app data current
- App → Okta (From App): imports data from application
  Used for: importing existing app users into Okta

**Profile Editor — Apps Tab:**
Shows all connected application profile schemas.
Each app has its own profile with mappable attributes.
Left column = Okta attribute
Right column = App attribute
Arrow direction = data flow

**OIE Discovery — Legacy Configuration:**
In Okta Identity Engine SAML attribute statements
for custom app integrations appear under
'Show Legacy Configuration' on the Sign On tab.
This differs from Classic Engine where attributes
appeared directly in the main configuration view.
Always check legacy configuration when attribute
statements are not immediately visible in OIE.

**Data Transformation with Expression Language:**
Attribute values can be transformed during mapping:
- Combine fields: user.firstName + ' ' + user.lastName
- Convert case: String.toUpperCase(user.department)
- Extract substring: user.login.substringBefore('@')

---

## Mapping Configuration Requirements

| Mapping Type | Requirements |
|-------------|-------------|
| SAML Attributes | App must support SAML — no API needed |
| SCIM Provisioning | Active API connection required |
| Profile Editor | App must be added to Okta org |

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Wrong attribute mapped | App receives incorrect user data |
| Missing required attribute | App account creation fails |
| Wrong mapping direction | Data flows wrong way |
| Apply on Create only | Updates never sync to app |
| Case mismatch in values | App rejects or misreads data |

---

## Real World Application
In enterprise deployments attribute mapping ensures:
- HR data flows correctly to all connected apps
- Department changes automatically update app permissions
- Employee IDs sync for compliance reporting
- Display names are formatted correctly per app requirements

---

## Exam Tips
- Profile Editor location: Directory → Profile Editor
- Apps tab shows all connected application schemas
- Two directions: To App (provisioning) and From App (import)
- SAML attributes appear in Sign On tab configuration
- In OIE check Show Legacy Configuration for SAML attributes
- Mapping requires active API connection for SCIM provisioning
- Know the difference between SAML attributes and SCIM mapping
- Apply on: Create and Update ensures ongoing sync

---

*Lab completed as part of Okta Certified Professional
exam preparation — Okta Learning Grant program.*
