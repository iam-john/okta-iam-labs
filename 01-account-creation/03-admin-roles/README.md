# Lab 03 — Assign Admin Roles

**Category:** Account Creation  
**Exam Domain:** User Lifecycle Management (27%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Assign standard administrator roles to users following 
least privilege principles to limit admin access to 
only what is necessary for each role.

---

## What I Configured
- Navigated to Security → Administrators
- Assigned Sarah IT as Help Desk Administrator
- Reviewed permissions included in each standard role
- Practiced removing and re-adding the role assignment
- Verified Sarah IT appeared in the Administrators list

---

## Key Concepts Learned

**Least Privilege for Admins** — not every IT staff 
member needs Super Admin access. Right-sizing admin 
permissions reduces insider threat risk and limits 
blast radius if an admin account is compromised.

**Standard Admin Roles:**
- Super Admin: full access to everything
- Org Admin: full org management except role assignments
- App Admin: manage specific applications only
- Group Admin: manage specific groups only
- Help Desk Admin: reset passwords, unlock accounts, clear sessions
- Read Only Admin: view everything, change nothing
- Report Admin: access reports and logs only

**Help Desk Admin specifically can:**
- Reset user passwords
- Unlock locked out accounts
- Clear active sessions
- View user profiles

**Help Desk Admin cannot:**
- Create or delete users
- Modify security policies
- Assign admin roles to others
- Access billing or org settings

---

## Why This Matters in Real Deployments
In enterprise environments the Help Desk team handles 
the majority of user support tickets. Giving them 
Super Admin access to reset a password is a massive 
over-privilege. Help Desk Admin gives them exactly 
what they need — nothing more.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Everyone is Super Admin | Single compromised account = full org takeover |
| Help Desk has no admin role | Cannot reset passwords — users locked out with no support |
| Wrong role assigned | Admin either can't do their job or has too much access |

---

## Exam Tips
- Navigation: Security → Administrators → Add Administrator
- Standard roles cannot be scoped to specific users — they apply org wide
- Custom roles + Resource Sets are needed for scoped admin access
- Know what Help Desk Admin can and cannot do — this is exam tested
- Admin roles can be assigned to users OR manually managed groups

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
