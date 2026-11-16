# Domain 4: Describe the capabilities of Microsoft compliance solutions (20–25%)

## Service Trust Portal and privacy principles

- **Service Trust Portal (STP):** Microsoft's public site with content, tools and resources about how Microsoft cloud services protect your data.
  - **Certifications, regulations and standards:** audit reports and compliance guides (ISO, SOC, GDPR, FedRAMP, etc.).
  - **Reports, whitepapers and artifacts:** pen test results, business continuity documents, privacy and data protection.
  - **Industry and regional resources.**
  - **My Library:** save documents and get notified when they're updated.
  - Signing in with a Microsoft cloud account unlocks some documents.
- **Microsoft's six privacy principles:**

| Principle | Meaning |
|-----------|---------|
| **Control** | You control your data and your privacy choices |
| **Transparency** | Microsoft is open about how it collects and uses data |
| **Security** | Data is protected with strong security and encryption |
| **Strong legal protections** | Microsoft respects local privacy laws and defends your privacy as a fundamental right |
| **No content-based targeting** | Your email, chat, files and other content aren't used to target ads |
| **Benefits to you** | When Microsoft collects data, it's used to benefit you and improve your experience |

> **Exam tip:** "Where can I download Microsoft's ISO 27001 audit report?" → **Service Trust Portal**.

## Compliance management in Microsoft Purview

- **Microsoft Purview portal:** the central place for compliance and data governance solutions (Compliance Manager, Information Protection, DLP, eDiscovery, Audit, etc.).
- **Microsoft Purview Compliance Manager:** helps you manage compliance across multi-cloud environments, from taking inventory of risks to implementing controls.
  - **Controls:** requirements of a regulation or standard. Three types: **Microsoft-managed**, **your** (customer-managed) and **shared**.
  - **Assessments:** groups of controls for a specific regulation or standard (e.g., GDPR, ISO 27001, NIST). The **Microsoft Data Protection Baseline** is assessed by default.
  - **Templates:** prebuilt assessment frameworks for regulations.
  - **Improvement actions:** recommended steps with implementation guidance; you assign them to people and track them.
- **Compliance score:** measures your progress on improvement actions. **Higher is better.**
  - Actions are worth points. **Mandatory** and **preventive** actions are worth more than **discretionary**, **detective** or **corrective** actions.
  - Score combines Microsoft-managed actions (already scored) with your own actions.

> **Exam tip:** **Compliance score** (Purview) = progress on **regulatory compliance**. **Secure score** (Defender) = **security posture**. Don't mix them up.

## Information protection, data lifecycle, and data governance

Microsoft Purview follows a **know your data → protect your data → prevent data loss → govern your data** approach.

### Know your data: classification

- **Sensitive information types (SITs):** patterns that identify sensitive data, such as credit card numbers, passport numbers or bank account numbers. There are many built-in SITs, and you can create custom ones.
- **Trainable classifiers:** use machine learning to recognize types of content (e.g., resumes, contracts, source code) from examples rather than patterns.
- **Data classification dashboard:**
  - **Content explorer:** shows **what** sensitive items exist and **where** (you can drill into individual items with the right permissions).
  - **Activity explorer:** shows **what's being done** with sensitive data (labeled, label changed, copied to USB, etc.).

### Protect your data: sensitivity labels

- **Sensitivity labels:** classify and protect content (e.g., Public, General, Confidential, Highly Confidential). They're **persistent**, staying with the file wherever it goes, and stored in file metadata.
  - Labels can **encrypt** content, add **watermarks**, headers and footers, restrict access, and protect Teams, groups and SharePoint sites.
  - Applied manually by users, by default, or **automatically** based on content.
- **Label policies:** publish labels to users and groups, and set options such as a **default label**, **mandatory labeling** and **justification** to remove or downgrade a label.

### Prevent data loss: DLP

- **Data loss prevention (DLP):** stops sensitive data from being shared or leaked inappropriately.
  - Works across **Exchange, SharePoint, OneDrive, Teams, endpoints (Windows and macOS devices)**, on-prem repositories and some third-party cloud apps.
  - **Policies** use conditions (e.g., content contains credit card numbers) and actions (block, warn, encrypt, notify).
  - **Policy tips** warn users in context before they share something they shouldn't.
  - **Endpoint DLP** controls actions on devices: copy to USB, print, upload to the cloud, copy to clipboard.

### Govern your data: data lifecycle and records management

- **Retention policies:** apply to **locations** (e.g., all of Exchange, specific SharePoint sites, Teams). Keep content, delete it, or keep it and then delete it.
- **Retention labels:** apply to **individual items** (documents, emails). Can be applied manually or automatically. **An item can only have one retention label.**
- **Principles of retention:** **retention wins over deletion**, the **longest retention period wins**, **explicit inclusion wins over implicit inclusion**, and the **shortest deletion period wins**.
- **Records management:** uses retention labels to **declare items as records**, which prevents them from being edited or deleted. **Regulatory records** are the strictest; even admins can't remove the label. Includes **disposition review** before content is deleted.

> **Exam tip:** **Sensitivity labels** = **protection** (encryption, watermarks, access). **Retention labels** = **how long** to keep content. An item can have **one of each**.

## Insider risk, eDiscovery, and audit

- **Insider risk management:** detects and helps act on risky activities by people inside the organization.
  - **Policy templates:** data theft by departing users, data leaks, security policy violations, and others.
  - **Workflow:** policies → alerts → triage → investigate → action.
  - Built with **privacy by design**: users are **pseudonymized** (shown with anonymized names) by default, and access is controlled by role.
- **Communication compliance:** detects inappropriate messages (harassment, sharing sensitive information, regulatory violations) in Teams, Exchange and other channels.
- **eDiscovery:** identifies and delivers electronic information that can be used as **evidence in legal cases**.
  - Search content across Exchange, SharePoint, OneDrive and Teams.
  - Place content on **legal hold** so it can't be deleted.
  - Review, analyze and **export** results.
  - The modern eDiscovery experience in the Purview portal unifies the older Content search, eDiscovery (Standard) and eDiscovery (Premium) tools.
- **Audit:** records user and admin activity across Microsoft 365 for security investigations and compliance.
  - **Audit (Standard):** turned on by default; logs kept for **180 days**.
  - **Audit (Premium):** keeps logs for **one year** by default (up to **10 years** with an add-on license), adds **intelligent insights** (e.g., MailItemsAccessed for investigating compromised mail) and higher API bandwidth.

> **Exam tip:** "Legal team needs to find and preserve emails for a lawsuit" → **eDiscovery** (with **legal hold**). "Find out who deleted a file last week" → **Audit**.

## Key terms

| Term | Definition |
|------|-----------|
| Service Trust Portal | Microsoft's audit reports and compliance documentation |
| Six privacy principles | Control, transparency, security, strong legal protections, no content-based targeting, benefits to you |
| Compliance Manager | Tool for managing compliance with regulations |
| Compliance score | Progress on improvement actions |
| Sensitive information type | Pattern-based identifier for sensitive data |
| Trainable classifier | ML-based content classification |
| Content explorer / Activity explorer | Where sensitive data is / what's being done with it |
| Sensitivity label | Persistent classification and protection |
| DLP | Prevents sensitive data from being shared inappropriately |
| Retention policy / label | Retention for locations / for individual items |
| Records management | Declare items as records that can't be changed or deleted |
| Insider risk management | Detects risky activities by internal users |
| eDiscovery / legal hold | Find legal evidence / preserve it from deletion |
| Audit (Standard / Premium) | 180-day activity logs / 1-year logs and intelligent insights |

## Questions to review

1. Where can you find Microsoft's SOC and ISO audit reports?
2. Which Microsoft privacy principle says your content won't be used to target ads?
3. What does the compliance score in Compliance Manager measure?
4. Which tool shows you where sensitive data is stored? Which shows what users are doing with it?
5. You want to encrypt and watermark documents classified as Confidential. What do you use?
6. A user tries to email a file containing credit card numbers to an external address and gets a warning. Which feature is this?
7. Can an email have both a sensitivity label and a retention label?
8. Your legal team needs to stop certain mailboxes from being deleted during a lawsuit. What do you use?
9. How long does Audit (Standard) keep logs by default?

<details>
<summary>Show answers</summary>

1. **Service Trust Portal.**
2. **No content-based targeting.**
3. **Progress on improvement actions** toward regulatory compliance.
4. **Content explorer** shows where sensitive data is; **Activity explorer** shows what's being done with it.
5. **Sensitivity labels.**
6. **Data loss prevention (DLP)**, showing a **policy tip.**
7. **Yes.** An item can have one sensitivity label and one retention label.
8. **eDiscovery** with a **legal hold.**
9. **180 days.**

</details>
