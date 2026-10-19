# Security Policy

## Supported versions

Security fixes land on the latest release of each project. Older releases may not receive patches.

| Version | Supported |
|---|---|
| Latest release | Yes |
| Previous minor and older | No |

## Reporting a vulnerability

Do not open a public issue or discussion for a security vulnerability. Use GitHub's private vulnerability reporting instead:

> **Security > Report a vulnerability** on the repository page
> (https://github.com/Axelthebat/Axelthebat/security/advisories/new)

This opens a private advisory visible only to you and me. If that button is missing from your GitHub interface, email **security@axelthebat.dev**. I will send a PGP key on request.

Do not post vulnerability details in an issue, a discussion, or a pull request. Do not include real credentials, tokens, private keys, or customer data. Do not test against systems you do not own or have written permission to test.

### What to include

- Type of issue: remote code execution, path traversal, authentication bypass, privilege escalation, information leak, or another class
- Affected project and version
- Steps to reproduce, or a proof of concept
- Impact, described in terms of what an attacker can do
- A suggested mitigation, if you have one

### What to expect

| Stage | Target |
|---|---|
| Acknowledgement | 48 hours |
| Initial assessment | 7 days |
| Fix and release | 30 days, faster for critical issues |
| Public advisory | Coordinated with you, after the fix ships |

I will keep you updated throughout the process, and I will credit you in the advisory unless you prefer to stay anonymous.

## Scope

In scope: vulnerabilities in the code hosted in this organisation's repositories.

Out of scope:

- Findings in upstream dependencies with no working proof of impact. Report those upstream.
- Self-inflicted issues, such as running as root with an explicit `--insecure` flag or disabling TLS verification on purpose
- Social engineering, phishing, and physical attacks
- Denial of service through deliberate resource exhaustion
- Missing hardening headers on a static profile page
- Reports produced entirely by scanners with no manual verification

Thanks for taking the time to report responsibly.
