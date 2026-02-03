# 🛡️ Wazuh SIEM Lab on AWS (Hybrid Environment)

## 📌 Project Overview
This project demonstrates the design, deployment, and hardening of a **hybrid Wazuh SIEM lab**
using AWS cloud infrastructure and an on-prem Linux endpoint.

The lab simulates a real SOC environment by integrating cloud-based and on-prem systems while
applying secure networking principles, controlled agent enrollment, and post-deployment
hardening.

---

## 🏗️ Environment Architecture
The lab consists of the following components:

- ☁️ **Wazuh All-in-One Server (AWS EC2)**
  - Wazuh Manager  
  - Wazuh Indexer  
  - Wazuh Dashboard (HTTPS)

- 🖥️ **Cloud Linux Agent (AWS EC2)**
  - Ubuntu Server monitored via private VPC networking

- 💻 **On-Prem Kali Linux Agent**
  - Local virtual machine with static IP
  - Securely connected using temporary public access during enrollment

Cloud agents communicate exclusively over private IP addresses, while public access is tightly
restricted and removed after agent onboarding.

---

## 🔐 Security Design Decisions
Key security practices implemented in this lab include:

- 🔒 Private VPC communication for cloud-based agents
- ⏳ Temporary exposure of agent enrollment ports for on-prem onboarding only
- 🎯 Strict CIDR-based security group rules
- 🧹 Post-enrollment removal of public agent ports
- 📌 Version pinning to prevent agent/manager incompatibility
- 🌐 HTTPS dashboard access with restricted source IPs

These controls reduce attack surface and align with SOC and cloud security best practices.

---

## 📚 Documentation
Full technical details are provided in the following documents:

- 📘 **Step-by-Step Setup Guide**  
  Reproducible instructions for deploying the lab from scratch  
  → `docs/setup-guide.md`

- 📗 **Technical & Architecture Documentation**  
  Design decisions, network architecture, and operational behavior  
  → `docs/technical-documentation.md`

---

## ✅ Operational Validation
The lab was validated by:

- ✔️ Successful agent enrollment and key exchange
- 🔄 Persistent connectivity after instance stop/start
- 📊 Verified visibility of all agents in the Wazuh dashboard
- 🔐 Post-enrollment hardening without loss of agent connectivity

---

## 🧠 Skills Demonstrated
This project demonstrates hands-on experience with:

- SIEM deployment and configuration (Wazuh)
- AWS EC2, VPC, and Security Group design
- Hybrid cloud/on-prem integration
- Linux endpoint monitoring
- Secure agent enrollment workflows
- SOC-style troubleshooting and validation

---

## 🚀 Future Enhancements
Planned improvements include:

- Windows endpoint onboarding
- MITRE ATT&CK mapping and alert correlation
- Attack simulation and alert validation
- VPN-based connectivity for on-prem agents
- Custom dashboards and alert tuning
