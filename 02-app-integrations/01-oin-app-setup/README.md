# Lab 05 — Add an App from the OIN (Salesforce)

**Category:** Application Setup with OIN  
**Exam Domain:** Part II — Hands-On Configuration (30%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Add a pre-built application integration from the Okta 
Integration Network (OIN) using SAML 2.0 as the 
sign-on method.

---

## What I Configured
- Located Salesforce.com in the OIN via Browse App Catalog
- Selected Sandbox as the instance type
- Configured SAML 2.0 as the sign-on method
- Verified SAML metadata details including Sign on URL,
  Sign out URL, Issuer, and Signing Certificate
- App showing Active status after setup

---

## Troubleshooting Encountered
Initial setup selected SWA (Secure Web Authentication) 
instead of SAML 2.0. The sign-on method is selected on 
the Sign-On Options tab during setup — not General Settings.

**Resolution:** Deactivated the incorrectly configured app, 
deleted it after deactivation became available, then 
recreated with SAML 2.0 correctly selected.

**Key lesson:** Sign-on method cannot be changed after 
app creation. Always verify the correct method before 
clicking Done.

---

## Key Concepts Learned

**OIN (Okta Integration Network)** contains 8,000+ 
pre-built app integrations. Always check OIN before 
building a custom integration — OIN integrations are 
pre-validated and maintained by Okta or the vendor.

**Browse App Catalog vs Create App Integration:**
- Browse App Catalog = use a pre-built OIN integration
- Create App Integration = build a custom integration
- The exam specifically says "from the OIN" = Browse App Catalog

**SAML Metadata fields:**
- Metadata URL: contains all IdP info for the SP to configure
- Sign on URL: where Okta posts the SAML assertion
- Sign out URL: where users go after logging out
- Issuer: Okta's unique identifier as the IdP
- Signing Certificate: SP uses this to verify assertions came from Okta

**Instance Types:**
- Sandbox: for developer/test orgs and Salesforce Developer Edition
- Production: for real enterprise Salesforce deployments

**Deactivate before Delete:**
In Okta apps must be deactivated before the delete 
option becomes available. This prevents accidental 
deletion of active integrations.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Wrong sign-on method (SWA vs SAML) | SSO won't work — users prompted for separate credentials |
| Wrong instance type (Production vs Sandbox) | SAML endpoints point to wrong Salesforce environment |
| Missing signing certificate | SP cannot verify assertion — SSO rejected |

---

## Exam Tips
- "Add app from OIN" = Browse App Catalog not Create App Integration
- SAML 2.0 must be selected during setup — cannot change after
- Deactivate first then Delete becomes available
- Know the five SAML metadata fields and their purpose
- Sandbox = test environments, Production = live deployments

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
