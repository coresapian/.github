# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in any Coresapian project, please report it responsibly by emailing:

**info@coresapian.com**

Please do not file public issues or pull requests for security-related problems.

## What Qualifies as a Security Issue

- Remote code execution or privilege escalation
- SQL injection, cross-site scripting (XSS), or cross-site request forgery (CSRF)
- Authentication or authorization bypasses
- Exposure of sensitive data (credentials, personal information, secrets)
- Denial-of-service vulnerabilities exploitable with modest resources
- Flaws in cryptographic implementations or key management

The following are generally **not** security issues and should be reported as regular bugs:

- Missing rate limiting (unless it enables account takeover or data exfiltration)
- Social engineering attacks
- Issues in third-party dependencies without a proven exploit against our services
- Theoretical vulnerabilities without a reproducible scenario

## Responsible Disclosure

We ask that you:

1. Report vulnerabilities in good faith and avoid accessing or modifying other users' data.
2. Allow us a **90-day embargo period** to investigate and remediate before any public disclosure.
3. Do not exploit the vulnerability beyond what is necessary to demonstrate the issue.
4. Provide enough detail for us to reproduce and verify the problem (affected project, steps, impact).

We will not pursue legal action against researchers who follow this policy in good faith.

## Response Timeline

| Stage                        | Target      |
|------------------------------|-------------|
| Acknowledgment of report     | 3 business days |
| Initial triage and assessment| 5 business days |
| Remediation or mitigation    | Within 90 days   |
| Notification to reporter     | After fix is deployed |

We will keep you informed of progress throughout the process. If the 90-day window is approaching without resolution, we will discuss options with you before any coordinated disclosure.

## Out of Scope

Individual projects may define additional scope or reporting details in their own `SECURITY.md`. If a project-level policy exists, it takes precedence for that project.
