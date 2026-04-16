# Versioning Policy

## 1. Versioning Scheme

`contributing-specification` follows **Semantic Versioning 2.0.0** (SemVer).

Versions are expressed as `MAJOR.MINOR.PATCH`:

- **MAJOR**: Breaking changes to the normative specification that require implementers to update their validators or documentation significantly.
- **MINOR**: Additions to the specification (new sections, rules, or recommended practices) that are backwards-compatible.
- **PATCH**: Clarifications, formatting fixes, or non-normative corrections.

## 2. Stability Tiers

- **Internal Draft**: Rapidly changing, not for implementation.
- **Proposed Standard**: Stable enough for early implementation and feedback.
- **Canonical Standard**: The authoritative version used across the Repose ecosystem.

## 3. Breaking Changes

Breaking changes MUST be clearly identified in the `CHANGELOG.md` under a `### Removed` or `### Changed` header with a `[BREAKING]` prefix.

## 4. Automation

This repository aims for **100% automated versioning** driven by the commit semantics defined in `CONTRIBUTING.md`.
