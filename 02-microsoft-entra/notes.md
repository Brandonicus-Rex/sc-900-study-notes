# Domain 2: Describe the capabilities of Microsoft Entra (25–30%)

## Function and identity types of Microsoft Entra ID

- **Microsoft Entra ID** (formerly Azure Active Directory) is Microsoft's cloud-based identity and access management service. It handles authentication, SSO, app access, device management and identity protection.
- **Licensing:** Microsoft Entra ID **Free**, **P1** (adds Conditional Access, hybrid features, dynamic groups) and **P2** (adds ID Protection, Privileged Identity Management, access reviews). Microsoft Entra ID Governance is a separate add-on.
- **Identity types:**
  - **Human identities:** employees (**internal**) and partners, vendors or customers (**external**).
  - **Workload identities:** identities assigned to software (apps, services, scripts, containers).
    - **Service principal:** the identity of an app in a tenant.
    - **Managed identity:** a service principal that Azure manages automatically, so there are no credentials to store or rotate. **System-assigned** = tied to one resource and deleted with it. **User-assigned** = standalone and can be shared by several resources.
  - **Devices:** **Microsoft Entra registered** (personal/BYOD), **Microsoft Entra joined** (organization-owned, cloud-only sign-in), **Microsoft Entra hybrid joined** (joined to both on-prem AD and Entra ID).
- **Groups:** **Security** groups (access to resources) and **Microsoft 365** groups (collaboration: shared mailbox, calendar, files). Membership can be **assigned** or **dynamic** (rule-based).
- **Hybrid identity:** one identity across on-prem and cloud.
  - **Microsoft Entra Connect Sync** and the lighter **Microsoft Entra Cloud Sync** sync identities from on-prem AD to Entra ID.
  - **Sign-in options:** password hash synchronization (PHS), pass-through authentication (PTA) or federation (e.g., AD FS).
- **External identities:**
  - **B2B collaboration:** invite guest users who sign in with their own credentials.
  - **B2B direct connect:** two-way trust with another Entra organization (used for Teams shared channels).
  - **Microsoft Entra External ID for customers:** customer sign-up and sign-in for apps you publish.

> **Exam tip:** "An app needs to access Azure resources without storing credentials in code" → **managed identity**.

## Authentication capabilities

- **Authentication methods:** passwords, phone (SMS or voice), **Microsoft Authenticator** app, OATH tokens (hardware or software), Windows Hello for Business, **FIDO2** security keys, passkeys, certificate-based authentication, Temporary Access Pass.
- **Passwordless:** **Windows Hello for Business** (biometric or PIN tied to the device), **Microsoft Authenticator**, **FIDO2/passkeys**. These are the most secure and most convenient options.
- **Multifactor authentication (MFA):** requires two or more of: something you **know** (password), something you **have** (phone, key) and something you **are** (fingerprint, face).
  - **Security defaults:** free baseline settings that turn on MFA for all users and block legacy authentication. Recommended if you don't use Conditional Access.
- **Self-service password reset (SSPR):** users reset their own password using registered methods, which reduces help desk calls.
- **Password protection:** blocks weak passwords using a **global banned password list** (maintained by Microsoft) and a **custom banned password list** (yours). Can extend to on-prem AD.
- **Smart lockout:** locks out attackers trying to guess passwords while allowing the real user to keep signing in.

> **Exam tip:** SMS and voice calls are the **least** secure MFA methods. Passwordless methods (Windows Hello, FIDO2, Authenticator) are the **most** secure.

## Access management capabilities

- **Conditional Access:** the Zero Trust policy engine of Entra ID. Works as **if-then** statements: **signals → decision → enforcement**.
  - **Signals (assignments):** user or group, location (IP ranges, countries), device platform or state, application, **sign-in risk** and **user risk** (risk signals need ID Protection / P2).
  - **Access controls:** **block** access, or **grant** access while requiring MFA, a compliant device, a hybrid-joined device, an approved app, or a password change. **Session controls** limit what the user can do (e.g., app-enforced restrictions, sign-in frequency).
  - Requires Microsoft Entra ID **P1**.
- **Microsoft Entra roles:** control access to **Entra ID resources** (users, groups, apps), e.g., Global Administrator, User Administrator, Billing Administrator. You can create custom roles.
- **Azure RBAC:** controls access to **Azure resources** (VMs, storage, etc.) with roles such as Owner, Contributor and Reader at a scope.
- **Least privilege:** give users only the permissions they need, and only for as long as they need them.

> **Exam tip:** **Entra roles** = managing identities and Entra itself. **Azure RBAC** = managing Azure resources. Global Administrator is an Entra role, not an Azure RBAC role.

## Identity protection and governance

- **Microsoft Entra ID Governance:** makes sure the right people have the right access at the right time. Covers the **identity lifecycle** (joiner, mover, leaver) and **access lifecycle**.
  - **Entitlement management:** **access packages** bundle groups, apps and sites that users can request, with approval workflows and expiration.
  - **Lifecycle workflows:** automate tasks for joiners, movers and leavers.
- **Access reviews:** periodically review group memberships, app access and role assignments to remove access people no longer need. Reviewers can be managers, owners or the users themselves.
- **Privileged Identity Management (PIM):** manages, controls and monitors access to important resources.
  - **Just-in-time** access: roles are **eligible** and must be **activated** when needed.
  - **Time-bound** access with start and end dates.
  - Requires **approval** and **justification** to activate, with **MFA** on activation.
  - Notifications, access reviews and an audit history.
  - Requires Microsoft Entra ID **P2** (or ID Governance).
- **Microsoft Entra ID Protection:** detects, investigates and remediates identity risks.
  - **Sign-in risk:** the chance a specific sign-in wasn't made by the account owner (e.g., anonymous IP address, atypical travel, unfamiliar sign-in properties).
  - **User risk:** the chance an account is compromised (e.g., leaked credentials found online).
  - Risk can feed **Conditional Access** policies (e.g., require MFA for medium sign-in risk, require a password change for high user risk).
- **Microsoft Entra Permissions Management:** a cloud infrastructure entitlement management (CIEM) tool for permissions across Azure, AWS and GCP.

> **Exam tip:** "Admins should only have Global Administrator rights when they need them, for a limited time" → **PIM**. "Remove access people no longer need" → **access reviews**.

## Key terms

| Term | Definition |
|------|-----------|
| Microsoft Entra ID | Cloud identity and access management (formerly Azure AD) |
| Workload identity | Identity for software: service principals and managed identities |
| Managed identity | Azure-managed identity with no credentials to manage |
| Hybrid identity | One identity across on-prem AD and Entra ID |
| Entra Connect Sync / Cloud Sync | Tools that sync on-prem identities to Entra ID |
| PHS / PTA / federation | Hybrid sign-in options |
| B2B collaboration | Guest access using the guest's own credentials |
| MFA | Two or more factors: know, have, are |
| Passwordless | Windows Hello, Authenticator, FIDO2/passkeys |
| SSPR | Self-service password reset |
| Password protection | Global and custom banned password lists |
| Conditional Access | Signal-based if-then access policies (P1) |
| Entra roles vs Azure RBAC | Identity admin vs Azure resource access |
| Entitlement management | Access packages with approvals and expiration |
| Access reviews | Periodic recertification of access |
| PIM | Just-in-time, time-bound privileged roles (P2) |
| ID Protection | Detects sign-in risk and user risk (P2) |

## Questions to review

1. What kind of identity should an Azure VM use to access a storage account without storing credentials?
2. Which hybrid sign-in method validates passwords against on-prem AD without storing password hashes in the cloud?
3. Which authentication methods are considered passwordless?
4. What feature blocks users from choosing passwords like "Contoso123"?
5. Which license tier is required for Conditional Access?
6. A user signs in from an anonymous IP address. Which Entra feature detects this risk?
7. You want admins to activate the Global Administrator role only when needed, with approval. Which feature do you use?
8. What's the difference between Microsoft Entra roles and Azure RBAC roles?

<details>
<summary>Show answers</summary>

1. A **managed identity.**
2. **Pass-through authentication (PTA).**
3. **Windows Hello for Business, Microsoft Authenticator, FIDO2 security keys/passkeys.**
4. **Password protection** (custom banned password list).
5. **Microsoft Entra ID P1.**
6. **Microsoft Entra ID Protection** (sign-in risk).
7. **Privileged Identity Management (PIM).**
8. **Entra roles** manage Entra ID (users, groups, apps); **Azure RBAC** manages access to Azure resources.

</details>
