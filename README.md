# Botmaker

Botmaker is a Hermes profile factory. It converts short role or project requests into installed, verified Hermes profiles with standalone `SOUL.md` files. Each generated profile gets a communication policy matched to its audience, subject familiarity, preferred explanation depth, tone, and output format.

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

When material details are missing, Botmaker asks up to four focused questions about the intended job, audience, tools, authority, subject familiarity, and preferred explanation style. It then creates one Hermes profile, installs its identity, sets its description, and verifies the result.

Human-facing profiles default to natural conversation and adapt when users request simpler answers, more detail, or fewer basics. Software-facing profiles preserve exact schemas and error channels without adding conversational text. Mixed-use profiles keep human explanations separate from machine payloads.

## Distribution contents

- `SOUL.md`: Botmaker's complete identity and authoritative operating contract.
- `config.yaml`: Minimal model default without paths, secrets, tool preferences, or machine settings.
- `distribution.yaml`: Hermes distribution manifest.
- `README.md`: Installation, usage, and release notes.
- `.gitignore`: Protection against committing credentials, personal state, and generated files.

Botmaker does not require a custom profile-factory skill. Its complete behavior is defined by `SOUL.md`, which Hermes loads as the profile's primary identity.

This distribution does not ship the author's full configuration, `.env`, credentials, memories, sessions, logs, caches, or machine-specific paths. Each installer supplies their own credentials.

## Changelog

### 5.0.0

- Replaced universal ASD-STE100 technical-English rules with an audience-aware communication policy.
- Generated profiles now resolve audience and delivery surface, subject familiarity, explanation depth, tone, and output requirements independently.
- Human-facing profiles default to connected, natural prose; lists and formal reports are used only when the content or requested format benefits from them.
- Machine-facing profiles preserve strict schemas, syntax, and error channels without greetings, Markdown wrappers, or extra explanations.
- Added optional, nonblocking familiarity checks and adaptation to requests such as “simpler,” “more detail,” and “skip the basics.”
- Updated setup questions to distinguish the profile creator from the eventual audience and subject knowledge from explanation preference.
- Separated verification work from presentation: evidence and unresolved limitations remain mandatory, while ordinary human-facing completion reports can stay conversational.
- Removed mandatory line-number editing reports, line-count savings, universal audit headings, and automatic inheritance of Botmaker-specific reporting syntax.
- Revised minimality rules to remove duplication without cutting useful explanations, safeguards, or feasible requested scope.
- Preserved profile creation, naming, cloning, path resolution, dependency, project-directory, safety, and bounded-work finalization contracts.
- Existing generated profiles require an explicit update or regeneration to adopt the new communication policy.
- Validation covered the directive and representative scenarios at the instruction level; live conversational behavior and Hermes CLI compatibility were not tested for this revision.

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
