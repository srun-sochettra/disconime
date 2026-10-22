# Security guidance

## Configuration

The root `.env` file is a Flutter asset. Its contents must be treated as public client configuration. The current documented setting is the API base URL; do not add private API keys, passwords or access tokens.

Favourites, search history and cached responses use local preferences. This documentation does not claim that storage is encrypted or suitable for secrets.

## Reporting a concern

Do not publish credentials, personal data or exploit details in a public issue. Use a private reporting route only if one is actually available on the repository, or contact the maintainer through an existing verified private channel. No dedicated security address, response deadline or supported-version policy is established by this document.

Provide a minimal reproduction, affected source paths and expected versus observed behaviour. Redact sensitive information from logs and screenshots. If credentials have been exposed, revoke or rotate them rather than relying only on deleting a commit.

## Scope

Disconime depends on third-party API and image services. This guide is not a security audit or a guarantee about those services or the application.
