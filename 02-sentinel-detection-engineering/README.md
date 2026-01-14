# Sentinel Detection Engineering

## Purpose
This section focuses on **detection engineering using Microsoft Sentinel**.

The goal is to design, implement, and tune **high-fidelity security detections** that reduce SOC alert fatigue and improve incident response outcomes.

This is an **execution-focused lab**, not a theoretical overview.

---

## Scope (Strictly Enforced)

### In Scope
- Microsoft Sentinel
- Log Analytics workspace design (security telemetry only)
- Analytics rule engineering (KQL)
- Alert severity modeling
- Detection tuning and validation
- SOC workflow alignment
- Limited, safe automation (Logic Apps)

### Explicitly Out of Scope
- Identity architecture (covered in Section 1)
- Network security architecture (covered in Section 3)
- Governance / Azure Policy (covered in Section 5)
- Defender for Cloud posture management (covered in Section 4)

This section focuses **only** on detection engineering.

---

## Engineering Objectives

### Objective 1: Deploy a Minimal, Cost-Aware Sentinel Architecture
Design a Sentinel deployment that ingests **only high-value security telemetry**.

**Tasks**
- Deploy Sentinel using a dedicated Log Analytics workspace
- Enable only required data sources:
  - Entra ID sign-in logs
  - Entra ID audit logs
  - Azure Activity Logs
- Configure intentional log retention
- Avoid unnecessary diagnostic settings

---

### Objective 2: Engineer Custom Analytics Rules for Core Threat Scenarios
Replace default analytics rules with **engineered detections** aligned to attacker behavior.

**Threat Scenarios**
1. Risky sign-in with successful authentication
2. Privileged role misuse
3. Suspicious Azure control-plane activity

**Tasks**
- Review and disable low-signal default rules
- Create custom KQL analytics rules per scenario
- Assign severity based on **business impact**
- Ensure each alert has a defined SOC response

---

### Objective 3: Build an Identity-Centric Detection Model
Engineer detections that escalate **only when identity compromise would matter**.

**Tasks**
- Correlate sign-in risk, authentication success, and privilege level
- Suppress expected or low-risk behavior
- Escalate only when risk intersects with privilege

---

### Objective 4: Engineer Alert Severity and SOC Workflow
Ensure alerts are meaningful, actionable, and consistent.

**Tasks**
- Define a clear severity model (High / Medium / Low)
- Map each detection to:
  - Investigation steps
  - Expected response actions
- Eliminate alerts without a response path

---

### Objective 5: Automate Low-Risk, High-Frequency Responses
Reduce SOC toil through **safe, targeted automation**.

**Tasks**
- Identify at least one low-risk detection suitable for automation
- Build a Logic App playbook to enrich or respond
- Attach automation to the relevant analytics rule

---

### Objective 6: Validate, Tune, and Iterate
Continuously improve detection quality through controlled testing.

**Tasks**
- Safely simulate detection scenarios
- Trigger and validate each rule
- Tune thresholds, suppression, and severity
- Iterate based on observed outcomes

---

## Execution Approach
Work is performed in the following order:
1. Define the detection objective
2. Implement the detection in Sentinel
3. Validate with simulated activity
4. Tune to reduce noise
5. Capture evidence and decisions

Documentation reflects **completed work**, not planned work.

---

## Success Criteria
This section is considered complete when:
- All core threat scenarios are covered by custom detections
- Alert volume is controlled and intentional
- Each alert has a clear SOC response
- Automation reduces analyst workload
- Detection logic can be clearly explained in interviews

---
