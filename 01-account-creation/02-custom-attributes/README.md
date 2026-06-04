# Lab 02 — Create Custom Attributes

**Category:** Account Creation  
**Exam Domain:** User Lifecycle Management (27%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Extend the Okta user profile schema with custom attributes 
to store organization-specific data not included by default.

---

## What I Configured
- Audited existing schema before making changes
- Discovered costCenter already exists as a default attribute
- Created custom attribute: employeeID (string, Read-Write)
- Created custom attribute: clearanceLevel (string, Hidden)
- Updated test users with employeeID values

---

## Key Concepts Learned

**Profile Editor** is where the Okta user profile schema 
is managed. Changes here affect all users in the org.

**Custom Attributes** extend the default profile with 
organization-specific fields. Once created they appear 
on every user profile.

**User Permission levels:**
- Read-Write: user can view and edit their own value
- Read-Only: admin sets it, user can see but not change
- Hidden: completely invisible to users, admin only

**Pre-lab audit finding:** costCenter already existed in 
the default schema. Always audit before creating — 
duplicate attributes are not allowed as Okta will deny it.  

---

## Why clearanceLevel was set to Hidden
In federal and government contracting environments 
clearance classifications are sensitive. Users should 
not be able to see or reference their own clearance 
level in their profile settings. Hidden ensures only 
administrators can view and manage this field.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Read-Write on clearanceLevel | Users could modify their own clearance classification — major security risk |
| Required = Yes | Blocks creation of any user without a clearance level — breaks onboarding for non-cleared staff |
| Duplicate attribute | Data conflicts between two fields storing the same data |

---

## Exam Tips
- Profile Editor location: Directory → Profile Editor → User (default)
- Know the three permission levels and when to use each
- Read-Write = user self-service, Read-Only = admin managed, Hidden = system only
- Always check existing schema before adding new attributes

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
