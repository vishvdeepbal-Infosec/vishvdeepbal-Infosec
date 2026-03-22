# 🕵️‍♂️ Threat Hunt Roadmap: Unauthorized TOR Usage 
> **Status:** 🟢 UPCOMING (Scheduled to commence immediately following completion of Vulnerability Management Project)
**Environment:** Azure Tenant | Microsoft Defender for Endpoint (EDR) | Microsoft Sentinel (SIEM)

## 📌 Project Objective
To proactively identify the installation and execution of the TOR (The Onion Router) browser within a corporate Windows 11 environment. This project simulates an "Insider Threat" or "Shadow IT" scenario where a user attempts to bypass network controls and establish covert communication channels.

---

## 🗺️ The Roadmap (Project Phases)

### **Phase 1: Environment Setup & Baselining (Planned Start: Post-Vuln Mgmt)**
* [ ] **Provisioning:** Deploying a Windows 11 target VM within an Azure Tenant.
* [ ] **Onboarding:** Enrolling the asset into **Microsoft Defender for Endpoint** and ensuring telemetry flows to **Microsoft Sentinel**.
* [ ] **Policy Review:** Verifying **Network Security Groups (NSGs)** to monitor outbound traffic on standard TOR ports (9001, 9030, 9050).

### **Phase 2: Adversary Emulation (The "Bad Actor" Workflow)**
* [ ] **Delivery:** Downloading the TOR portable installer via a browser.
* [ ] **Execution:** Performing a **Silent Installation** using the `/S` flag to simulate stealthy deployment.
* [ ] **Persistence:** Establishing a circuit and browsing `.onion` domains to generate realistic **NetworkEvents** and **DNS** logs.
* [ ] **Artifact Creation:** Creating and deleting a "shopping-list.txt" file to simulate data staging/exfiltration prep.

### **Phase 3: Detection Engineering & KQL Development**
* [ ] **File Analytics:** Writing **KQL** queries to track `DeviceFileEvents` for renamed or hidden installers.
* [ ] **Process Logic:** Developing queries for `DeviceProcessEvents` to catch the parent-child relationship between the installer and the `tor.exe` process.
* [ ] **Network Hunting:** Creating high-fidelity alerts in Sentinel for connections hitting TOR entry/exit nodes.

### **Phase 4: Analysis & Reporting**
* [ ] **Root Cause Analysis (RCA):** Documenting the timeline of the "attack" from initial download to network connection.
* [ ] **MITRE Mapping:** Mapping the activity to **T1571** (Non-Standard Port) and **T1071.001** (Application Layer Protocol: Web Protocols).
* [ ] **Remediation Recommendations:** Drafting a "Trusted Advisor" report on how to block TOR at the firewall and EDR level.

---

## 🛠️ Technical Stack
| Category | Tool |
| :--- | :--- |
| **EDR** | Microsoft Defender for Endpoint |
| **SIEM** | Microsoft Sentinel (KQL) |
| **Cloud** | Azure (Bastion, NSGs) |
| **Forensics** | Process Tree Analysis, Timeline Analysis |

---

## 📜 Credit & Mentorship
* **Lab Framework:** Inspired by the **Log(n) Pacific Cyber Range** under the mentorship of **Josh Madakor**.
* **Developed & Documented By:** Vishvdeep Singh Bal

---
