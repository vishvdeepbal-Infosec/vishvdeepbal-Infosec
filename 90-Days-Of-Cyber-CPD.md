# 🛡️ SOC Readiness: Daily Technical Audit Trail
**Name:** Vishvdeep Singh Bal, CC  

## 📋 Why this Audit Trail?
In Cybersecurity, documentation is as critical as technical execution. This repository serves as a centralized "Central Source of Truth" for my daily growth, capturing insights from:

* **Hands-on Labs:** Building and defending enterprise-grade environments in the **Josh Madakor Cyber Range**.
* **Certification Tracks:** Daily progress through **CompTIA Security+** and **ISC2 CC** domains.
* **Mentorship:** High-level strategic sessions with **RiskStifle** on firewall logic and security audits.
* **Industry Intelligence:** Insights from daily cyber news, threat reports, and industry podcasts (e.g., Darknet Diaries, CyberWire).
* **Tool Mastery:** Documentation of my evolving stack: Microsoft Sentinel (SIEM), Defender (EDR), Azure AD, and Tenable.

---

## 🗓️ February 2026 Logs

### 📍 Saturday, Feb 21, 2026 — Day 1: Foundation & Identity
**Focus:** Firewall & Vulnerability Management Theory & Professional Identity Engineering

#### 🏗️ Theoretical Deep Dive (06:00 - 10:00)
* **Firewall Logic:** Studied Next-Generation Firewall (NGFW) architecture with a focus on **Fortigate**.
* **Audit Principles:** Explored the relationship between security audits, internal controls, and Firewall Audits.
* **Enterprise Connectivity:** Analyzed how firewall policy logic governs traffic flow in regulated sectors.

#### 💻 Portfolio & Architecture Engineering
* **GitHub Hub:** Initialized the `vishvdeepbal-Infosec` repository as a professional portfolio.
* **Credential Validation:** Integrated verified links for **ISC2 Certified in Cybersecurity (CC)** and **Forage simulations** (AIG, Deloitte, Mastercard).
* **Project Roadmapping:** Defined the **Vulnerability Management** lifecycle (Discover, Prioritize, Remediate, Verify).
* **Architecture Design:** Finalized the high-level design for the **Cyber Range** lab, identifying the integration points between Azure, Tenable, and EDR endpoints.

---

  ### 📍 Sunday, Feb 22, 2026 — Day 2: The Multi-Source Learning Loop
**Focus:** Vulnerability Theory & Cloud Infrastructure Prep

 ### 🏗️ Project 1: Vulnerability Management (Azure + Tenable)
Status: Initialized Phase 1 (Theory & Scoping).

Activity: Deep-dive into the NIST Vulnerability Management Life Cycle.

Generalization: Researching how Tenable concepts translate to Rapid7 and Qualys to maintain a "product-agnostic" mindset.

Cloud Prep: Reviewing Azure Resource Group naming conventions for the "Cyber Range" student VMs.

📚 Security+ & Certification Prep
Domain Focus: Threats, Attacks, and Vulnerabilities.

Concept Mastery: Reinforced the difference between "Vulnerabilities" (weaknesses) and "Threats" (actors who exploit them), aligning this with the practical lab work in Tenable.

🧠 Analyst Key Takeaway
"A SOC Analyst doesn't just look at a dashboard; they look at the world. Sunday was about connecting Security+ theory to the Cyber Range labs, ensuring my technical actions are informed by current threat intelligence."

---

### 📍 Monday & Tuesday, Feb 23-25, 2026 — Day 3 & 4: Strategic Theory & Baseline Assessment
**Focus:** Security+ Domain 1 & Industry Intelligence

#### 📚 Security+ SY0-701 Certification Prep
* **Resource Confirmation:** Finalized the 2026 study stack using Inside Cloud and Security (Exam Cram series), Professor Messer, and Crucial Exams.
* **Baseline Assessment:** Completed a baseline practice exam via Crucial Exams and Professor Messer’s Pop Quizzes.
* **Objective:** Identify knowledge gaps in Domain 1 (General Security Concepts) before continuing Azure implementation.
* **Domain 1 Deep-Dive:** Focused on Section 1.1: Security Control Categories.
    * **Technical vs. Managerial vs. Operational vs. Physical:** Studied how these controls overlap.
    * **Control Types:** Mastered the differences between Deterrent, Preventive, Detective, Corrective, and Compensating controls.

#### 🎙️ Industry Intel & News
* **Podcast:** The CyberWire Daily (Ep 2494 | 02.23.26).
* **Topic:** "The basics broke telecom."
* **Analysis:** Connected the podcast's discussion on fundamental infrastructure failures to the Change Management and Operational Controls studied in Security+ today.

#### 🧠 Analyst Key Takeaway
"Today was a 'Pivot Day.' I chose to delay the Cyber Range hands-on to focus on establishing a solid theoretical baseline for Security+. In a SOC environment, you must sometimes pause operations to ensure your fundamental knowledge of controls (Preventive vs. Detective) is 100% accurate."

---

### 📍 Thursday & Friday, Feb 26–27, 2026 — Day 6 & 7: Incident Narratives & Strategic Pivots
**Focus:** Technical Storytelling, Anti-Forensics Analysis, and Azure Cloud Fundamentals
**Activity Type:** Technical Synthesis & Certification Planning

#### 🏗️ Technical Synthesis & Post Engineering
* **Case Study Development:** Formalized the "Timestomping vs. EDR Telemetry" scenario. This involved documenting the delta between unreliable file system metadata ($MACE$) and the ground truth found in process execution logs.
* **Defense Strategy:** Evaluated why Real-Time Threat Intelligence acts as a critical failure-override for static whitelisting during the Delivery Phase of the Kill Chain.
* **LinkedIn Technical Lead Gen:** Authored and published a high-engagement case study focused on the SOC Mindset.
    * **The Narrative:** Detailed a phishing investigation where an attacker used Timestomping to hide a 2026 payload under a 2019 timestamp.
    * **The Solution:** Highlighted the use of EDR parent-child process trees to uncover the truth.
* **Asset Creation:** Designed a custom technical 16:9 thumbnail using high-contrast "Defender vs. Attacker" visual themes to increase post CTR (Click-Through Rate).
* **Strategic Outreach:** Initiated professional contact with Rachel Ko (Magnet Forensics), leveraging shared interests in digital artifacts and forensic investigation.

#### 💻 Portfolio & Certification Engineering
* **GitHub Hub:** Pushed updates to the vishvdeepbal-Infosec repository, including the initial structure for the Daily Cyber CPD Audit and professional credentials.
* **Strategic Pivot (AZ-900):** Finalized the decision to sit for the AZ-900 (Microsoft Azure Fundamentals) exam at the end of next week.
    * **Rationale:** Establishing a validated foundation in cloud concepts, architecture, and governance to support future specialization in Microsoft Sentinel and Azure Security Center.

---

### 📍 Saturday, Feb 28, 2026 — Day 8: Cryptographic Architecture & Enterprise Vulnerability Strategy
**Focus:** Hardware Security Roots (TPM/HSM) and NIST 800-40 Remediation Strategy
**Activity Type:** Riskstifle Mentorship Class (Discussion) & The Cyber Range's Vulnerability Management Domain

#### 🏗️ Theoretical Deep Dive: Hardened Encryption & Trust (10:00 - 13:00)
* **TPM (Trusted Platform Module):** Analyzed how TPM provides a Hardware Root of Trust.
    * **Rootkit Prevention:** Explored Measured Boot protocols where the TPM verifies the hash of each boot stage, preventing unauthorized kernel-level changes.
    
    * **DLP Integration:** Studied "Sealing" keys to hardware, ensuring data remains encrypted and inaccessible if the storage medium is moved to an unauthorized device.
* **HSM vs. Cloud Vaults:** Evaluated the architectural differences between physical Hardware Security Modules (FIPS 140-2 Level 3) for high-compliance key management vs. Azure Key Vault/KMS for scalable cloud application secrets.
* **Identity & PKI:** Reviewed the role of Certificate Authorities (CA) and the cryptographic handshake in securing enterprise communications.

#### 💻 Enterprise Vulnerability Management Theory (14:00 - 18:00)
* **Domain (40% Completion):** Deep dive into the Vulnerability Management Lifecycle based on NIST 800-40.

* **Strategic Remediation:** Analyzed the risks of "Security-Induced Outages"—where a patch causes more downtime than a potential exploit.
* **Tiered Rollout Strategy:** Mastered the industry-standard remediation flow to ensure 99.9% Uptime while patching:
    * **Pre-Pilot:** IT-only sandbox testing.
    * **Pilot:** Small, controlled user groups.
    * **Pre-Production:** Departmental validation (Pre-Prod).
    * **Production:** Full-scale enterprise deployment.
* **Change Management Nuance:** Evaluated the "Strategic vs. Tactical" divide, identifying that securing stakeholder buy-in is often more challenging than the physical act of patching.




