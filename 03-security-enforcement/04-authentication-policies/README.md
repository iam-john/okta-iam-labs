# Lab 12 — Authentication Policy and Rules

**Category:** Security Enforcement  
**Exam Domain:** Part II — Hands-On Configuration (25%)  
**Date Completed:** June 2026  
**Status:** ✅ Complete  

---

## Objective
Create an Authentication Policy with multiple rules
implementing risk-based access control for a specific
application, demonstrating correct rule priority order
and catch-all rule configuration.

---

## What I Configured
- Navigated to Security → Authentication Policies
- Created Finance App Security Policy
- Added three custom rules in priority order:
  1. Corporate Network Access (Password only)
  2. Remote Access Requires MFA (Password + Any factor)
  3. Catch-All Deny (blocks all unmatched requests)
- Discovered pre-existing default Allow rule at Priority 4
- Positioned custom Deny rule above default Allow rule
- Assigned policy to Salesforce.com application
- Documented before and after app policy assignment
- Verified rule priority order is correct

---

## Key Concepts Learned

**Authentication Policy Purpose:**
Controls what authentication requirements must be met
to access a SPECIFIC application. Each app can have
its own policy with unique requirements.

**Rule Evaluation — Top to Bottom:**
Okta evaluates rules from Priority 1 downward.
First matching rule wins — evaluation stops immediately.
Lower priority rules never fire if a higher one matches.

**The Three Rule Types in This Lab:**

Rule 1 — Corporate Network Access:
- Most specific — targets a specific network zone
- Allows password only — trusted network = lower risk
- Must be Priority 1 — specific rules go to the top

Rule 2 — Remote Access Requires MFA:
- Broader — catches all non-corporate network access
- Requires MFA — untrusted network = higher risk
- Priority 2 — below specific rule, above catch-all

Rule 3 — Catch-All Deny:
- Most general — catches everything not matched above
- Denies access — explicit security decision
- Priority 3 — must be above default Allow rule

**Pre-existing Default Rule Discovery:**
Okta Authentication Policies contain a built-in
default catch-all rule that cannot be deleted.
It typically allows access and sits at the bottom.
Custom Catch-All Deny rule was positioned above it
at Priority 3 to ensure unmatched requests are denied
before reaching the default Allow rule.

**Global Session Policy vs Authentication Policy:**
- Global Session Policy: how long Okta session lasts
- Authentication Policy: what to access specific app
- They work together — both must be satisfied
- Configured in completely different locations

**Deny Rule Behavior:**
When a Deny rule fires there is NO fallback.
No MFA prompt, no redirect, no alternative path.
Access is blocked completely — this is absolute.

---

## Policy Assignment Process
Apps must be assigned to an Authentication Policy.
Every app has a policy — either default or custom.

Assignment methods:
1. From policy: Applications tab → Add App
2. From app: Sign On tab → Authentication Policy → Edit

Both methods achieve the same result.
Documented with before/after screenshots showing
Salesforce moving from default to custom policy.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Specific rule below general rule | General rule fires first — specific never evaluated |
| Missing catch-all deny | Unmatched requests hit default Allow — security gap |
| Deny rule above Allow rules | Everyone denied — no one gets in |
| Wrong zone in Rule 1 | Corporate users never matched — always prompted MFA |
| Policy not assigned to app | App uses default policy — custom rules ignored |

---

## Real World Scenario
Client reports MFA is not triggering for remote users.
Investigation finds Remote MFA rule exists but is
Priority 1 while Corporate Network rule is Priority 2.
Corporate network rule catches everyone first —
remote users never reach the MFA rule.
Fix: Move Corporate Network rule to Priority 1.
This is the #1 Authentication Policy misconfiguration
in real enterprise deployments.

---

## Exam Tips
- Authentication Policy = per-app access requirements
- Global Session Policy = org-wide session management
- Most specific rules ALWAYS go to the top
- Catch-all rule ALWAYS goes to the bottom
- Deny rule = absolute — no fallback, no alternatives
- Default rule cannot be deleted — position above it
- Know the difference between Allow and Deny outcomes
- Policy must be ASSIGNED to app — creating it is not enough
- This was your weakest area at 33% — now you own it

---

*Lab completed as part of Okta Certified Professional
exam preparation — Okta Learning Grant program.*
