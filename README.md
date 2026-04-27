# phishing_case-8815
# 🛡️ Incident Report: Phishing via Shortened URL – Case 8815

**Case ID:** 8815
**Date:** June 16, 2025
**Exercise Source:** LetsDefend – SOC Simulation
**Severity:** Medium – Phishing

---

## 🔎 Executive Summary

A phishing attempt was identified through an email sent from a suspicious address impersonating Amazon. The message contained a shortened `bit.ly` link that redirected to an IP address previously flagged as malicious. Although the targeted user clicked the link, the organization's firewall successfully blocked the outbound connection, preventing a potential compromise.

---

## 🧪 Technical Analysis

| Field | Value |
|---|---|
| **Sender** | `urgents@amazon.biz` |
| **Recipient** | `h.harris@thetrydaily.thm` |
| **User Internal IP** | `10.20.2.17` |
| **Malicious Link** | `http://bit.ly/3sHkX3da12340` |
| **Resolved Destination IP** | `67.199.248.10` |

### Threat Intelligence Findings

- **VirusTotal:** 2 antivirus engines flagged the link and destination IP as malicious.
- **AbuseIPDB:** IP `67.199.248.10` has been reported multiple times for malicious activity.
- **SIEM / Firewall:** The outbound connection attempt was detected and blocked at the perimeter.
- **User Action:** Click confirmed — no payload was downloaded or executed.

---

## 🧾 Indicators of Compromise (IOCs)

| Type | Value | Notes |
|---|---|---|
| Email | `urgents@amazon.biz` | Brand impersonation (Amazon) |
| URL | `http://bit.ly/3sHkX3da12340` | Shortened URL redirecting to malicious host |
| IP | `67.199.248.10` | Destination IP flagged as malicious |
| User | `h.harris@thetrydaily.thm` | Affected user account |
| Internal IP | `10.20.2.17` | Workstation IP of affected user |

---

## 🗺️ MITRE ATT&CK Mapping

| Technique ID | Name | Description |
|---|---|---|
| T1566.002 | Phishing: Spearphishing Link | Malicious link delivered via email |
| T1204.001 | User Execution: Malicious Link | User clicked the phishing link |

---

## 🚨 Final Verdict

| | |
|---|---|
| **Classification** | ✅ Confirmed Malicious |
| **Impact** | ✅ None — connection blocked by firewall |
| **Escalation Required** | ❌ No |

---

## 🛡️ Response Actions Taken

- Malicious URL and destination IP added to firewall and SIEM blocklists.
- Affected user was notified and received targeted security awareness guidance.
- No further activity related to this alert was detected post-investigation.
- IP `67.199.248.10` added to active monitoring rules across SIEM.

---

## 📘 Lessons Learned

- Brand impersonation (particularly well-known services like Amazon) remains a highly effective social engineering vector.
- Perimeter firewall controls proved effective in preventing a potential endpoint compromise.
- This case reinforces the need for ongoing end-user security awareness training, particularly around shortened URLs and unsolicited emails.

---

## 📎 Evidence

### 📌 SIEM Alert
![splunk1](https://github.com/user-attachments/assets/b34eebfa-8b90-4f37-9b7d-2420cb65f645)

### 📌 VirusTotal Analysis
![caso1vt](https://github.com/user-attachments/assets/7129a975-e95c-4c83-ad54-319190aa86c6)

### 📌 AbuseIPDB Report
![caso1abuse](https://github.com/user-attachments/assets/f591f1c2-4e45-4ac2-9e03-96bc5c33367a)




