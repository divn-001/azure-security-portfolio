# Explicit MFA Deny Detection

## Overview

This detection is designed to identify repeated **explicit MFA denial actions** by a user within a short time window.

Explicit MFA denials occur when a user actively rejects an MFA prompt (for example, denying a number match request). While a single denial can be benign, repeated denials in a short interval may indicate that an attacker has valid credentials and is attempting MFA fatigue or prompt abuse.

This detection focuses on **user-driven MFA denial behavior**, not general authentication failures.

---

## Security Objective

The objective of this detection is to identify users who repeatedly **explicitly deny MFA prompts**, which may indicate:

- Ongoing credential compromise
- MFA fatigue attempts
- An attacker triggering MFA prompts that the user does not recognize

Repeated explicit denials elevate user risk and warrant investigation, even if no successful authentication occurs.

---

## Data Source

- **Table:** `SigninLogs`
- **Plane:** Identity (Microsoft Entra ID)

This detection relies on Microsoft Entra sign-in telemetry and evaluates MFA-related authentication outcomes recorded during interactive sign-ins.

---

## Detection Logic (High-Level)

The detection looks for:

- MFA authentication attempts where the user **explicitly denies** the MFA prompt
- Multiple such denials by the **same user principal name**
- A defined frequency threshold within a short time window

Example logic characteristics:
- Explicit MFA denial signals (e.g. number match deny / strong authentication failure during MFA)
- Count-based threshold (e.g. 5 denials within 15 minutes)
- Grouped by user principal name

---

## Noise Reduction

To reduce false positives from accidental or one-off denials, the detection:

- Requires **multiple explicit denials** within a short interval
- Does not trigger on single MFA failures

This helps distinguish normal user behavior from sustained suspicious activity.

---

## Scope

- **Users:** All users
- **Sign-in type:** Interactive sign-ins that involve MFA

This detection is intentionally broad to surface early indicators of compromise across the tenant.

---

## Severity

**Medium**

The alert indicates potentially malicious activity but does not confirm account compromise. Investigation is required to determine intent and impact.

---

## Out of Scope

This detection does **not** attempt to identify:

- Password brute-force attacks
- Password spray attacks
- MFA timeouts or non-responses
- Non-interactive sign-in failures
- Misconfigured Conditional Access policies

Those scenarios are better addressed by separate, purpose-built detections.

---

## Expected Analyst Actions

When this alert fires, analysts should consider:

- Contacting the user to validate MFA prompt legitimacy
- Reviewing recent sign-in locations, devices, and IP addresses
- Checking for follow-on activity such as successful sign-ins or role changes
- Assessing whether additional protections (e.g. sign-in risk policies) should be applied

---

## Notes

This detection is intended as a **behavioral signal**, not a definitive compromise indicator. It is most effective when combined with additional identity and sign-in analytics.
