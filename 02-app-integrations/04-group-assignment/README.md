# Lab 08 — Group-Based App Assignment

**Category:** Application Setup with OIN  
**Exam Domain:** Part II — Hands-On Configuration (30%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Assign a group to an application and verify that group 
members automatically receive app access demonstrating 
scalable access management.

---

## What I Configured
- Navigated to Salesforce.com → Assignments tab
- Clicked Assign → Assign to Groups
- Assigned Finance-Team group to Salesforce.com
- Verified Finance-Team appears in Groups filter
- Verified John Finance shows Salesforce.com in his
  application assignments automatically

---

## Key Concepts Learned

**Group Assignment vs Individual Assignment:**
- Individual: assign one user at a time — does not scale
- Group: assign once — all current and future members
  get access automatically

**The Automation This Enables:**
New employee joins Finance department
        ↓
Department attribute triggers group rule
        ↓
User added to Finance-Team automatically
        ↓
Finance-Team assigned to Salesforce
        ↓
User gets Salesforce access automatically
        ↓
Zero manual steps — zero IT tickets

**Verification Steps:**
Always verify group assignment worked two ways:
1. Check Groups filter in Assignments tab
2. Check individual user profile — confirm app appears

**Self Service:**
The Assignments tab also shows a Self Service panel.
When enabled users can request access to apps themselves
through their Okta dashboard — adding a governance layer.

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Assign to People instead of Groups | Doesn't scale — manual work for every user |
| Wrong group assigned | Wrong users get access |
| Group rule not active | Group never populates — no one gets access |
| Provisioning not enabled | SSO works but no app account created |

---

## Exam Tips
- Navigation: App → Assignments → Assign → Assign to Groups
- Always verify BOTH the group assignment AND individual user access
- Group assignment = scalable, Individual = manual and error prone
- The exam will ask you to assign a group AND verify a user can access
- Don't forget the verification step — it is required on the exam

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
