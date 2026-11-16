# Security and Privacy Policy

## Supported scope

Security reports are welcome for the current default branch and the latest published release, once releases are available.

## Reporting

Do not publish exploitable vulnerabilities, credentials, personal information, or private endpoint details in public issues. Contact the repository maintainers through a private GitHub security advisory or another private channel designated by the organization.

Include the affected version or commit, impact, reproduction steps, and a suggested mitigation where possible. Do not include real user data.

## Non-negotiable privacy requirements

- Tool data, settings, history, files, and local databases stay on the user's device.
- No personal telemetry, hidden background upload, or cloud synchronization.
- The public build must not contain private registration UI, company email delivery, private API endpoints, or secrets.
- Logs must not contain names, phone numbers, email addresses, file contents, or other personal data.
- Network requests must be documented, minimized, and justified.

## Secure development

- Validate untrusted input and render user text safely; avoid unsafe HTML injection.
- Keep dependencies minimal and review provenance, advisories, and transitive dependencies.
- Use secure deployment headers, including a suitable Content Security Policy.
- Scan the repository and release artifacts for secrets and personal data before every public release.
- Use synthetic data in tests.

## Response

Maintainers should acknowledge reports, assess severity and affected versions, prepare a fix, and coordinate disclosure. Do not claim a vulnerability is fixed until the relevant tests and release checks pass.
