# Profile Creation and Verification Recipe

Use this reference after a successful `hermes profile create` command.

## Command Sequence

Run these commands through `terminal`:

```text
hermes profile list
hermes profile create NAME --clone-all
hermes profile show NAME
hermes profile describe NAME --text "DESCRIPTION"
hermes profile show NAME
hermes -p NAME doctor
```

Do not add flags to the creation command.

Use the `Path` field from `profile show` for all profile file operations.

## Read-Back Targets

Read these files with `read_file`:

```text
RESOLVED_PROFILE_PATH/SOUL.md
RESOLVED_PROFILE_PATH/profile.yaml
```

Read the entire `SOUL.md` when its size permits.

Confirm that `profile.yaml` contains the exact description.

Do not read `.env` during routine verification.

## Content Probe

Use a deterministic script to inspect the installed file.

Check these properties:

```text
file_exists
nonempty
first_two_sections
all_required_sections
identity_match
conditional_tool_claims
safety_exists
stop_conditions_exist
no_unresolved_placeholders
```

Search unresolved placeholders with a bounded pattern for:

```text
TODO
TBD
FIXME
INSERT
PLACEHOLDER
{{...}}
<...>
```

Do not treat ordinary Markdown links or comparison operators as placeholders.

## Alias Verification

Treat `profile show` as the primary alias report.

If Hermes reports an alias, verify that the wrapper path exists.

If doctor omits the alias, do not declare failure when the wrapper exists.

Report the diagnostic inconsistency as a non-blocking observation.

## Doctor Interpretation

Use the doctor exit result and relevant findings separately.

A successful doctor exit does not mean that every optional integration is configured.

Treat these findings as non-blocking unless the requested job depends on them:

- optional messaging packages;
- unused provider authentication;
- optional media or desktop dependencies;
- rate-limit credentials for optional hubs;
- unrelated orphan aliases.

Treat these findings as material when the requested job depends on them:

- invalid profile configuration;
- unavailable selected model authentication;
- missing required toolset;
- inaccessible profile directory;
- missing `SOUL.md`;
- active security advisory affecting the requested operation.

## Project Directory

If the user supplied an existing project directory, resolve the directory before configuration.

Then run:

```text
hermes -p NAME config set terminal.cwd ABSOLUTE_PROJECT_PATH
hermes -p NAME config get terminal.cwd
```

If the user supplied no project directory, do not change the cloned setting.

Read the cloned setting only for the final report.

## Final Status

Use `VERIFIED` only when every material profile check passes.

Use `PARTIALLY VERIFIED` when the profile exists but a material later step remains unknown.

Use `BLOCKED` when creation fails or required authorization is unavailable.

Do not delete a partial profile automatically.
