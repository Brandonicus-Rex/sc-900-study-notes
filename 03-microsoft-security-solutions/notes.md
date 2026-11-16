# Domain 3: Describe the capabilities of Microsoft security solutions (35–40%)

## Core infrastructure security services in Azure

| Service | What it does | Key point |
|---------|-------------|-----------|
| **Azure DDoS Protection** | Defends against distributed denial-of-service attacks | Basic infrastructure protection is free and automatic. **DDoS Network Protection** and **DDoS IP Protection** add tuning, alerts, telemetry and cost protection |
| **Azure Firewall** | Managed, cloud-based **stateful** network firewall | Filters traffic at layers 3–7 across VNets and subscriptions. Built-in high availability, threat intelligence filtering, central policy. Tiers: Basic, Standard, Premium |
| **Web Application Firewall (WAF)** | Protects web apps from common exploits | Blocks **SQL injection** and **cross-site scripting** (OWASP Top 10). Runs on **Application Gateway**, **Azure Front Door** or Azure CDN |
| **Network security groups (NSGs)** | Allow or deny traffic to Azure resources in a VNet | Rules use **5-tuple** (source, source port, destination, destination port, protocol), processed by **priority** (lower number first). Applied to subnets or NICs. Default rules can't be deleted |
| **VNet segmentation** | Split networks into VNets and subnets | Limits attacker movement; supports Zero Trust |
| **Azure Bastion** | Secure RDP/SSH to VMs **through the Azure portal over TLS** | VMs don't need public IPs, and RDP/SSH ports aren't exposed to the internet |
| **Azure Key Vault** | Securely stores and manages **secrets**, **keys** and **certificates** | Centralized, access controlled with RBAC or access policies, logged. Backed by HSMs |

> **Exam tip:** **NSG** = basic allow/deny rules on a subnet or NIC. **Azure Firewall** = central, stateful, fully managed firewall for many VNets. **WAF** = protection for **web apps** specifically.

## Security management capabilities of Azure

- **Microsoft Defender for Cloud:** a **cloud-native application protection platform (CNAPP)** for Azure, on-prem (via **Azure Arc**), AWS and GCP. Two main pillars:
  - **Cloud security posture management (CSPM):** finds weak spots in your configuration.
    - **Foundational CSPM** is **free**: secure score, recommendations, asset inventory.
    - **Defender CSPM** is paid: adds attack path analysis, cloud security explorer, agentless scanning and more.
  - **Cloud workload protection (CWP):** threat protection for specific workloads through **Defender plans** (e.g., Defender for Servers, Storage, SQL, Containers, Key Vault, App Service). Produces security **alerts**.
- **Secure score:** a percentage showing your security posture. **Higher is better.** Raise it by fixing recommendations.
- **Security policies and initiatives:** built on **Azure Policy**. The default initiative is the **Microsoft cloud security benchmark (MCSB)**. Defender for Cloud checks resources against it and generates **recommendations**.
- **Regulatory compliance dashboard:** shows compliance against standards such as ISO 27001, PCI DSS and NIST.
- **DevOps security:** visibility into code repos and pipelines (GitHub, Azure DevOps, GitLab).

> **Exam tip:** **CSPM** = posture (are my resources configured securely?). **CWP** = threat protection (is someone attacking my workloads?).

## Capabilities of Microsoft Sentinel

- **SIEM (security information and event management):** **collects** and **analyzes** security data from many sources and generates alerts.
- **SOAR (security orchestration, automation and response):** takes alerts and **automates responses** through playbooks.
- **Microsoft Sentinel** is a **cloud-native SIEM and SOAR**. It's built on a Log Analytics workspace and is now integrated into the **Microsoft Defender portal**.
- **How Sentinel works:**
  - **Collect:** **data connectors** for Microsoft and third-party sources (Microsoft 365, Entra ID, AWS, firewalls, syslog). **Content hub** solutions package connectors, rules and workbooks.
  - **Detect:** **analytics rules** find threats and create **incidents**. Uses Microsoft threat intelligence and machine learning (UEBA).
  - **Investigate:** incidents group related alerts. **Investigation graph** shows relationships between entities. **Hunting** uses KQL queries and **notebooks** to look for threats proactively.
  - **Respond:** **automation rules** and **playbooks** (built on **Azure Logic Apps**) automate response, e.g., disable a user or block an IP.
  - **Visualize:** **workbooks** for dashboards.
- **Pricing:** pay based on data ingested and stored (pay-as-you-go or commitment tiers).

> **Exam tip:** "Automatically respond to an alert" → **playbook** (Logic Apps). "Proactively search for threats" → **hunting**. "Dashboards" → **workbooks**.

## Threat protection with Microsoft Defender XDR

- **Microsoft Defender XDR** (extended detection and response) is a unified, pre- and post-breach defense suite. It **correlates** signals across endpoints, identities, email and apps into **incidents** and can automatically respond.

| Service | Protects | Key capabilities |
|---------|---------|------------------|
| **Defender for Office 365** | Email and collaboration (Exchange Online, Teams, SharePoint, OneDrive) | **Safe Links**, **Safe Attachments**, anti-phishing. **Plan 1** = protection; **Plan 2** = adds Threat Explorer, automated investigation and response (AIR), attack simulation training |
| **Defender for Endpoint** | Devices (Windows, macOS, Linux, iOS, Android) | Endpoint detection and response (EDR), attack surface reduction, next-generation protection (antivirus), automated investigation and remediation |
| **Defender for Cloud Apps** | SaaS apps | **Cloud access security broker (CASB)**. Discovers **shadow IT**, controls app sessions, protects data, detects threats, manages **SaaS security posture** |
| **Defender for Identity** | **On-prem Active Directory** | Uses sensors on domain controllers to detect compromised identities, reconnaissance, lateral movement and attacks such as pass-the-hash |
| **Defender Vulnerability Management** | Devices and software | Continuous asset discovery, risk-based prioritization of vulnerabilities and misconfigurations, remediation tracking |
| **Microsoft Defender Threat Intelligence** | Threat research | Information on threat actors, their infrastructure and indicators of compromise to speed up investigations |

- **Microsoft Defender portal** (security.microsoft.com): one place for incidents, alerts, hunting, threat analytics and Secure Score across Defender XDR, Sentinel and Defender for Cloud.
- **Microsoft Secure Score** (in the Defender portal): measures security posture across Microsoft 365 identities, devices and apps. Not the same as the Defender for Cloud secure score, which covers Azure resources.

> **Exam tip:** **Defender for Identity** = **on-prem AD**. **Entra ID Protection** = **cloud** identity risk. **Defender for Cloud Apps** = **SaaS apps and shadow IT**.

## Key terms

| Term | Definition |
|------|-----------|
| DDoS Protection | Defends against denial-of-service attacks |
| Azure Firewall | Managed, stateful, central network firewall |
| WAF | Protects web apps from SQL injection, XSS and similar attacks |
| NSG | Allow/deny rules on subnets or NICs, processed by priority |
| Azure Bastion | Browser-based RDP/SSH without public IPs |
| Azure Key Vault | Stores secrets, keys and certificates |
| Defender for Cloud | CNAPP: CSPM plus workload protection |
| CSPM / CWP | Posture management / workload threat protection |
| Secure score | Percentage measure of security posture |
| Microsoft cloud security benchmark | Default security policy initiative in Defender for Cloud |
| SIEM / SOAR | Collect and analyze / automate response |
| Microsoft Sentinel | Cloud-native SIEM and SOAR |
| Playbook | Automated Sentinel response built on Logic Apps |
| Defender XDR | Unified suite correlating signals across domains |
| CASB | Cloud access security broker (Defender for Cloud Apps) |
| Shadow IT | Apps used without IT approval |

## Questions to review

1. Which service protects web apps from SQL injection and cross-site scripting?
2. How can admins connect to VMs over RDP without giving the VMs public IP addresses?
3. Where should an app store its database connection string and certificates?
4. Which part of Defender for Cloud is free and provides a secure score and recommendations?
5. What's the difference between SIEM and SOAR?
6. In Microsoft Sentinel, what do you use to automatically respond to an incident?
7. Which Defender product detects attacks against on-premises Active Directory domain controllers?
8. Which Defender product discovers shadow IT apps in your organization?

<details>
<summary>Show answers</summary>

1. **Web Application Firewall (WAF).**
2. **Azure Bastion.**
3. **Azure Key Vault.**
4. **Foundational CSPM.**
5. **SIEM** collects and analyzes security data to detect threats; **SOAR** automates the response.
6. **Playbooks** (and automation rules).
7. **Microsoft Defender for Identity.**
8. **Microsoft Defender for Cloud Apps.**

</details>
