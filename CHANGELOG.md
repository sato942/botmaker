# Changelog

This changelog records Botmaker behavior changes between the two retained profile specifications:

- Version 1: `SOUL.botmakerv1.md`
- Version 2: `SOUL.botmakerv2.md`

## [2.0.0] - 2026-09-05

Version 2 keeps the complete Version 1 contract and adds 154 lines. No Version 1 lines were removed.

### Added

#### Output economy

- Added a short-response policy for chat output.
- Added direct tool-call behavior without preambles or progress narration.
- Protected commands, paths, identifiers, errors, numbers, units, and negations from compression.
- Disabled terse output for security warnings, irreversible confirmations, and ambiguity-sensitive procedures.
- Kept persisted artifacts in normal prose instead of terse chat style.

#### Minimal generated profiles

- Added a six-step minimality ladder for generated `SOUL.md` files.
- Required Botmaker to skip unnecessary rules and reuse existing runtime behavior.
- Required the minimum implementation that satisfies the requested job.
- Prohibited speculative abstractions and unrequested scaffolding.
- Preserved trust-boundary validation, data-loss handling, security, accessibility, and requested behavior.

#### Review before installation

- Added a mandatory excess-content review before writing a generated `SOUL.md`.
- Added `delete`, `runtime`, `yagni`, and `shrink` finding categories.
- Added the `net: -<N> lines possible.` review summary.
- Added `Lean already. Install.` as the clean-review result.
- Required accepted reductions to be applied before installation.

#### Deferred-setup tracking

- Added `botmaker: <ceiling>, <trigger to revisit>` markers for deferred setup.
- Added a `Deferred Setup` section to final responses when markers exist.
- Required markers without a revisit trigger to be reported as `no-trigger`.
- Prevented deferred requirements from closing silently.

#### Honest claims

- Prohibited unsupported claims about time, token, or cost savings.
- Prohibited guarantees of profile competence or accuracy.
- Limited readiness evidence to observed creation, read-back, description, and doctor results.

#### Inheritance requirements

- Required every generated profile to inherit adapted forms of the new Version 2 controls.
- Mapped output economy into `Output and Completion Contract`.
- Mapped the minimality ladder into `Workflow`.
- Mapped review-before-install into `Domain Quality Gates`.
- Mapped deferred-setup tracking into `Uncertainty, Failure, and Escalation`.
- Mapped honest claims into `Output and Completion Contract`.
- Mapped intensity levels into `Efficiency and Stop Conditions`.
- Required domain-appropriate adaptations for non-coding profiles.

#### Risk-based intensity

- Added `lite` for common, low-risk jobs.
- Added `full` for normal jobs with external or irreversible effects.
- Added `ultra` for high-risk, regulated, or production jobs.
- Matched verification depth to the selected intensity.

### Changed

- Expanded live-profile verification to confirm that generated profiles contain the inherited Version 2 controls.
- Expanded the final self-check to confirm inheritance of output economy, minimality, review, deferral, honesty, and intensity rules.

### Compatibility

- Kept the Version 1 profile naming, creation, path resolution, description, verification, safety, and completion contracts.
- Kept `hermes profile create <name> --clone-all` as the required creation command.
- Added no replacement commands and removed no existing requirements.

### Comparison evidence

```text
SOUL.botmakerv1.md: 487 lines
SOUL.botmakerv2.md: 641 lines
Difference:          154 additions, 0 deletions
```
