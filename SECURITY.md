# Security Policy

## Supported versions

| Version | Supported |
|---|---|
| Latest on main | Yes |

## Reporting a vulnerability

If you discover a security vulnerability in Qryptum, please do not open a public issue.

Instead, report it privately:

1. Email a description of the vulnerability to the maintainers
2. Include steps to reproduce, potential impact, and any suggested fix
3. Allow reasonable time for the team to investigate and respond before public disclosure

We take all security reports seriously and will respond within 72 hours.

## Scope

In scope for security reports:

- Smart contract vulnerabilities (ShieldFactory, PersonalVault, ShieldToken)
- Logic errors that could allow unauthorized access to vault funds
- Cryptographic weaknesses in the vault proof system
- Backend API vulnerabilities that expose user data

Out of scope:

- Issues requiring physical access to the user's device
- Social engineering attacks
- Vulnerabilities in third-party dependencies (report those upstream)

## Responsible disclosure

We follow a 90-day responsible disclosure policy.
After a fix is deployed, we will publicly acknowledge the reporter unless they prefer to remain anonymous.
