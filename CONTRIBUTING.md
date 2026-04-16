# Contributing to the Rhythmus Contributing Specification

This repository contains the official **Rhythmus `CONTRIBUTING.md` Specification**. As the canonical source for this standard, this repository MUST adhere to the very rules it defines.

## 1. Overview

This document provides guidelines for contributing to the specification itself. We use a dogfooding approach: everything defined in `CONTRIBUTING.spec.md` is strictly enforced here.

## 2. Contribution Lifecycle

We follow the standard Rhythmus lifecycle:
**discover → discuss → implement → validate → submit → review → merge**

## 3. Development Workflow

### 3.1 Branching: Typed Workstreams

Branches MUST follow the `<type>/[scope]/<description>` pattern.

### 3.2 Commit Messages: Conventional Commits

We use the Conventional Commits standard. Messages MUST be prefixed with `feat:`, `fix:`, `refactor:`, etc.

## 4. Getting Started

1.  **Fork** the repository.
2.  **Clone** your fork locally.
3.  **Install** dependencies using `pnpm install`.
4.  **Create** a typed branch for your work.

## 5. Issue Reporting

Please use the provided **Issue Templates** to report bugs or request features. Ensure reproduction steps are clear and exhaustive.

## 6. Standards

- **Specification Style**: Documentation follows RFC-style normative language (RFC 2119).
- **Code Style**: Any supporting tools must follow the project's `.editorconfig`.

## 7. Pull Request Protocol

Every Pull Request MUST satisfy the **Standard** compliance tier or higher before it will be considered for review. This includes:
- Valid branch naming.
- Valid commit history.
- Passing CI validation (`pnpm run validate:contributing`).

## 8. Communication

General discussions happen via **GitHub Issues** or the **Rhythmus Community** channels. Formal specification proposals MUST follow the RFC lifecycle.

## 9. Release & Versioning

This project adheres to **Semantic Versioning**. All notable changes are documented in the [CHANGELOG.md](CHANGELOG.md). Detailed versioning protocols and stability tiers are defined in [VERSIONING.md](VERSIONING.md).

## 10. Machine-Readable Specification Alignment

```yaml
contributing:
  commit:
    standard: conventional
    enforced: true
  branching:
    pattern: "<type>/[scope]/<description>"
    enforced: true
  versioning:
    standard: semver
  validation:
    required:
      - commit
      - test
```

---

*This guide is normative for all contributors to the `contributing-specification` repository.*
