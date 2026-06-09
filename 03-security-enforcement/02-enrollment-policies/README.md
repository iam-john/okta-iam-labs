# Lab 10 — Configure Enrollment Policies

**Category:** Security Enforcement  
**Exam Domain:** Part II — Hands-On Configuration (25%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Configure MFA enrollment policies that control which 
authenticators users must enroll in and when, creating 
tiered security requirements by user group.

---

## What I Configured
- Navigated to Security → Authenticators → Enrollment tab
- Reviewed the default enrollment policy
- Created a new enrollment policy with custom rules
- Configured authenticator requirements:
  - Okta Verify: Required
  - Email: Optional
  - Phone: Disabled
- Set enrollment period to prompt during sign-in
- Verified policy priority order

---

## Key Concepts Learned

**Three Enrollment States:**
- Required: user MUST enroll before accessing Okta
- Optional: user CAN enroll but is not forced
- Disabled: completely hidden — user cannot see or use it

**Critical Distinction:**
- Disabled ≠ Inactive
- Disabled = hidden from users in enrollment flow
- Inactive = turned off org-wide in Authenticators page

**Policy Evaluation:**
Enrollment policies evaluate top to bottom.
First matching policy wins — same as all Okta policies.
More specific policies must be above general ones.

**Enrollment Period Options:**
- Prompt during sign-in until enrolled
- Prompt at next sign-in only once
- Allow user to skip (not recommended for Required)

**Why This Matters:**
Setting Okta Verify to Required ensures 100% MFA 
coverage. Optional means many users will skip it 
leaving accounts vulnerable to credential attacks.

---

## Tiered Enrollment Strategy for Enterprise

| User Group | Okta Verify | FIDO2 | Email | Phone |
|-----------|-------------|-------|-------|-------|
| Executives | Required | Required | Optional | Disabled |
| Standard Staff | Required | Optional | Optional | Optional |
| Contractors | Required | Disabled | Required | Disabled |
| Help Desk | Required | Optional | Optional | Optional |

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| All authenticators Optional | Low MFA adoption — security risk |
| Required authenticator not available | Users blocked — cannot enroll |
| Wrong policy priority | Wrong policy applies to users |
| Enrollment period too permissive | Users skip indefinitely |

---

## Exam Tips
- Navigation: Security → Authenticators → Enrollment tab
- Required = must enroll, Optional = can enroll, 
  Disabled = completely hidden
- Policy order matters — top to bottom evaluation
- Enrollment policies control WHAT users enroll in
- Authentication policies control WHAT is required to 
  access a specific app
- These two policies work together but are separate

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
