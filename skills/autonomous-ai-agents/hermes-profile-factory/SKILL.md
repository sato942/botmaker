---
name: hermes-profile-factory
description: Create and verify isolated Hermes job profiles.
version: 0.1.0
author: Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [hermes, profiles, soul, verification]
    related_skills: [hermes-agent]
---

# Hermes Profile Factory

Create one installed Hermes profile from a role or project request. Produce a standalone `SOUL.md` and verify the live profile.

## When to Use

Use this skill when the user asks to:

- create a Hermes bot or profile;
- build an agent for a durable job;
- install a specialized profile identity;
- verify or update a profile definition.

Do not use this skill when the user requests only prompt text or a preview.

## Prerequisites

Load the `hermes-agent` skill before profile work.

Use the live Hermes CLI as the command source.

Get explicit approval before overwriting an existing profile identity.

Do not expose copied credentials, memory content, or private configuration.

## Naming

Select one lowercase alphanumeric job noun.

Require this regular expression:

```text
^[a-z][a-z0-9]*$
```

Run `hermes profile list` before creation.

If the selected name exists, do not overwrite the profile.

Select a different natural job noun when one fits the request.

Do not add a numeric suffix without user approval.

## Procedure

1. Classify requested capabilities as prompt-addressable, tool-dependent, human-gated, or unsafe.
2. Select one valid profile name.
3. Run `hermes profile list` and confirm that the name is absent.
4. Run exactly `hermes profile create NAME --clone-all`.
5. Stop if creation fails.
6. Run `hermes profile show NAME` after creation.
7. Use the reported `Path` value as the profile home.
8. Write the identity to `PATH/SOUL.md` with `write_file`.
9. Set one concise description with `hermes profile describe NAME --text "DESCRIPTION"`.
10. Set `terminal.cwd` only when the user supplied a project directory.
11. Read the exact installed `SOUL.md` after the write.
12. Run deterministic content checks.
13. Run `hermes profile show NAME` again.
14. Run `hermes -p NAME doctor` when practical.
15. Report verification before conclusion.

Each step must have observed evidence before the next dependent claim.

## SOUL.md Contract

Make the identity standalone.

Start with these sections:

1. `ASD-STE100 Simplified Technical English`
2. `Verification Before Conclusion`

Then include:

3. `Identity and Mission`
4. `Scope and Non-Goals`
5. `Operating Priorities`
6. `Input and Context Contract`
7. `Output and Completion Contract`
8. `Workflow`
9. `Tool and Evidence Policy`
10. `Domain Quality Gates`
11. `Uncertainty, Failure, and Escalation`
12. `Safety, Permissions, and Side Effects`
13. `Efficiency and Stop Conditions`
14. `Final Self-Check`

Use domain procedures, evidence requirements, and acceptance criteria.

Do not claim that a role title creates expertise.

Make tool claims conditional when tool access is unknown.

Put durable project rules in `.hermes.md` or `AGENTS.md`.

## Deterministic Verification

Verify these checks separately:

- profile name matches the required expression;
- profile did not exist before creation;
- the exact clone command exited successfully;
- the resolved path came from `profile show`;
- `SOUL.md` exists and is not empty;
- all required sections exist in order;
- the identity matches the requested job;
- tool claims are conditional or supported;
- safety and stop conditions exist;
- no unresolved placeholders exist;
- the description exists in `profile.yaml`;
- the alias wrapper exists when Hermes reports an alias.

Use `read_file` for exact identity and description read-back.

Use a deterministic script for section order and placeholder checks.

See `references/profile-creation-verification.md` for the verification recipe and diagnostic interpretation.

## Pitfalls

Do not assume the operating-system home is the profile home.

Do not write `SOUL.md` before `hermes profile show` resolves the path.

Do not write `SOUL.md` into the project directory.

Do not delete cloned memories, skills, cron jobs, or plugins automatically.

Do not treat optional doctor warnings as profile-creation failures.

Do not hide doctor warnings that affect the requested job.

If doctor alias reporting conflicts with `profile show`, verify the wrapper file directly.

Do not claim the new identity affects an existing session.

## Verification Report

Report:

- final status;
- creation command and exit result;
- profile name and resolved path;
- exact `SOUL.md` read-back result;
- description read-back result;
- project-directory result;
- doctor result;
- inherited-state notice;
- unresolved checks.

Give both the direct alias and `hermes -p NAME chat` when available.
