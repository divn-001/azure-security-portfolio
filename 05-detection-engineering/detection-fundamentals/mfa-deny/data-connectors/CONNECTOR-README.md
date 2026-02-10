# Data Connector

## Required Connector
- **Microsoft Entra ID**
- **Table:** `SigninLogs`

This detection relies on Entra sign-in telemetry to identify explicit MFA deny events during interactive sign-ins.

## Quick validation
```kql
SigninLogs | where TimeGenerated > ago(24h) | take 5


