---
first published: 2026-04-16
last updated: 2026-04-16T10:30:00Z
version: 0.1.0
---

#            Repository CONTRIBUTING.md Specification (Version 0.1.0)

```text
   Independent Submission                                        W. Soudan
   Request for Comments: —                                     Independent
   Category: Informational                                   16 April 2026
```

## Abstract

   This document specifies version 0.1.0 of the Repository CONTRIBUTING.md
   Specification. It defines the structure, content, and presentation
   of repository contribution guidelines, with integrated validation schema 
   and commit message standards.

## Status of This Memo

   This is an Independent Submission for the RFC Series. It represents
   the consensus of the opensource community. It does not deliver
   an Internet Standards Track specification; it is published for
   informational purposes.

## Copyright Notice

   Copyright (c) 2026 Dr Wouter Soudan.  All rights reserved.

## Table of Contents

- [0. Front Matter](#0-front-matter)
- [1. Introduction](#1-introduction)
- [2. Conceptual Model](#2-conceptual-model)
- [3. Structural Specification](#3-structural-specification)
- [4. Content Requirements](#4-content-requirements)
- [5. Visual and Formatting Specification](#5-visual-and-formatting-specification)
- [6. Writing Style Specification](#6-writing-style-specification)
- [7. Advanced Enhancements](#7-advanced-enhancements)
- [8. Anti-patterns](#8-anti-patterns)
- [9. Validation and Compliance](#9-validation-and-compliance)
- [10. Repository Context Integration](#10-repository-context-integration)
- [11. Adaptation and Overrides](#11-adaptation-and-overrides)
- [Appendices](#appendices)
    - [A. Commit Message Specification (CMS)](#a-commit-message-specification-cms)
    - [B. Validator Specification](#b-validator-specification)
    - [C. Machine-Readable Rule Catalog](#c-machine-readable-rule-catalog)

---

## 0. Front Matter

### 0.1 Document Metadata
This document is titled _“Repository CONTRIBUTING Specification (RCS)”_. It defines a normative standard for the structure, content, and enforcement of repository contribution guidelines.

### 0.2 Abstract
The purpose of this specification is to define a consistent, rigorous, and practical standard for `CONTRIBUTING.md` files. It establishes requirements that ensure contribution guidelines are clear, actionable, and enforceable, serving as a formal protocol for repository collaboration.

### 0.3 Terminology and Conventions
The key words “MUST”, “SHOULD”, and “MAY” are to be interpreted as described in RFC 2119.

---

## 1. Introduction

### 1.1 Motivation
The `CONTRIBUTING.md` file functions as the primary interface between a repository and its contributors. In many repositories, these guidelines are either missing, vague, or unenforceable.

### 1.2 Objectives
1. Establishing normative standards for collaboration.
2. Enabling machine-checkability of contribution workflows.
3. Reducing friction for new contributors (human and agentic).

---

## 2. Conceptual Model

### 2.1 Contributing as a Protocol
A `CONTRIBUTING.md` document is not merely documentation; it is a **formal collaboration protocol** that defines the transformation of external intent into merged changes.

### 2.2 Dual Audience
The document MUST be authored for a dual audience:
- **Human contributors**: Clear prose, examples, and welcoming tone.
- **Agentic contributors**: Structured, deterministic rules and machine-readable metadata.

### 2.3 Enforcement Alignment
Any rule defined in `CONTRIBUTING.md` SHOULD be backed by an automated enforcement mechanism (e.g., CI, linters, git hooks).

---

## 3. Structural Specification

### 3.1 Required Sections (Normative)
A compliant `CONTRIBUTING.md` MUST include:
1. **Overview / Welcome**: What contributions are welcome and project scope.
2. **Contribution Lifecycle**: The stages from discovery to merge.
3. **Development Workflow**: Branching, environment setup, and commit rules.
4. **Validation & Enforcement**: What checks must pass and how they are run.
5. **Pull Request Protocol**: Requirements for submission and review process.

### 3.2 Recommended Sections
1. **Getting Started**: Setup instructions and tools.
2. **Issue Reporting**: Templates and guidelines for bugs/features.
3. **Code & Documentation Standards**: Linters, style guides, and naming conventions.
4. **Release & Versioning**: Mapping commits to releases (e.g., SemVer).
5. **Communication**: Channels for discussion and escalation.

### 3.3 Section Ordering
Information MUST follow the principle of **progressive disclosure**, moving from high-level onboarding to technical protocol details.

---

## 4. Content Requirements

### 4.1 Normative Language
Requirements MUST be stated clearly using normative words. Vague instructions like "try to keep code clean" SHOULD be replaced with "Code MUST pass ESLint verification".

### 4.2 Lifecycle Definition
The lifecycle SHOULD follow the canonical model:
`discover → discuss → implement → validate → submit → review → merge`.

---

## 5. Visual and Formatting Specification
(Analogous to RRS §5: GFM compliance, stable anchors, clear hierarchy).

---

## 6. Writing Style Specification
(Analogous to RRS §6: Technical precision, neutral confidence, active voice).

### 6.1 Imperative Mood
Instructions and commit message subjects MUST use the imperative mood (e.g., "Add feature" instead of "Added feature").

---

## 7. Advanced Enhancements
Automation of the contribution flow via CI-driven updates, auto-release systems, and agentic validation.

---

## 8. Anti-patterns
1. **Metadata-first walls**: Badges before the title.
2. **Undocumented rules**: Rules enforced by CI but not mentioned in the doc.
3. **Template rot**: Empty or placeholder sections.

---

## 9. Validation and Compliance

### 9.1 Compliance Levels
- **Minimal**: File exists, lifecycle defined.
- **Standard**: Commit convention defined, CI enforcement present.
- **Full**: Machine-readable schema, full toolchain, automated validation.

---

## 10. Repository Context Integration
Integration with `.editorconfig`, `commitlint.config.js`, and GitHub Actions.

---

## 11. Adaptation and Overrides
Repositories MAY override default conventions (e.g., replacing Conventional Commits with a custom grammar) provided the override is:
1. Explicitly declared.
2. Formally specified (grammar + examples).
3. Enforced by a detectable tool.

---

## Appendices

### A. Commit Message Specification (CMS)

#### A.1 Overview
This appendix defines the normative requirements for Git commit messages.

#### A.2 Grammar (EBNF)
```ebnf
commit        = header, [ newline, body ], [ newline, footer ] ;
header        = type, [ "(", scope, ")" ], [ "!" ], ":", space, subject ;
type          = "feat" | "fix" | "docs" | "refactor" | "test" | "chore" | "spec" | "lex" | "phon" | "build" | "ci" | "style" | "perf" | "revert" ;
scope         = identifier, { ( "-" | "," | "/" ), identifier } ;
subject       = text ;
```

#### A.3 Normative Rules
1. **Subject Length**: SHOULD NOT exceed 72 characters.
2. **Imperative Mood**: Subjects MUST use the imperative.
3. **Semantic Intent**: Types MUST reflect the intent (e.g., `refactor` for non-functional code changes).
4. **Breaking Changes**: MUST be indicated by `!` in the header or `BREAKING CHANGE:` in the footer.

---

### B. Validator Specification

#### B.1 Overview
The CONTRIBUTING Validator assesses the alignment between the documentation (prose) and the repository state (config files).

#### B.2 Validation Layers
1. **Discovery**: Locating `CONTRIBUTING.md`, `.editorconfig`, `commitlint`, etc.
2. **Extraction**: Inferring stated policies from Markdown AST.
3. **Execution**: Running rules against the extracted model.
4. **Diagnostics**: Emitting structured errors (e.g., "Commit enforcement claimed but no config found").

---

### C. Machine-Readable Rule Catalog

#### C.1 YAML Schema
```yaml
rules:
  - id: C001
    class: presence
    severity: error
    title: CONTRIBUTING.md must exist
    check: { file_exists: "CONTRIBUTING.md" }

  - id: C100
    class: structural
    severity: error
    title: Overview section required
    check: { section_exists: "overview" }

  - id: C202
    class: semantic
    severity: error
    title: Commit convention must be defined
    check: { policy_declared: "commit_policy" }

  - id: C301
    class: consistency
    severity: error
    title: Commitlint reference must match config
    applies_if: { reference_declared: "commitlint" }
    check: { any: [{ file_exists: "commitlint.config.js" }, { config_exists: "package_json_commitlint" }] }
```

#### C.2 Compliance Tiers
- **Minimal**: [C001, C100, C101, C102, C103, C104, C202]
- **Standard**: [minimal, C200, C201, C300, C301, C302]
- **Full**: [standard, C303, C400, C401, C500, C501]
