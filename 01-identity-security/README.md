# Identity Security

## Purpose
This section demonstrates how Azure identities are secured using Zero Trust principles.

The focus is on reducing identity attack surface, enforcing strong authentication, and
preventing unauthorized access before detection or response is required.

---

## Scope (Strictly Enforced)

### In Scope
- Microsoft Entra ID (Azure AD)
- Conditional Access policies
- Multi-Factor Authentication (MFA)
- Identity risk management
- Authentication hardening

### Explicitly Out of Scope
- Detection logic (see `05-detection-engineering`)
- Privileged role workflows (see `02-privileged-access-security`)
- Incident response and SOAR

---

## Capabilities Demonstrated

Projects in this section demonstrate the ability to:

### 1. Apply Zero Trust Identity Principles
- Enforce least privilege
- Verify explicitly
- Assume breach in identity design

### 2. Reduce Identity Attack Surface
- Require MFA for sensitive access
- Restrict legacy authentication
- Limit exposure of high-risk sign-in paths

### 3. Design Conditional Access Policies
- Align access decisions to user, device, and risk
- Balance security with usability
- Avoid policy sprawl and misconfiguration

---

## Execution Philosophy
Identity controls are designed to **prevent compromise**, not respond to it.
Configuration decisions prioritize clarity, simplicity, and auditability.

---

## Success Criteria
- Identity access paths are intentionally controlled
- MFA is enforced where it materially reduces risk
- Policies can be clearly explained and justified
