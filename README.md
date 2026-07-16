# 🛡️ AWS Cloud SSH Honeypot Monitoring Lab (Cowrie + Splunk Enterprise)

## 📌 Project Overview

This project demonstrates the deployment of a cloud-hosted SSH honeypot monitoring solution using **AWS**, **Ubuntu**, **Cowrie**, and **Splunk Enterprise**. SSH login attempts are captured by Cowrie, securely forwarded to Splunk through the **HTTP Event Collector (HEC)**, and analyzed using Splunk's Search Processing Language (SPL). The environment simulates a real-world Security Operations Center (SOC) workflow for centralized log collection and security monitoring.

---

## 🎯 Objectives

* Deploy a cloud-hosted Cowrie SSH honeypot on AWS.
* Deploy Splunk Enterprise as a centralized SIEM.
* Configure HTTP Event Collector (HEC) for secure log ingestion.
* Validate end-to-end event collection and analysis.
* Continuously collect and analyze real-world SSH attack activity.

---

## 🛠️ Technologies Used

* Amazon Web Services (AWS)
* Amazon EC2
* Ubuntu Server
* Cowrie SSH Honeypot
* Splunk Enterprise
* HTTP Event Collector (HEC)
* SSH
* Linux CLI
* SCP
* Python Virtual Environment
* JSON
* Search Processing Language (SPL)
