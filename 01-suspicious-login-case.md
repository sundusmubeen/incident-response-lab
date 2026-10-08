# Lab 01 — Suspicious login case (training)

**Scenario type:** Account compromise suspicion  
**Environment:** Training notes / simulated alert  
**Goal:** Walk a junior IR path from alert to lessons learned

## 1. Detection and analysis

**Alert (example):** Multiple failed logins followed by a successful login from an unusual location/IP for a standard user account.

**Questions I ask first:**
- Who is the user and what systems do they access?
- Is the IP/location consistent with past behaviour?
- Were MFA challenges passed or bypassed?
- Is there follow-on activity (new mail rules, file access, privilege changes)?

**Working severity:** Medium (possible account misuse; escalate if admin or sensitive data access appears).

## 2. Containment

Short-term actions for the lab scenario:

1. Disable or force-reset the affected account credentials.
2. End active sessions where the platform allows it.
3. Preserve relevant logs (auth, VPN, email, endpoint) before cleanup.
4. Block or monitor the suspicious IP if appropriate.

Avoid wiping the host until evidence needed for analysis is collected.

## 3. Eradication and recovery

1. Confirm no persistence (new forward rules, API tokens, scheduled tasks, local accounts).
2. Reset passwords / rotate tokens for the user and any shared secrets that may have been exposed.
3. Re-enable access only after checks pass.
4. Notify the user and remind them about phishing / credential hygiene if that was the likely entry.

## 4. Lessons learned

| Gap | Improvement |
| --- | --- |
| Unusual location not alerted early | Tune geo/IP anomaly alerts |
| Session revoke process unclear | Document exact steps per system |
| Evidence collection ad hoc | Keep a short IR checklist |

## ATT&CK (high level)

| Suspected activity | Tactic | Technique (example) |
| --- | --- | --- |
| Credential guessing / reuse | Credential Access | Brute Force (T1110) / Valid Accounts (T1078) |
| Access after login | Initial Access | Valid Accounts (T1078) |

## What I learned

- Contain first, then clean — but keep logs.
- Severity depends on account role and data touched, not only the alert name.
- A one-page timeline (alert → actions → outcome) is enough for most junior write-ups.
