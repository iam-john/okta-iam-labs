# Lab 04 — Create Groups and Group Rules

**Category:** Account Creation  
**Exam Domain:** User Lifecycle Management (27%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Create department groups and configure automated group 
rules using Okta Expression Language to eliminate manual 
group management at scale.

---

## What I Configured
- Created three groups: Finance-Team, IT-Team, HR-Team
- Created group rules using department attribute conditions
- Activated all three rules
- Verified users were automatically assigned to correct groups
- Tested automation by confirming group membership populated

---

## Key Concepts Learned

**Groups** are containers for users that drive access 
control. Every app assignment, policy condition, and 
admin scope in Okta can reference a group.

**Group Rules** automatically populate groups based on 
user attribute conditions. They use Okta Expression 
Language to evaluate attributes.

**Common Expression Language patterns:**
- user.department == "Finance"
- user.title == "Manager"
- String.stringContains(user.title, "Director")
- user.userType == "Employee"

**Rule Evaluation:** Rules run automatically when:
- A new user is created
- A user attribute is updated
- A rule is manually activated

**The automation chain this enables:**
New user created → department attribute set → 
group rule fires → user added to group → 
group assigned to apps → user gets app access automatically

---

## Why This Matters in Real Deployments
In enterprise environments with thousands of users, 
manual group management is impossible to maintain 
accurately. Group rules ensure access is always 
consistent with the user's current role — no 
orphaned access, no missed assignments.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Rule not activated | Users never get added — rule exists but does nothing |
| Wrong attribute name | Rule never matches — check exact spelling and case |
| Rule assigned to wrong group | Users get incorrect app access |
| Case sensitivity mismatch | "finance" vs "Finance" — rule won't fire |

---

## Exam Tips
- Navigation: Directory → Groups → Rules → Add Rule
- Rules must be ACTIVATED — creating a rule does not activate it
- Expression Language is case sensitive — Finance ≠ finance
- Group rules only apply to Okta-mastered users not AD-mastered users
- Rule-managed groups cannot have admin roles assigned to them

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
