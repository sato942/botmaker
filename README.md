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

Botmaker creates one isolated Hermes profile, installs its identity, sets its description, and verifies the result.

## Distribution contents

- `SOUL.md`: Botmaker identity and operating contract.
- `skills/autonomous-ai-agents/hermes-profile-factory/`: Profile creation and verification procedure.
- `config.yaml`: Minimal model default without paths, secrets, tool preferences, or machine settings.
- `distribution.yaml`: Hermes distribution manifest for version `2.0.0`.

This distribution does not ship the author's full configuration, `.env`, credentials, memories, sessions, logs, caches, or machine-specific paths. Each installer supplies their own credentials.

## Requirements

- Hermes Agent `>=0.21.0`
- Git

No API key is declared by this distribution. Botmaker uses the model and credentials configured by each installer.

## Update

```bash
hermes profile update botmaker
```

## Security

Review `SOUL.md` and the bundled skill before use. A Hermes profile can use enabled tools and is not a security sandbox.
