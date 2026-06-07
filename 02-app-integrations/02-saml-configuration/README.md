# Lab 06 — Configure Custom SAML Integration

**Category:** Application Setup with OIN  
**Exam Domain:** Part II — Hands-On Configuration (30%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Build a custom SAML 2.0 application integration from 
scratch using Create App Integration, configure all 
required SAML fields, and add attribute statements.

---

## What I Configured
- Created custom SAML app: Test SAML Application
- Selected SAML 2.0 as sign-in method during setup wizard
- Configured Single Sign-On URL and Audience URI
- Set Name ID format to EmailAddress
- Previewed the raw SAML assertion XML
- Added three attribute statements:
  - firstName → user.firstName
  - lastName → user.lastName
  - department → user.department

---

## Key Concepts Learned

**Create App Integration vs Browse App Catalog:**
- Browse App Catalog = pre-built OIN integration
- Create App Integration = custom integration built manually
- Use custom when app is not in OIN or needs specific config

**Critical SAML Fields:**
- Single Sign-On URL: where Okta POSTs the assertion
- Audience URI (SP Entity ID): unique identifier for the SP
- Name ID Format: how the user is identified in the assertion
- Default Relay State: where user lands after SSO

**Attribute Statements:**
Send additional user data inside the SAML assertion.
The application receives these as part of authentication
and can use them for authorization or personalization.

**SAML Assertion XML Structure:**
- saml2:Issuer: Okta's identity as the IdP
- saml2:NameID: user identifier (email format)
- saml2:Conditions: assertion validity window
- saml2:AudienceRestriction: confirms intended SP
- saml2:AuthnStatement: authentication method used
- saml2:AttributeStatement: custom user attributes

**Advanced SAML Security Settings:**
- Response: Signed
- Assertion Signature: Signed
- Signature Algorithm: RSA-SHA256
- Digest Algorithm: SHA256

---

## OIN vs Custom SAML Comparison

| Feature | OIN Integration | Custom SAML |
|---------|----------------|-------------|
| Setup time | Minutes | Longer |
| Pre-validated | Yes | No |
| Flexibility | Limited | Full control |
| Maintenance | Okta/vendor | You |
| Best for | Known apps | Custom/legacy apps |

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Wrong SSO URL | Assertion sent to wrong endpoint — SSO fails |
| Wrong Audience URI | SP rejects assertion — entity ID mismatch |
| Wrong Name ID format | User not recognized in the app |
| Missing attributes | App missing required user data |

---

## Exam Tips
- Know the three SAML fields cold: SSO URL, Audience URI, Name ID
- Attribute statements = additional user data in the assertion
- Preview SAML Assertion shows the actual XML Okta will send
- Sign-on method selected during wizard cannot be changed after
- Custom SAML = Create App Integration, OIN = Browse App Catalog

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
