# Security Policy

The [OpenNG Foundation](https://www.openng.org/) takes security seriously. If you believe you have found a vulnerability in an OpenNG Foundation open-source project, please report it responsibly so we can investigate and address it.

## Supported versions

Security fixes are provided for maintained releases of each library. Check the repository README and release notes for supported Angular and library versions. Unsupported or end-of-life releases may not receive patches.

## Reporting a vulnerability

**Do not** open a public GitHub issue, pull request, or discussion for security vulnerabilities. Public reports can put users at risk before a fix is available.

### Preferred: GitHub private vulnerability reporting

For repositories that have [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) enabled:

1. Open the affected repository on GitHub.
2. Go to the **Security** tab.
3. Click **Report a vulnerability** and submit the form.

This is the fastest way for maintainers to triage, coordinate a fix, and credit reporters when appropriate.

### Alternative: Email

If private reporting is not available on a repository, or you are unsure which repository is affected, email **openng.foundation@gmail.com** with:

- A clear description of the vulnerability and its potential impact
- Steps to reproduce, including versions (library, Angular, Node, browser if relevant)
- Any proof-of-concept code, logs, or screenshots
- Your preferred contact information for follow-up

Encrypt sensitive details if you can; we will work with you on a secure channel if needed.

## What to expect

- **Acknowledgment** — We aim to confirm receipt within a few business days.
- **Investigation** — Maintainers will assess severity, affected versions, and mitigations.
- **Coordination** — We may ask for clarification or additional reproduction details.
- **Disclosure** — We prefer coordinated disclosure. Please allow reasonable time for a fix before public disclosure. We will agree on a timeline with you when possible.
- **Credit** — With your permission, we are happy to acknowledge your report in release notes or a security advisory.

## Scope

This policy applies to OpenNG Foundation repositories under the [openng-foundation](https://github.com/openng-foundation) organization. Individual repositories may publish additional security notes in their README; follow those when they exist.

Out of scope for this channel:

- General support questions or non-security bugs (use GitHub Issues with the appropriate template)
- Vulnerabilities in third-party dependencies already tracked publicly elsewhere — report those to the upstream project, and let us know if an OpenNG library is affected
- Social engineering, physical security, or issues in deployments or applications built with our libraries that do not stem from the library itself
