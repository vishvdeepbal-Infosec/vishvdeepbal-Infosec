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

*Figure 1: Data visualization of the top 10 Source IPs generating failed logon events over a 24-hour period.*
[Top Attackers Analysis](<img width="1000" height="600" alt="top_attackers_chart" src="https://github.com/user-attachments/assets/67dbf6ef-1044-41d8-a71b-db6aabd75ecb" />)

*Figure 2: KQL Query used for the findings & Mapping the detected Brute Force and Password Spraying techniques.*
<img width="2536" height="1286" alt="image" src="https://github.com/user-attachments/assets/751a638b-8114-4199-9cfd-606f1fdc23c3" />

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

## 4. Technical Implementation (KQL)-Improved Detection
The following query was developed and tuned within **Microsoft Sentinel** to reduce alert fatigue by focusing on systemic attacks rather than isolated typos.

kusto
DeviceLogonEvents
| where TimeGenerated > ago(24h)
| where ActionType == "LogonFailed"
| where isnotempty(RemoteIP)
| summarize FailureCount = count(), 
            TargetCount = dcount(DeviceName)
            by RemoteIP, RemoteIPType
| where FailureCount > 50 or TargetCount > 3
| sort by FailureCount desc

---

## 5. AI-Augmented SOC Workflow

In this investigation, I integrated **Google Gemini (LLM)** as an "AI SOC Co-Pilot" to augment the threat hunting lifecycle. This synergy between human analysis and machine intelligence allowed for:

* **Advanced KQL Refinement:** Leveraged the LLM to optimize query logic, specifically utilizing `dcount` functions to identify target diversity. This was instrumental in distinguishing the **Attack Engine's** spraying pattern from standard noise.
* **Rapid Telemetry Synthesis:** Automated the conversion of high-volume raw CSV telemetry into this structured, executive-level report, significantly reducing the "Time to Insight."
* **Data Prioritization:** Utilized AI to assist in the statistical prioritization of the top 10 most aggressive source IPs, ensuring immediate focus on the highest-risk threats.

---

## 6. Response & Actionables

Based on the findings of this hunt, the following security operations were executed:

1.  **Perimeter Defense:** Initiated immediate blocking of identified malicious Public IPs at the **Azure Network Security Group (NSG)** level to neutralize the external brute force threat.
2.  **Alert Validation:** Successfully cross-referenced activity from `10.0.0.8` with the **log(N) Pacific Attack Engine** logs. This confirmed a 100% detection rate for the simulated "Password Spray" exercise.
3.  **Endpoint Hardening:** Conducted a post-incident verification to ensure that **Account Lockout Policies** were triggered correctly on all target Windows and Linux machines, preventing unauthorized access during the simulation.

---





