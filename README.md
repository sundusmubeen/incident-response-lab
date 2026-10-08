# Incident Response Lab Notes

Educational notes practising a basic incident response workflow aligned with NIST SP 800-61 style phases: preparation, detection and analysis, containment, eradication, recovery, and lessons learned.

## What this repo shows

- How I structure an incident from first alert to close-out
- Clear evidence notes and decision points
- Practical containment and recovery ideas suitable for a junior / graduate role

## Sample case

See [`labs/01-suspicious-login-case.md`](labs/01-suspicious-login-case.md).

| Phase | What I practise |
| --- | --- |
| Detection & analysis | Triage alerts, confirm scope, classify severity |
| Containment | Limit blast radius without destroying evidence |
| Eradication & recovery | Remove cause, restore service, verify |
| Lessons learned | Short post-incident notes for next time |

## References

- NIST SP 800-61 (Computer Security Incident Handling Guide)
- NIST Cybersecurity Framework (Respond / Recover functions)
- MITRE ATT&CK for describing suspected activity

## Disclaimer

Training scenario only. No real organisations or production systems were involved.
