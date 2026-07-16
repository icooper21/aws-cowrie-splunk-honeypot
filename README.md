# 🛡️ AWS Cloud SSH Honeypot Monitoring Lab (Cowrie + Splunk Enterprise)

# 📌 Project Overview

This project demonstrates the deployment of a cloud-hosted SSH honeypot monitoring solution using **AWS**, **Ubuntu**, **Cowrie**, and **Splunk Enterprise**. SSH login attempts are captured by Cowrie, securely forwarded to Splunk through the **HTTP Event Collector (HEC)**, and analyzed using Splunk's Search Processing Language (SPL). The environment simulates a real-world Security Operations Center (SOC) workflow for centralized log collection and security monitoring.

---

# 🎯 Objectives

* Deploy a cloud-hosted Cowrie SSH honeypot on AWS.
* Deploy Splunk Enterprise as a centralized SIEM.
* Configure HTTP Event Collector (HEC) for secure log ingestion.
* Validate end-to-end event collection and analysis.
* Continuously collect and analyze real-world SSH attack activity.

---

# 🛠️ Technologies Used

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

---

# 🏗️ Architecture Overview

* Two Ubuntu-based Amazon EC2 instances deployed within AWS.
* Cowrie SSH honeypot captures inbound SSH login attempts.
* Security events are forwarded to Splunk Enterprise using the HTTP Event Collector (HEC).
* Events are indexed in a dedicated **cowrie** index.
* Splunk Search & Reporting is used to search, monitor, and visualize attack activity.

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

---

# 🌐 Environment Configuration

* **Cowrie Server:** Ubuntu EC2 instance running the Cowrie SSH honeypot.
* **Splunk Server:** Ubuntu EC2 instance running Splunk Enterprise.
* **SSH Management:** TCP Port **22** restricted to **My IP**.
* **Cowrie Honeypot:** TCP Port **2222** open to capture SSH attack attempts.
* **Splunk Web Interface:** TCP Port **8000** restricted to **My IP**.
* **HTTP Event Collector (HEC):** TCP Port **8088** for secure event forwarding.
* **Event Storage:** Dedicated **cowrie** index for centralized log collection.


---

# ⚙️ Implementation Summary

* Deployed two Ubuntu-based Amazon EC2 instances for Cowrie and Splunk Enterprise.
* Installed and configured the Cowrie SSH honeypot to capture SSH login attempts.
* Installed and configured Splunk Enterprise on a dedicated EC2 instance.
* Created a dedicated **cowrie** index and configured the HTTP Event Collector (HEC).
* Integrated Cowrie with Splunk to securely forward JSON event data.
* Validated end-to-end event ingestion using controlled SSH login attempts.
* Configured the environment to continuously collect and analyze real-world SSH attack activity.


---

# ✅ Validation & Results

* Successfully verified end-to-end event ingestion from Cowrie to Splunk Enterprise using HTTP Event Collector (HEC).
* Confirmed SSH login attempts were captured, indexed, and searchable within the **cowrie** index.
* Validated the environment using Splunk Search Processing Language (SPL) queries.
* Configured the honeypot to continuously collect and monitor real-world SSH attack activity.

### Sample SPL Queries

```spl
index=cowrie
```

```spl
index=cowrie
| stats count
```

```spl
index=cowrie
| top src_ip
```

```spl
index=cowrie
| top username
```

## 📸 Screenshots

*(To be updated after collecting additional real-world attack activity.)*


---

# 💡 Skills Demonstrated

* AWS Cloud Infrastructure
* Linux Administration
* Network Security
* Splunk Enterprise (SIEM)
* HTTP Event Collector (HEC)
* SSH & Secure Remote Administration
* Security Monitoring & Log Analysis
* Search Processing Language (SPL)
* Troubleshooting & Root Cause Analysis

---

# 📚 Lessons Learned

* Strengthened Linux system administration and troubleshooting skills.
* Gained hands-on experience deploying and integrating a SIEM solution.
* Developed a deeper understanding of secure log collection and event analysis.
* Reinforced the importance of validating end-to-end connectivity in cloud environments.

---

# 🚀 Future Enhancements

*This section will be updated as additional real-world SSH attack activity is collected and analyzed.*

