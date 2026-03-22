# 🛡️ Project Sentinel-Eye: Authentication Audit & Brute Force Mitigation
**Author:** Vishvdeep Singh Bal  
**Environment:** Log(N) Pacific – The Cyber Range (Azure Enterprise)  
**Date:** March 22, 2026

---

## 1. Objective
To proactively identify and mitigate unauthorized authentication attempts within the Azure Enterprise infrastructure. This hunt focuses on distinguishing between automated external noise and simulated internal attack vectors.

## 2. MITRE ATT&CK® Mapping
| Tactic | Technique | ID | Discovery |
| :--- | :--- | :--- | :--- |
| **Credential Access** | Brute Force | [T1110](https://attack.mitre.org/techniques/T1110/) | Automated attempts targeting public VMs. |
| **Credential Access** | Password Spraying | [T1110.003](https://attack.mitre.org/techniques/T1110.003/) | **Attack Engine** hitting multiple hosts. |
| **Lateral Movement** | Exploitation of Remote Services | [T1210](https://attack.mitre.org/techniques/T1210/) | Systematic failed logons detected on critical nodes. |

---

## 3. Findings & Visualization

![Top Attackers Analysis](top_attackers_chart.png)
*Figure 1: Data visualization of the top 10 Source IPs generating failed logon events over a 24-hour period.*

### **A. External Threat: Automated Brute Force**
- **Source IP:** `185.156.73.24` (Public)
- **Target:** `ahmed-test-vm`
- **Volume:** **200 failed attempts**
- **Analysis:** High-frequency failures from a single public source indicate a botnet-driven attempt to crack administrative credentials.

### **B. Internal Threat: Verified Attack Simulation (Success)**
- **Source IP:** `10.0.0.8` (Private - **Internal Attack Engine**)
- **Targets:** `cyberclaw-vm`, `fuentes-vuln-mg`
- **Total Volume:** **353 cumulative failures**
- **Analysis:** This activity was mapped back to the **log(N) Pacific Attack Engine**. The high-volume failures across multiple assets demonstrate a successful "Password Spray" simulation. My KQL successfully flagged this activity as an anomaly, providing 100% detection coverage of the internal red-team exercise.

---

## 4. Technical Implementation (KQL)
The following query was developed and tuned within **Microsoft Sentinel** to reduce alert fatigue by focusing on systemic attacks rather than isolated typos.

```kusto
DeviceLogonEvents
| where TimeGenerated > ago(24h)
| where ActionType == "LogonFailed"
| where isnotempty(RemoteIP)
| summarize FailureCount = count(), 
            TargetCount = dcount(DeviceName)
            by RemoteIP, RemoteIPType
| where FailureCount > 50 or TargetCount > 3
| sort by FailureCount desc
