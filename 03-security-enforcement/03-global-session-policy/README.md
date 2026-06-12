# Lab 11 — Global Session Policy Rule

**Category:** Security Enforcement  
**Exam Domain:** Part II — Hands-On Configuration (25%)  
**Date Completed:** June 2026  
**Status:** ✅ Complete  

---

## Objective
Create a Global Session Policy rule that controls 
session lifetime and re-authentication requirements,
implementing tiered session management by user group.

---

## What I Configured
- Navigated to Security → Global Session Policy
- Reviewed existing Default rule and Standards rule
  from Okta grant program
- Created Executive Session Rule for Management-Team:
  - Maximum session lifetime: 12 hours
  - Re-authenticate after inactivity: 2 hours
  - MFA required: Password + Any factor
- Verified rule priority order:
  1. Executive Session Rule (Priority 1)
  2. Standards Rule (Priority 2)
  3. Default Rule (catch-all, last)
- Verified session policy applied via System Log

---

## Key Concepts Learned

**What Global Session Policy Controls:**
- How long a user's Okta session stays active
- When re-authentication is required
- Whether persistent sessions (remember me) are allowed
- MFA requirements for session establishment

**What Global Session Policy Does NOT Control:**
- Which apps a user can access (Authentication Policy)
- Which authenticators users enroll in (Enrollment Policy)
- Password complexity (Password Policy)

**Critical Distinction — Session vs Authentication Policy:**
- Global Session Policy = controls the OKTA SESSION
  (how long you stay logged into Okta)
- Authentication Policy = controls APP ACCESS
  (what you need to access a specific application)
  
These two work together but serve different purposes.
A user can have an active Okta session but still be
challenged when accessing a high-security app.

**Rule Priority Logic:**
Rules evaluate top to bottom — first match wins.
Executive rule is Priority 1 because it is more 
specific (targets a specific group) than the general
Standards rule which applies to all users.

**Session Lifetime vs Inactivity Timeout:**
- Session lifetime: maximum time regardless of activity
- Inactivity timeout: expires session after idle period
- Both apply — whichever triggers first ends the session

---

## Real World Scenario
A CTO complains their session expires too quickly.
Root cause: Standard 8-hour session rule firing before
the Executive rule because of wrong priority order.
Fix: Move Executive rule to Priority 1.
This is one of the most common Global Session Policy
misconfiguration issues in real deployments.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Executive rule below Standard rule | Executives get standard sessions — priority wrong |
| No inactivity timeout | Unattended sessions stay open — security risk |
| Session too short | Users constantly re-authenticating — poor UX |
| Session too long | Increased window for session hijacking |
| No catch-all default rule | Users with no matching rule get no session policy |

---

## Exam Tips
- Navigation: Security → Global Session Policy
- Global Session Policy ≠ Authentication Policy
- Session policy = how long in Okta
- Auth policy = what to access specific app
- Most specific rules always above general rules
- Default rule is always last — never move it above others
- Inactivity timeout and session lifetime work independently
- Know what happens when session policy conditions 
  are not met: user is prompted to re-authenticate

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
