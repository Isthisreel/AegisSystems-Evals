# Security Policy

## Supported Versions

This repository is currently in active development. Security fixes will be applied to the latest version on the `main` branch.

| Version | Supported          |
| ------- | ------------------ |
| latest  | :white_check_mark: |

## Reporting a Vulnerability

We take security vulnerabilities seriously. If you discover a security issue in this project, please follow responsible disclosure practices and **do not** open a public GitHub issue.

### How to Report

**GitHub Private Vulnerability Reporting:** Use GitHub's built-in [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) feature by navigating to the **Security** tab of this repository and clicking **Report a vulnerability**.

Please include:
- A description of the vulnerability
- Steps to reproduce the issue
- Potential impact assessment
- Any suggested mitigations (optional)

### What to Expect

- **Acknowledgement:** We aim to acknowledge receipt of your report within **48 hours**.
- **Assessment:** We will assess the severity and impact within **7 days** and keep you informed.
- **Resolution:** We will work to resolve critical vulnerabilities within **30 days** of confirmed impact.
- **Disclosure:** We will coordinate public disclosure with you after the fix has been deployed.

### Scope

The following are considered in-scope for security reports:

- Hardcoded secrets, API keys, or private keys committed to this repository
- Container escape vulnerabilities in gVisor/eBPF configurations
- Privilege escalation in the agent sandbox environment
- Unauthorized data exfiltration paths in the evaluation framework
- Dependency vulnerabilities with known CVEs

### Out of Scope

- Theoretical vulnerabilities without a proof-of-concept
- Issues in third-party libraries that already have published advisories (please report those upstream)
- Social engineering attacks

## Security Best Practices for Contributors

- **Never** commit real API keys, private keys, passwords, or tokens — use `.env` files that are listed in `.gitignore`
- Always use placeholder values in `.env.example` files (e.g., `YOUR_API_KEY_HERE`)
- Run `git log --all --full-history -S "sk-" -S "AIza" -S "ody_" -S "PRIVATE_KEY"` before pushing to verify no secrets are in history
- For blockchain private keys, use a hardware wallet or secrets manager — never store real keys in flat `.env` files
- Enable 2FA on your GitHub account

## Automated Security Tooling

This repository uses the following automated security tools:

- **GitHub Secret Scanning** — automatically detects committed API keys, tokens, and private keys
- **Dependabot** — monitors dependencies for known vulnerabilities and opens automated fix PRs
- **CodeQL** — static analysis to detect security vulnerabilities in source code

If you believe any of these tools have generated a false positive, please open an issue with the label `security`.
