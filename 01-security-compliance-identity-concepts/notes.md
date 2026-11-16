# Domain 1: Describe the concepts of security, compliance, and identity (10–15%)

## Security and compliance concepts

- **Shared responsibility model:** security duties are split between the cloud provider and the customer, and the split depends on the service type.

| Responsibility | On-prem | IaaS | PaaS | SaaS |
|----------------|---------|------|------|------|
| Information and data, devices, accounts and identities | Customer | Customer | Customer | Customer |
| Identity and directory infrastructure | Customer | Customer | Shared | Shared |
| Applications, network controls | Customer | Customer | Shared | Provider |
| Operating system | Customer | Customer | Provider | Provider |
| Physical hosts, network, datacenter | Customer | Provider | Provider | Provider |

- **Defense-in-depth:** layered security so that if one layer fails, others still protect you. Layers (outer to inner): physical → identity and access → perimeter → network → compute → application → data.
- **CIA triad:**
  - **Confidentiality:** only authorized people can see data (e.g., encryption).
  - **Integrity:** data isn't altered without authorization (e.g., hashing).
  - **Availability:** data and systems are accessible when needed.
- **Zero Trust:** "never trust, always verify." Assume the network is already compromised.
  - **Guiding principles:** verify explicitly, use least-privilege access, assume breach.
  - **Six pillars:** identities, devices, applications, data, infrastructure, networks.
- **Encryption:** makes data unreadable without a key.
  - **Symmetric:** the same key encrypts and decrypts (fast; e.g., AES).
  - **Asymmetric:** a public/private key pair. Encrypt with the public key, decrypt with the private key (e.g., RSA, TLS).
  - **At rest:** stored data (disks, databases). **In transit:** data moving over a network (TLS/HTTPS). **In use:** data being processed in memory.
- **Hashing:** a one-way function that produces a fixed-length value. It **can't be reversed**; the same input always gives the same hash. Used for passwords (stored as hashes, often **salted**) and integrity checks.
- **GRC concepts:**
  - **Governance:** rules, policies and processes an organization uses to direct and control its activities.
  - **Risk:** identifying, assessing and responding to threats.
  - **Compliance:** following laws, regulations and standards. Related terms: **data residency** (where data is physically stored), **data sovereignty** (data is subject to the laws of the country where it's stored), **data privacy** (transparency about collecting and using personal data).

> **Exam tip:** **Encryption** is two-way (can be decrypted with a key). **Hashing** is one-way (can't be reversed). If the question mentions verifying a password without storing it, the answer is hashing.

## Identity concepts

- **Identity as the primary security perimeter:** with cloud, mobile and remote work, the network edge no longer defines security, so identity becomes the main control plane.
- **Four pillars of an identity infrastructure:**
  - **Administration:** creating and managing identities.
  - **Authentication (AuthN):** proving who you are.
  - **Authorization (AuthZ):** what you're allowed to do.
  - **Auditing:** tracking who did what, when and where.
- **Authentication vs authorization:** AuthN comes first (prove identity), AuthZ second (grant access level).
- **Identity provider (IdP):** creates, maintains and manages identities and provides authentication services. Microsoft Entra ID is an IdP. Uses modern protocols such as **OAuth 2.0** (authorization), **OpenID Connect** (authentication) and **SAML** (federation and SSO).
- **Single sign-on (SSO):** sign in once and access multiple apps.
- **Directory service:** stores directory data (users, groups, devices) and makes it available to users and admins.
  - **Active Directory Domain Services (AD DS):** the traditional on-prem directory, built around domain controllers, Kerberos and LDAP. Not designed for modern cloud or mobile scenarios.
  - **Microsoft Entra ID:** the cloud-based identity and access management service (formerly Azure AD).
- **Federation:** trust relationships between separate identity providers, so users can sign in with credentials from their own organization. Trust isn't always two-way, and isn't transitive unless configured.

> **Exam tip:** Questions that describe "using one company's credentials to access another company's resources" are about **federation**.

## Key terms

| Term | Definition |
|------|-----------|
| Shared responsibility model | Provider vs customer duties by service type |
| Defense-in-depth | Layered security controls |
| CIA triad | Confidentiality, integrity, availability |
| Zero Trust | Verify explicitly, least privilege, assume breach |
| Symmetric / asymmetric encryption | One shared key / public-private key pair |
| Hashing | One-way, fixed-length transformation; salted for passwords |
| GRC | Governance, risk and compliance |
| Data residency / sovereignty | Where data is stored / whose laws apply |
| Authentication / authorization | Prove identity / grant access level |
| Identity provider | Service that manages identities and authenticates users |
| SSO | Sign in once for many apps |
| AD DS | On-prem Active Directory directory service |
| Federation | Trust between identity providers |

## Questions to review

1. In SaaS, who is responsible for the user's devices and accounts?
2. Which Zero Trust principle says you should operate as if an attacker is already in your network?
3. What's the main difference between hashing and encryption?
4. Which type of encryption uses a public key and a private key?
5. What do we call data that's subject to the laws of the country it's stored in?
6. Which comes first: authentication or authorization?
7. What are the four pillars of an identity infrastructure?
8. What lets users at a partner organization sign in to your apps using their own company credentials?

<details>
<summary>Show answers</summary>

1. The **customer.**
2. **Assume breach.**
3. **Hashing is one-way** and can't be reversed; **encryption is two-way** and can be decrypted with the right key.
4. **Asymmetric** encryption.
5. **Data sovereignty.**
6. **Authentication.**
7. **Administration, authentication, authorization, auditing.**
8. **Federation.**

</details>
