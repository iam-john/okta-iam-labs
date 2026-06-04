# Lab 01 — Create Users Manually

**Category:** Account Creation  
**Exam Domain:** User Lifecycle Management  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Manually create user accounts in Okta Universal Directory with correct profile attributes including department and title.

---

## What I Configured
- Created three users: John Finance, Sarah IT, Mike HR
- Set department and title attributes for each user
- Used real email addresses per Okta grant program instructions
- Resolved a password expired issue using admin password reset

---

## Key Concepts Learned

**Universal Directory** is Okta's central identity store. Every user, attribute, and group membership lives here. It is the foundation that all SSO, MFA, and lifecycle management builds on.

**User Profile Attributes** — the default profile includes firstName, lastName, email, username, department, and title. Department is critical because group rules reference it for automated access assignment.

**User States** — during this lab I encountered a real Password Expired state and resolved it using Resend Password Email, which triggered a branded password reset email from the Okta org (branded as Streamward).

---

## Screenshots

See screenshots folder for:
1. Add Person form showing required fields
2. Manual user creation process
3. Password expired troubleshooting scenario
4. Password reset email received
5. All three users showing Active status
6. Individual profile attributes for John, Sarah, and Mike

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Missing department attribute | Group rules won't fire — no automatic app access |
| Wrong username format | SSO name ID mismatch — login failures |
| No password set | User stuck in Provisioned state |

---

## Exam Tips
- Navigation: Directory → People → Add Person
- Know all user states: Active, Suspended, Locked Out, Password Expired, Deactivated
- Password Expired → Resend Password Email or Reset Password
- Locked Out → Unlock (does NOT reset the password)

---

*Lab completed as part of Okta Certified Professional exam preparation — Okta Learning Grant program.*
