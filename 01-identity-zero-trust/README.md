# Identity & Zero Trust Engineering

## Objective
Design and implement a **risk-based Zero Trust identity architecture** in Azure that reduces credential-based attacks while maintaining usability.

This project focuses on **preventing identity incidents** rather than responding to them.

## Scope
**In scope:**
- Azure Entra ID (Azure AD)
- Conditional Access (risk-based)
- Multi-Factor Authentication
- Privileged Identity Management (PIM)
- Break-glass access strategy

**Out of scope:**
- On-prem AD integration
- Third-party IdP solutions

## Architecture Summary
The identity model follows Zero Trust principles:
- Verify explicitly
- Enforce least privilege
- Assume breach

Access decisions are based on:
- User risk
- Sign-in risk
- Device state
- Role sensitivity

## Lab Implementation Plan
- Configure baseline Conditional Access policies
- Implement risk-based MFA enforcement
- Configure PIM for administrative roles
- Create and secure break-glass accounts
- Log identity events to Microsoft Sentinel

## Threats Addressed
- Credential phishing
- MFA fatigue attacks
- Token replay
- Excessive standing privileges

## Expected Outcomes
- Reduced identity-related SOC alerts
- Clear separation between user and admin access
- Improved auditability and control over privileged actions

## Validation
Validation will be performed by:
- Simulated risky sign-ins
- Privilege elevation tests
- Conditional Access policy evaluation
- Sentinel alert verification

---
