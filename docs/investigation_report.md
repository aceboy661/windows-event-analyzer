Investigation Report - Windows Event Analyzer

**Date:** October 30, 2026  
**Analyst:** Marlon Lonmon  
**Project:** Windows Event Analyzer

---

## Summary
The failed logon detector was executed against sample Windows Security logs. Multiple failed authentication attempts were identified.

---

## Findings

### Failed Logon Activity (Event ID 4625 style)
- 6 failed logon events detected
- Targeted accounts included: Administrator, admin, guest, and root
- Main source IP: 203.0.113.50
- Pattern is consistent with password spraying or brute-force activity

**Severity:** Medium-High

---

## Recommendation
- Block or monitor the source IP 203.0.113.50
- Review account lockout policies
- Correlate with successful logons and other security events

---

## Conclusion
The script successfully identified suspicious authentication activity. This project demonstrates practical Windows event log analysis skills relevant to SOC Tier 1 roles.
