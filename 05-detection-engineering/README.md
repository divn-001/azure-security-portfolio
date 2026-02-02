# Detection Engineering (Microsoft Sentinel)

## Purpose
This section demonstrates detection engineering using Microsoft Sentinel.

The focus is on designing, implementing, and tuning **high-fidelity security detections**
that reduce SOC alert fatigue and improve incident response outcomes.

This is an execution-focused portfolio area showcasing real detection engineering decisions,
not a theoretical overview.

---

## Scope (Strictly Enforced)

### In Scope
- Microsoft Sentinel
- Log Analytics workspace design (security telemetry only)
- Custom analytics rule engineering (KQL)
- Alert severity modeling
- Detection tuning and validation
- SOC workflow alignment
- Limited, safe automation (Logic Apps)

### Explicitly Out of Scope
- Identity architecture (see `01-identity-security`)
- Privileged access configuration (see `02-privileged-access-security`)
- Network security architecture
- Governance / Azure Policy (see `04-governance-and-landing-zones`)
- Defender for Cloud posture management (see `03-cloud-posture-management`)

This section focuses **only** on detection engineering.

---

## Capabilities Demonstrated

Projects in this section demonstrate the ability to:

### 1. Design a Minimal, Cost-Aware Sentinel Architecture
- Deploy Sentinel using a dedicated Log Analytics workspace
- Ingest only high-value security telemetry
- Configure intentional log retention
- Avoid unnecessary diagnostic and data sources

### 2. Engineer Custom Analytics Rules Aligned to Threat Behavior
- Replace low-signal default rules with custom detections
- Build KQL-based analytics aligned to attacker techniques
- Assign alert severity based on business impact
- Ensure every alert has a defined SOC response path

### 3. Build Identity-Centric Detections
- Correlate sign-in risk, authentication success, and privilege level
- Suppress expected or low-risk behavior
- Escalate only when identity compromise would be impactful

### 4. Align Alerts with SOC Workflow
- Define a clear severity model (High / Medium / Low)
- Map detections to investigation steps and response actions
- Eliminate alerts without a clear owner or response

### 5. Apply Targeted, Low-Risk Automation
- Identify high-frequency, low-risk alerts suitable for automation
- Use Logic Apps for enrichment or response
- Attach automation directly to relevant analytics rules

### 6. Validate, Tune, and Iterate
- Safely simulate detection scenarios
- Trigger and validate analytics rules
- Tune thresholds, suppression, and severity
- Iterate based on observed outcomes

---

## Execution Philosophy

Work in this section follows a consistent detection engineering lifecycle:

1. Define the detection objective
2. Implement the detection in Sentinel
3. Validate using simulated or controlled activity
4. Tune to reduce noise and false positives
5. Capture evidence, decisions, and trade-offs

Documentation reflects **completed work**, not planned or hypothetical configurations.

---

## Success Criteria

This section is considered complete when:

- Core threat scenarios are covered by custom detections
- Alert volume is controlled and intentional
- Every alert has a defined SOC response
- Automation demonstrably reduces analyst workload
- Detection logic and design decisions can be clearly explained in interviews
