# Botmaker

Botmaker is a Hermes profile factory. It converts short role or project requests into installed, verified Hermes profiles with standalone `SOUL.md` files.

## Install

```bash
hermes profile install github.com/sato942/botmaker --alias
```

Start Botmaker:

```bash
botmaker chat
```

You can also run:

```bash
hermes -p botmaker chat
```

## Example

Ask Botmaker:

```text
Create a C++ programmer for C:\path\to\project
```

Botmaker creates one Hermes profile, installs its identity, sets its description, and verifies the result.

## Distribution contents

- `SOUL.md`: Botmaker's complete identity and authoritative operating contract.
- `config.yaml`: Minimal model default without paths, secrets, tool preferences, or machine settings.
- `distribution.yaml`: Hermes distribution manifest for version `4.0.0`.
- `README.md`: Installation, usage, and release notes.
- `.gitignore`: Protection against committing credentials, personal state, and generated files.

Botmaker does not require a custom profile-factory skill. Its complete behavior is defined by `SOUL.md`, which Hermes loads as the profile's primary identity.

This distribution does not ship the author's full configuration, `.env`, credentials, memories, sessions, logs, caches, or machine-specific paths. Each installer supplies their own credentials.

## Changelog

### 4.0.0

- Replaced strict sentence-length limits with clarity-first communication: use natural, complete sentences, retain ordinary grammar, and explain unfamiliar technical terms and results.
- Made the clarity rules take precedence over other style rules in the Botmaker SOUL.
- Removed the chat-only short-form rules that required terse output to resume after sensitive content.
- Replaced best-effort profile creation with clarification before creation.
- Botmaker now asks three or four focused questions about purpose, context, authority, and communication when those details are missing.
- Botmaker skips questions already answered and waits for the remaining answers before drafting or installation.
- In single-query mode, Botmaker returns the questions without creating a profile when no user is available to answer.
- Botmaker proceeds with stated conservative defaults only when the user requests them.

### 3.0.0

- Required Botmaker and every generated profile to reconcile bounded delegations and background work before a final completion report.

## Requirements

- Hermes Agent `>=0.21.0`
- Git

No API key is declared by this distribution. Botmaker uses the model and credentials configured by each installer.

## Update

```bash
hermes profile update botmaker
```

## Security

Review `SOUL.md` before use. A Hermes profile can use enabled tools and is not a security sandbox.
