# Security Policy

## Scope

This policy applies to all repositories in the `eAg-HFMS-AgroTutor` organization.

## Never commit

- Passwords
- API keys
- Access tokens
- Refresh tokens
- Private keys
- Real `.env` files
- Personal data
- Sensitive research data
- Private infrastructure details

## Reporting a vulnerability

Create a private security report where available, or contact the project technical lead directly. Do not open a public issue for exploitable vulnerabilities or exposed secrets.

Include:

- Affected repository
- Affected component
- Description of the issue
- Steps to reproduce, if safe
- Potential impact
- Suggested mitigation, if known

## If a secret is exposed

1. Revoke or rotate the secret immediately.
2. Remove it from active configuration.
3. Notify the technical lead.
4. Review repository history and logs.
5. Add a preventive control, such as secret scanning or CI validation.

## Data protection

Repositories must not contain raw restricted datasets, personal data, credentials, or unpublished confidential material unless explicitly approved and access-controlled.
