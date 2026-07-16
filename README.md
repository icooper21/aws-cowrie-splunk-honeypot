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


---

# 🏗️ Architecture Overview

The environment consists of two Ubuntu-based Amazon EC2 instances deployed within AWS. The first EC2 instance hosts the Cowrie SSH honeypot and listens for inbound SSH connections on TCP port **2222**. Captured events are securely forwarded to a second EC2 instance running Splunk Enterprise through the **HTTP Event Collector (HEC)** over TCP port **8088**. Splunk indexes the events in a dedicated **cowrie** index, where they can be searched, analyzed, and visualized using Search Processing Language (SPL).

```text
                    Internet
                        │
          Automated SSH Login Attempts
                        │
                        ▼
         AWS EC2 (Ubuntu + Cowrie Honeypot)
                 TCP 2222 (SSH)
                        │
           JSON Events via HEC (TCP 8088)
                        │
                        ▼
       AWS EC2 (Ubuntu + Splunk Enterprise)
               Index: cowrie
                        │
                        ▼
       SPL Searches • Dashboards • Analysis
```

### Key Components

| Component                       | Purpose                                                                   |
| ------------------------------- | ------------------------------------------------------------------------- |
| **AWS EC2 (Cowrie)**            | Hosts the SSH honeypot and captures attacker activity.                    |
| **Cowrie**                      | Simulates an SSH server and records login attempts and attacker commands. |
| **HTTP Event Collector (HEC)**  | Securely forwards Cowrie events to Splunk.                                |
| **AWS EC2 (Splunk Enterprise)** | Receives, indexes, and analyzes Cowrie event data.                        |
| **Splunk Search & Reporting**   | Searches, visualizes, and monitors collected security events using SPL.   |

