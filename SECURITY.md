# Security Policy

## Supported Versions

| Version | Supported |
|---|---|
| Latest (main branch) | Yes |
| Previous releases | Security fixes only |

## Reporting a Vulnerability

DevLink takes security seriously. If you discover a security vulnerability, please report it responsibly.

**Do not open a public GitHub issue for security vulnerabilities.**

### How to Report

1. Email **security@devlink.org** with a detailed description of the vulnerability.
2. Include steps to reproduce the issue, if possible.
3. Provide any relevant logs, screenshots, or proof-of-concept code.

### What to Expect

- **Acknowledgment** within 48 hours of your report.
- **Assessment** within 5 business days, including severity classification.
- **Resolution timeline** communicated based on severity:
  - Critical: Fix deployed within 72 hours
  - High: Fix deployed within 1 week
  - Medium: Fix deployed within 2 weeks
  - Low: Fix included in next scheduled release

### Disclosure Policy

- We follow a coordinated disclosure process.
- Reporters will be credited in the security advisory (unless anonymity is requested).
- Public disclosure occurs only after a fix is available.

## Security Best Practices

All contributors must follow these practices:

- Never commit secrets, API keys, or credentials to version control.
- Use environment variables for all sensitive configuration.
- Validate and sanitize all user input.
- Apply the principle of least privilege in access controls.
- Keep dependencies updated and audit for known vulnerabilities.
- Use TLS for all external communication.

## Contact

For security-related questions or concerns, contact **security@devlink.org**.
