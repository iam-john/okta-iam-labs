# Lab 07 — Set Up Lifecycle Management (Provisioning)

**Category:** Application Setup with OIN  
**Exam Domain:** Part II — Hands-On Configuration (30%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Configure automated user provisioning connecting Okta 
to Salesforce to enable the joiner/mover/leaver 
lifecycle management workflow.

---

## What I Configured
- Navigated to Salesforce.com → Provisioning tab
- Clicked Configure API Integration
- Enabled API Integration checkbox
- Explored OAuth credential requirements
- Identified that To App settings require successful
  API connection before becoming available
- Documented the complete provisioning setup process

---

## Environment Note
A live Salesforce org with admin credentials is required 
to complete the API connection. In this developer org 
environment the OAuth authentication could not be 
completed. The configuration process was fully explored 
and documented.

---

## Key Concepts Learned

**What Provisioning Does:**
Automates user account management in connected apps.
When enabled Okta automatically:
- Creates user accounts when assigned to the app
- Updates user attributes when Okta profile changes
- Deactivates accounts when user is removed or deactivated

**Two Provisioning Directions:**
- To App: Okta pushes changes TO the application
- From App: Application imports users INTO Okta

**To App Settings (require active API connection):**
- Create Users: auto-create app account on assignment
- Update User Attributes: sync profile changes to app
- Deactivate Users: auto-deactivate on removal
- Sync Password: push Okta password to app (optional)

**API Integration Requirements:**
Salesforce provisioning uses OAuth 2.0 for the API 
connection. Required credentials:
- OAuth Consumer Key (from Salesforce Connected App)
- OAuth Consumer Secret (from Salesforce Connected App)
- Or use Authenticate with Salesforce.com button for
  automatic OAuth token generation

**The Joiner/Mover/Leaver Automation Chain:**
When fully configured the workflow is:
New user assigned to app group
        ↓
Group rule fires → user added to Salesforce group
        ↓
Provisioning creates Salesforce account automatically
        ↓
User attribute changes in Okta sync to Salesforce
        ↓
User deactivated in Okta → Salesforce account deactivated
        ↓
Zero manual steps — full automation

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| API integration not enabled | No provisioning — all manual |
| Wrong OAuth credentials | Connection fails — provisioning blocked |
| Create Users not enabled | Users assigned but no app account created |
| Deactivate Users not enabled | Terminated users keep app access |
| To App not configured | Okta changes don't sync to app |

---

## Real World Value
Provisioning is one of the highest value Okta features 
for enterprise clients. Manual user management across 
50+ applications is impossible to maintain accurately. 
Automated provisioning eliminates orphaned accounts, 
reduces IT workload, and ensures immediate access 
revocation on termination.

---

## Exam Tips
- Provisioning tab location: App → Provisioning
- Must enable API integration before To App settings appear
- To App = Okta pushes to app (most important direction)
- From App = app imports to Okta
- Know the three main To App actions: Create, Update, Deactivate
- Deactivating a user in Okta triggers app deactivation 
  only if Deactivate Users is enabled in provisioning

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
