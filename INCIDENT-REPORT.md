# Incident Report: Wazuh SIEM Alert Investigation

## Incident Title

Suspicious Endpoint Activity Detected in Wazuh SIEM

---

## Report Type

Lab-based SOC investigation report

---

## Environment

| Component | Details |
|---|---|
| SIEM | Wazuh |
| Endpoint | Linux / Windows lab endpoint |
| Agent | Wazuh Agent |
| Analyst | Albin John Sebastian |
| Report Status | Lab report / training scenario |

---

## Incident Summary

Wazuh generated an alert from a monitored endpoint. The alert was reviewed from the Wazuh dashboard as part of a SOC triage workflow.

The purpose of this investigation was to validate endpoint visibility, review alert details, determine potential risk, and document recommended remediation steps.

This report represents a controlled lab investigation and is intended to demonstrate basic SOC analysis, documentation, and response planning.

---

## Detection Source

| Field | Value |
|---|---|
| Detection Tool | Wazuh SIEM |
| Alert Source | Wazuh Agent |
| Event Type | Endpoint security event |
| Alert Category | Authentication / File integrity / Vulnerability / System event |
| Severity | To be updated based on actual alert |
| Status | Under review |

---

## Timeline

| Time | Activity |
|---|---|
| T1 | Wazuh agent reported endpoint activity |
| T2 | Alert appeared in Wazuh dashboard |
| T3 | Alert details were reviewed |
| T4 | Affected endpoint and event source were identified |
| T5 | Risk and remediation steps were documented |

---

## Alert Details

| Field | Value |
|---|---|
| Agent Name | `<add-agent-name>` |
| Agent IP | `<add-agent-ip>` |
| Rule ID | `<add-rule-id>` |
| Rule Description | `<add-rule-description>` |
| Alert Level | `<add-alert-level>` |
| Event Timestamp | `<add-timestamp>` |
| Source Log | `<add-source-log>` |
| User Account | `<add-user-if-applicable>` |
| Source IP | `<add-source-ip-if-applicable>` |

---

## Investigation Steps

1. Verified that the endpoint agent was connected to Wazuh.
2. Reviewed the alert in the Wazuh dashboard.
3. Checked the rule description and alert severity.
4. Identified the affected endpoint.
5. Reviewed event timestamp and source log.
6. Checked whether the activity was expected or suspicious.
7. Documented risk and recommended remediation.

---

## Evidence

| Evidence Item | Description |
|---|---|
| Screenshot 1 | Wazuh dashboard showing the alert |
| Screenshot 2 | Expanded alert details |
| Screenshot 3 | Agent status / endpoint visibility |
| Screenshot 4 | Related logs or event details |

Screenshots should be stored in:

```text
screenshots/
```

Example Markdown image references:

```markdown
![Wazuh alert overview](./screenshots/wazuh-alert-overview.png)

![Expanded alert details](./screenshots/wazuh-alert-details.png)

![Agent status](./screenshots/wazuh-agent-status.png)
```

---

## Analysis

The alert indicates that Wazuh successfully collected and processed endpoint security telemetry. The event should be reviewed based on severity, source, affected endpoint, and whether the activity matches expected administrative behavior.

If the alert is related to authentication failures, the analyst should review:

- Number of failed attempts
- Source IP address
- Targeted user account
- Affected endpoint
- Time window of the attempts
- Whether the activity may indicate brute-force behavior

If the alert is related to file integrity monitoring, the analyst should review:

- Modified file or directory
- User account associated with the change
- Timestamp of the change
- Whether the change was authorized
- Whether the file path is sensitive

If the alert is related to vulnerability detection, the analyst should review:

- Affected package or software
- CVE details
- Severity rating
- Available patch or mitigation
- Business impact of the affected system

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Notes |
|---|---|---|
| Credential Access | Brute Force | Use only if the alert involves repeated failed login attempts |
| Defense Evasion | Modify System Files | Use only if the alert involves unauthorized file modification |
| Initial Access | Exploit Public-Facing Application | Use only if evidence supports it |
| Discovery | System Information Discovery | Use only if the alert relates to enumeration activity |

---

## Impact Assessment

| Area | Assessment |
|---|---|
| Confidentiality | No confirmed data exposure in lab scenario |
| Integrity | Potential concern if unauthorized file changes are detected |
| Availability | No confirmed service disruption |
| Scope | Limited to lab endpoint |
| Business Impact | Low in lab; could be higher in production depending on affected asset |

---

## Containment Actions

Recommended containment actions, depending on alert type:

- Validate whether the activity was authorized.
- Disable or reset affected account if suspicious authentication activity is confirmed.
- Block suspicious source IP if repeated malicious access attempts are confirmed.
- Isolate endpoint if compromise is suspected.
- Preserve logs and screenshots before making major changes.

---

## Remediation Recommendations

- Patch vulnerable packages or software.
- Review user account security.
- Enforce strong passwords and MFA where applicable.
- Monitor authentication failures.
- Enable file integrity monitoring for sensitive paths.
- Review endpoint hardening baseline.
- Tune alerts to reduce false positives.
- Document known administrative activity to avoid confusion during triage.

---

## Final Classification

| Field | Value |
|---|---|
| Incident Type | Endpoint security alert |
| Severity | Low / Medium / High |
| Classification | True Positive / False Positive / Benign True Positive / Needs Further Review |
| Status | Open / Closed |
| Analyst Decision | `<add-final-decision>` |

---

## Lessons Learned

This investigation demonstrated the importance of endpoint visibility, alert context, and structured documentation in SOC operations.

The lab also showed how Wazuh can support detection, investigation, and remediation workflows when endpoint agents are properly configured and monitored.

---

## Next Steps

- Add real alert screenshots.
- Add actual rule ID and event details.
- Add MITRE mapping based on real alert evidence.
- Add remediation confirmation.
- Repeat the investigation with another alert type.
