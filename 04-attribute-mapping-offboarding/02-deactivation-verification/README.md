# Lab 14 — Deactivate a User and Verify

**Category:** Attribute Mapping and Offboarding  
**Exam Domain:** Part II — Hands-On Configuration (20%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Execute a complete user offboarding workflow by
deactivating users, verifying access revocation,
and documenting the audit trail in the System Log.

---

## What I Configured
- Navigated to Directory → People
- Documented current access for John Finance and Mike HR
  before deactivation
- Deactivated John Finance via More Actions → Deactivate
- Deactivated Mike HR via More Actions → Deactivate
- Verified both users showing Deactivated status
- Confirmed OIE automatically revokes sessions on
  deactivation — no manual step required
- Verified deactivation events in System Log with
  timestamps for both users
- Reactivated both users after lab completion
- Authenticated both users via OKTA Verify AND Password for MFA

---

## Key Concepts Learned

**Deactivation vs Deletion:**
- Deactivated: account preserved, cannot authenticate
- Deleted: account permanently removed — unrecoverable
- Always deactivate first — never delete immediately
- Deactivated accounts preserved for audit purposes

**OIE Session Revocation Improvement:**
In Okta Identity Engine sessions are automatically
revoked upon user deactivation. In Classic Engine
this required a separate manual step.
This is an important OIE improvement for security —
access is terminated immediately and completely.

**User States After Deactivation:**
- Status changes to: Deactivated
- Cannot authenticate to Okta
- Cannot access any assigned applications
- Group memberships preserved
- Profile data preserved
- App assignments preserved (but access blocked)

**System Log as Compliance Evidence:**
Every deactivation event is recorded with:
- Exact timestamp of deactivation
- Actor (who performed the deactivation)
- Target (which user was deactivated)
- Outcome (success or failure)

This log entry is your compliance proof that access
was revoked — critical for SOX, HIPAA, and FedRAMP.

**Viewing Deactivated Users:**
Deactivated users are hidden from default People view.
Change Status filter to Deactivated to find them.
This prevents accidental reactivation of terminated users.

**The Complete Offboarding Checklist:**
1. Document current access before deactivating
2. Deactivate the user account
3. Verify sessions revoked (automatic in OIE)
4. Verify app access is blocked
5. Check System Log for deactivation timestamp
6. Save System Log screenshot as compliance evidence

---

## Offboarding vs Suspension

| Action | Use When | Access | Data |
|--------|----------|--------|------|
| Suspend | Temporary — leave of absence | Blocked | Preserved |
| Deactivate | Permanent — termination | Blocked | Preserved |
| Delete | Never immediately | Removed | Lost |

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Forgetting to deactivate | Terminated user retains access |
| Deleting instead of deactivating | Audit trail lost permanently |
| Not checking System Log | No compliance evidence |
| Wrong user deactivated | Legitimate user locked out |

---

## Real World Scenario
Employee terminated for cause at 2pm.
Security requires immediate access revocation.

Timeline:
2:00pm — HR notifies IT of termination
2:01pm — Admin navigates to user profile
2:02pm — User deactivated in Okta
2:02pm — OIE automatically revokes all sessions
2:03pm — System Log shows deactivation timestamp
2:04pm — Screenshot saved as compliance evidence

Total time: 4 minutes
Access window after termination: 2 minutes

Without Okta automation this process could take
hours or days across multiple systems.

---

## Exam Tips
- Navigation: Directory → People → More Actions → Deactivate
- Deactivated users hidden from default view — change filter
- OIE automatically revokes sessions on deactivation
- Always verify in System Log — timestamp is compliance proof
- Deactivate ≠ Delete — never delete immediately
- Suspend = temporary, Deactivate = permanent
- Reactivation restores access but may require password reset
- The exam requires THREE steps: Deactivate, Verify status,
  Verify in System Log

---

*Lab completed as part of Okta Certified Professional
exam preparation — Okta Learning Grant program.*
