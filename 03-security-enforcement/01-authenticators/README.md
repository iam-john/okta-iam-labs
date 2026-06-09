# Lab 09 — Add and Remove Authenticators

**Category:** Security Enforcement  
**Exam Domain:** Part II — Hands-On Configuration (25%)  
**Date Completed:** May 2026  
**Status:** ✅ Complete  

---

## Objective
Manage authenticators in Okta by adding, configuring, 
and deactivating authentication methods to control 
what users can use to verify their identity.

---

## What I Configured
- Navigated to Security → Authenticators
- Reviewed all currently active authenticators
- Added and configured Okta Verify authenticator
- Configured Email authenticator
- Practiced deactivating Phone/SMS authenticator
- Reactivated Phone authenticator
- Documented all authenticator states and their meanings

---

## Key Concepts Learned

**Authenticator States:**
- Active: available for enrollment and use
- Inactive: disabled — users cannot enroll or use it
- Not Set Up: never configured in this org

**Authenticator Types by Factor Category:**
- Something you know: Password, Security Question
- Something you have: Okta Verify, Phone, Email, 
  Hardware Key
- Something you are: Biometrics via Okta Verify FastPass

**Okta Verify Configuration Options:**
- Push notification: tap to approve
- OTP: 6-digit rotating code
- FastPass: passwordless device-bound auth
- Number challenge: prevents push fatigue attacks

**Security Considerations by Authenticator:**
- FIDO2/WebAuthn: highest security, phishing resistant
- Okta Verify Push: strong, good UX, push fatigue risk
- Email: medium security, out of band
- SMS/Phone: weak, vulnerable to SIM swapping
- Security Question: recovery only, not primary MFA

**Deactivate Before Delete:**
Same pattern as applications — authenticators must be 
deactivated before additional options become available.

---

## Authenticator Security Ranking

| Authenticator | Security Level | Phishing Resistant |
|--------------|---------------|-------------------|
| FIDO2/WebAuthn | Highest | Yes |
| Okta FastPass | Very High | Yes |
| Okta Verify Push | High | No |
| Okta Verify OTP | Medium-High | No |
| Email OTP | Medium | No |
| SMS/Phone | Low | No |
| Security Question | Very Low | No |

---

## What Would Break If Misconfigured

| Misconfiguration | Impact |
|-----------------|--------|
| Disabling all authenticators | Users cannot complete MFA |
| Enabling SMS only | Low security — SIM swap vulnerability |
| Not enabling number challenge | Push fatigue attack risk |
| Removing active authenticator users rely on | Users locked out |

---

## Exam Tips
- Navigation: Security → Authenticators
- Adding activates org-wide — all enrollment policies can use it
- Deactivating removes it from all enrollment policies
- Know security ranking of each authenticator
- FIDO2 = phishing resistant = hardware protected assurance level
- Number challenge prevents push bombing attacks
- Cannot delete authenticators users are actively enrolled in

---

*Lab completed as part of Okta Certified Professional 
exam preparation — Okta Learning Grant program.*
