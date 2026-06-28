# Security Policy

HumanizerCo takes data privacy and software security seriously. As a client-side execution tool, security and data isolation are primary design guarantees.

---

## Supported Versions

Only the latest version deployed on the `main` branch is supported with security updates.

| Version | Supported |
| :--- | :--- |
| Main (`head`) | Yes |
| Historical Releases | No |

---

## Reporting a Vulnerability

If you discover a potential security vulnerability in HumanizerCo, please report it privately rather than creating a public GitHub issue.

### How to Report

Please report security issues directly via GitHub Security Advisories:
1. Navigate to the [Security Tab](https://github.com/Manzela/HumanizerCo/security) of the repository.
2. Click **Report a vulnerability** to submit a private report.

### What to Include

To help us evaluate and address your report quickly, please include:
* A detailed description of the vulnerability and its potential security impact.
* Step-by-step proof-of-concept (PoC) instructions or code snippets to reproduce the issue.
* Any potential mitigation strategies or recommended fixes.

---

## Core Security Guarantees

* **Data Isolation**: All text transformation processing occurs entirely within the user's browser context.
* **No Telemetry PII Leakage**: Telemetry event dispatchers automatically strip raw text inputs, email addresses, and personal identifiable information prior to emission.
