# 🔍 njRAT Malware Analysis (Bladabindi)

> Static Analysis of one of the most persistent Remote Access Trojans (RATs) still active in modern cyber threats.

---

## 📌 Overview

This repository contains a **detailed static malware analysis** of **njRAT (Bladabindi)** — a widely გავრცელ (and still active) Remote Access Trojan first observed in 2012.

The analysis was performed in a **fully isolated lab environment** using industry-standard reverse engineering tools to understand its behavior, capabilities, and attack techniques.

---

## 🎯 Objectives

- Analyze a real-world malware sample safely  
- Understand njRAT architecture and execution flow  
- Identify persistence, C2 communication, and exfiltration techniques  
- Map behavior to **MITRE ATT&CK framework**  
- Provide defensive insights for detection and response  

---

## 🧪 Analysis Environment

| Component | Details |
|----------|--------|
| Platform | FLARE VM |
| OS | Windows 10 (x64) |
| Network | Isolated (Host-only) |
| VM Tools | VMware / VirtualBox |

---

## 🛠 Tools Used

- VirusTotal → Threat intelligence & detection  
- Detect It Easy (DIE) → Binary structure analysis  
- PE Studio → Static PE inspection  
- dnSpy → .NET decompilation  
- HxD → Hex-level inspection  

---

## 📄 Sample Information

| Property | Value |
|--------|------|
| File Name | `njrat_sample.exe` |
| File Type | PE32 (.NET) |
| Size | 37 KB |
| Language | VB.NET |
| Entropy | 5.574 (Not Packed) |

---

## 🚨 Detection Summary

- **63 / 71 antivirus engines** flagged the sample as malicious  
- Identified as:
  - njRAT  
  - Bladabindi  
  - Trojan / Backdoor / RAT  

---

## 🌐 Command & Control (C2)

- **0.tcp.eu.ngrok.io**
- Uses **TCP communication**
- Leverages **ngrok tunneling** to hide attacker infrastructure

---

## 🔬 Key Capabilities

### 🔑 Persistence
- Registry Run Key: HKCU\Software\Microsoft\Windows\CurrentVersion\Run

---

### ⌨️ Keylogging
- Uses `GetAsyncKeyState`
- Stores logs in registry
- Steals credentials & sensitive input

---

### 📸 Surveillance
- Webcam detection  
- Screenshot capture  
- Active window monitoring  

---

### 📂 File System Control
- Upload / Download / Execute files  
- Full remote system control  

---

### 🧩 Plugin-Based Execution
- Loads .NET assemblies in memory  
- Fileless execution capability  

---

### ⚠️ Anti-Removal Mechanism
- NtSetInformationProcess

- Marks process as **critical**
- Killing process → **BSOD (system crash)**

---

## 🧬 Execution Flow
Start → Install Persistence → Connect to C2
→ Send System Info → Wait for Commands
→ Execute Attacker Instructions


---

## 🛡️ MITRE ATT&CK Mapping

| Technique | Description |
|----------|------------|
| T1547.001 | Registry Run Keys |
| T1056.001 | Keylogging |
| T1041 | Data Exfiltration |
| T1572 | Protocol Tunneling |
| T1055 | Process Manipulation |

---

## 🛡️ Defensive Recommendations

- Keep OS & antivirus updated  
- Avoid suspicious downloads and email attachments  
- Monitor registry startup entries  
- Detect unusual outbound network traffic  
- Block tunneling services (ngrok, etc.)  
- Deploy EDR solutions  

---

## 📂 Repository Structure

📁 njrat-analysis
├── README.md
├── report/
│ └── njrat_analysis_report.docx
├── blog/
│ └── njrat_medium_blog.md
└── samples/
└── (hash references only)



---

## ⚠️ Disclaimer

This project is strictly for **educational and research purposes only**.

- Malware was analyzed in a **controlled, isolated environment**
- No malicious activity was performed
- Do NOT execute malware on your host system

---

## 👨‍💻 Authors

- **Khush Pachani**
- **Nand Gajera**

---

## 🔖 Tags

`#Cybersecurity` `#MalwareAnalysis` `#ReverseEngineering` `#njRAT` `#InfoSec` `#BlueTeam` `#DFIR`
