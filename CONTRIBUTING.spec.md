📜 CONTRIBUTING.md Specification
================================

**Version:** 1.0.0  
**Status:** Draft Standard  
**Scope:** Repository Collaboration Protocol

* * *

1\. Overview
============

This specification defines the **structure, semantics, and enforcement model** for `CONTRIBUTING.md` files in software repositories.

A `CONTRIBUTING.md` document serves as the **canonical collaboration protocol**, governing how contributors—human or agentic—propose, implement, validate, and submit changes.

The specification aims to ensure:

*   clarity and accessibility for contributors
*   deterministic, machine-checkable workflows
*   alignment between documentation and enforcement
*   extensibility across different project conventions

* * *

2\. Design Principles
=====================

2.1 Single Entry Point
----------------------

`CONTRIBUTING.md` MUST serve as the **primary index** for all contribution-related rules.

It MAY reference external documents but MUST NOT delegate essential rules without summary.

* * *

2.2 Progressive Disclosure
--------------------------

Information MUST be structured hierarchically:

*   high-level overview in `CONTRIBUTING.md`
*   detailed rules in referenced documents

* * *

2.3 Dual Audience
-----------------

The document MUST be:

*   human-readable (clear prose)
*   agent-interpretable (structured, deterministic rules)

* * *

2.4 Enforcement Alignment
-------------------------

All normative rules defined in `CONTRIBUTING.md` SHOULD be:

*   machine-checkable
*   enforced via tooling (CI, linters, hooks)

* * *

2.5 Extensibility
-----------------

Repositories MAY override:

*   commit conventions
*   versioning systems
*   branching models

provided these are:

*   explicitly declared
*   machine-readable
*   enforced

* * *

3\. Normative Structure
=======================

3.1 Required Sections
---------------------

A compliant `CONTRIBUTING.md` MUST include:

1.  Overview / Welcome
2.  Contribution Lifecycle
3.  Development Workflow
4.  Validation & Enforcement
5.  Pull Request Protocol

* * *

3.2 Recommended Sections
------------------------

The following SHOULD be included:

*   Getting Started
*   Issue Reporting
*   Code & Documentation Standards
*   Release & Versioning
*   Communication

* * *

3.3 Optional Sections
---------------------

*   Security disclosures
*   Governance
*   Domain-specific workflows

* * *

4\. Contribution Lifecycle
==========================

The lifecycle MUST be defined explicitly.

Canonical model:

```
discover → discuss → implement → validate → submit → review → merge
```

Each stage SHOULD include:

*   purpose
*   expected actions
*   tooling involved

* * *

5\. Development Workflow
========================

5.1 Branching
-------------

Repositories MUST define:

*   whether branching is required
*   naming conventions

Example:

```
<type>/<scope>/<description>
```

* * *

5.2 Commit Messages
-------------------

### 5.2.1 Normative Reference

Commit messages MUST follow:

👉 Conventional Commits

* * *

### 5.2.2 Project Extensions

Repositories MAY extend:

*   commit types
*   scope taxonomy
*   validation rules

These MUST be:

*   documented
*   enforced via tooling

* * *

### 5.2.3 Overrides

If an alternative convention is used:

*   it MUST be explicitly declared
*   it MUST define:
    *   grammar
    *   examples
    *   validation mechanism

* * *

5.3 Commit Semantics
--------------------

Commits SHOULD:

*   represent a single logical change
*   use imperative mood
*   encode intent, not file type

* * *

6\. Validation & Enforcement
============================

6.1 Principle
-------------

All critical rules MUST be enforceable.

* * *

6.2 Required Tooling
--------------------

A compliant repository MUST include:

### 6.2.1 Formatting

*   `.editorconfig`

* * *

### 6.2.2 Code Quality

*   linter configuration (e.g. ESLint, Prettier)

* * *

### 6.2.3 Commit Validation

*   commit message linter (e.g. commitlint)

* * *

### 6.2.4 Continuous Integration

*   CI pipeline validating:
    *   commits
    *   build
    *   tests
    *   linting

* * *

6.3 Enforcement Model
---------------------

| Rule Type | Enforcement |
| --- | --- |
| formatting | editor / CI |
| code style | linter |
| commits | commitlint |
| workflow | CI |

* * *

6.4 Example Toolchain
---------------------

```
.editorconfig
.eslintrc
.prettierrc
commitlint.config.js
.github/workflows/*.yml
```

* * *

7\. Pull Request Protocol
=========================

Repositories MUST define:

7.1 Submission Requirements
---------------------------

*   passing CI
*   valid commit messages
*   updated documentation

* * *

7.2 Structure
-------------

Pull requests SHOULD include:

*   description
*   rationale
*   linked issues

* * *

7.3 Templates
-------------

Repositories SHOULD use:

*   `.github/PULL_REQUEST_TEMPLATE.md`

* * *

7.4 Review Process
------------------

Define:

*   approval requirements
*   review roles
*   merge conditions

* * *

8\. Code & Documentation Standards
==================================

Repositories SHOULD define:

*   coding standards
*   documentation conventions

These MAY be:

*   embedded
*   referenced (e.g. `docs/style/`)

* * *

9\. Release & Versioning
========================

9.1 Default Standard
--------------------

Repositories SHOULD follow:

👉 Semantic Versioning

* * *

9.2 Overrides
-------------

If an alternative versioning system is used:

It MUST define:

*   version format
*   increment rules
*   mapping from commits to versions

* * *

9.3 Automation
--------------

Versioning SHOULD be:

*   automated via CI
*   derived from commit messages

* * *

10\. Machine-Readable Specification
===================================

A compliant repository SHOULD provide:

```
contributing:
  commit:
    standard: conventional
    enforced: true
    config: commitlint.config.js

  branching:
    pattern: "<type>/<scope>/<description>"

  validation:
    required:
      - lint
      - test
      - build
      - commit

  versioning:
    standard: semver
    automated: true
```

* * *

11\. External File Requirements
===============================

To be compliant, the repository MUST include:

*   `.editorconfig`
*   lint configuration(s)
*   commitlint configuration (or equivalent)
*   CI workflow configuration

* * *

12\. Compliance Levels
======================

12.1 Minimal
------------

*   CONTRIBUTING.md present
*   lifecycle defined

* * *

12.2 Standard
-------------

*   commit convention defined
*   CI enforcement present

* * *

12.3 Full (Recommended)
-----------------------

*   machine-readable schema
*   full toolchain
*   automated validation

* * *

13\. Extension Mechanism
========================

Repositories MAY extend:

*   commit types
*   workflow steps
*   validation rules

All extensions MUST:

*   be documented
*   be machine-enforceable

* * *

14\. Anti-Patterns
==================

The following are non-compliant:

*   undocumented contribution rules
*   rules not enforced by tooling
*   fragmented instructions across files without index
*   ambiguous commit conventions

* * *

15\. Rationale
==============

This specification ensures:

*   consistency across contributors
*   automation compatibility
*   reduced onboarding friction
*   alignment between documentation and behavior

* * *

16\. Relationship to Other Specifications
=========================================

This document complements:

*   README.md (orientation)
*   AGENTS.md (agent execution)

`CONTRIBUTING.md` governs **collaboration and change production**.

* * *

17\. Future Extensions
======================

Possible future modules:

*   security contribution protocol
*   governance models
*   contributor reputation systems

* * *

✅ Result
========

You now have:

*   a **complete RFC-grade CONTRIBUTING specification**
*   aligned with:
    *   real-world practice
    *   commitlint ecosystem
    *   CI enforcement
    *   your SpecLang philosophy

* * *

Next Step
=========

We can now:

1.  Generate a **real-world `CONTRIBUTING.md` file** from this spec
2.  Build a **validator CLI (like your README validator)**
3.  Integrate into your **SpecLang ecosystem**

* * *

If you want precision:

👉 Next best move = **design the validator + rule engine for this spec**

## Prompt:
16-4-2026, 11:47:49

Yes, please design the validator and the rule engine for this spec.

## Response:
16-4-2026, 11:47:51

I’m moving from the document spec to the executable model now: rule taxonomy, file discovery, diagnostics, compliance levels, and how prose rules map to machine checks. Then I’ll turn that into a concrete validator architecture and config format.

> Nagedacht gedurende 5s

Below is a **contract-grade validator and rule-engine design** for the `CONTRIBUTING.md` specification, modeled in the same spirit as the README validator work: normative, modular, machine-checkable, and extensible.

* * *

CONTRIBUTING Validator Specification
====================================

1\. Overview
------------

This specification defines a validator that checks whether a repository complies with the `CONTRIBUTING.md` specification.

The validator MUST assess not only the presence and structure of `CONTRIBUTING.md`, but also whether the repository contains the **supporting enforcement artifacts** that the document claims or requires, such as `.editorconfig`, commit-linting configuration, and CI workflows. The validator therefore operates at two levels:

1.  **Document-level compliance**  
    The `CONTRIBUTING.md` file itself: presence, structure, semantic sections, references, declared conventions.
2.  **Repository-level compliance**  
    The surrounding repository state: config files, hooks, workflow files, machine-readable policy declarations.

The validator SHOULD support both:

*   **strict conformance validation**
*   **advisory best-practice diagnostics**

* * *

2\. Validator Goals
-------------------

The validator MUST be able to answer the following questions:

1.  Does the repository contain a valid `CONTRIBUTING.md`?
2.  Does that file contain the required semantic sections?
3.  Are declared conventions explicit and unambiguous?
4.  Are machine-enforceable claims backed by actual config files?
5.  Are extensions and overrides properly declared?
6.  What compliance tier does the repository achieve?

* * *

3\. Validation Model
--------------------

The validator SHALL implement a **multi-layer rule engine**.

### 3.1 Layers

```
filesystem discovery
→ document extraction
→ semantic section parsing
→ policy extraction
→ repository artifact inspection
→ rule evaluation
→ diagnostics emission
→ compliance scoring
```

### 3.2 Rule Classes

The rule engine MUST distinguish at least the following rule classes:

| Class | Meaning |
| --- | --- |
| Presence | required file exists |
| Structural | required headings/sections exist |
| Semantic | required content intent is present |
| Referential | referenced files exist |
| Consistency | declarations match repository files |
| Enforcement | rules are backed by tooling |
| Extension | custom conventions are declared correctly |
| Advisory | recommended but non-blocking best practices |

* * *

4\. Inputs
----------

The validator MUST accept at least the following inputs:

### 4.1 Repository root

A local filesystem path or repository checkout root.

### 4.2 Primary target file

Default target:

```
CONTRIBUTING.md
```

The validator MAY also support:

*   `docs/CONTRIBUTING.md`
*   alternate configured path

### 4.3 Optional config

A validator-specific config file, for example:

```
contributinglint.config.yaml
```

This MAY define:

*   alternate contributing file locations
*   custom section aliases
*   custom convention identifiers
*   disabled rules
*   repository profile presets

* * *

5\. Discovery Phase
-------------------

5.1 File discovery
------------------

The validator MUST search for:

*   `CONTRIBUTING.md`
*   `.editorconfig`
*   commit convention config
*   formatter / linter configs
*   CI workflow files
*   optional machine-readable collaboration schema

### 5.2 Candidate files

The validator SHOULD inspect at least:

```
CONTRIBUTING.md
.editorconfig
commitlint.config.js
commitlint.config.cjs
commitlint.config.mjs
commitlint.config.ts
package.json
.github/workflows/*.yml
.github/workflows/*.yaml
.eslintrc
.eslintrc.js
.eslintrc.cjs
.eslintrc.json
eslint.config.js
eslint.config.mjs
.prettierrc
.prettierrc.json
.prettierrc.yaml
.prettierrc.yml
.prettierrc.js
docs/style/*
docs/contributing/*
```

### 5.3 Package.json inspection

The validator SHOULD inspect `package.json` for:

*   `commitlint`
*   lint scripts
*   test scripts
*   build scripts
*   release scripts

Example signals:

```
{
  "scripts": {
    "lint": "eslint .",
    "test": "vitest run",
    "build": "tsup",
    "commitlint": "commitlint --from=HEAD~1 --to=HEAD"
  }
}
```

* * *

6\. Document Parsing
--------------------

6.1 Markdown parsing
--------------------

The validator MUST parse `CONTRIBUTING.md` as Markdown into an AST.

The parser SHOULD preserve:

*   heading hierarchy
*   paragraphs
*   lists
*   fenced code blocks
*   tables
*   links

6.2 Section extraction
----------------------

The validator MUST extract sections by heading and normalize them to semantic section types.

### 6.3 Section aliases

Because repositories vary, the validator MUST support alias mapping.

Example:

| Semantic section | Acceptable heading examples |
| --- | --- |
| overview | Overview, Welcome, Contributing, How to Contribute |
| lifecycle | Contribution Lifecycle, Workflow, Process |
| getting\_started | Getting Started, Setup, Development Setup |
| issue\_reporting | Reporting Issues, Issues, Bug Reports |
| development\_workflow | Development Workflow, Git Workflow, Workflow Rules |
| validation | Validation, Checks, CI, Enforcement |
| pull\_requests | Pull Requests, PRs, Submitting Changes |
| standards | Code Standards, Style, Coding Standards, Documentation Standards |
| release\_versioning | Release, Versioning, Releases |
| communication | Communication, Questions, Support |

Section aliasing MUST be configurable.

* * *

7\. Semantic Extraction
-----------------------

The validator MUST attempt to extract the following policy facts from the document.

7.1 Commit policy
-----------------

Detect:

*   whether a commit message convention is declared
*   whether Conventional Commits is referenced
*   whether deviations/extensions are defined
*   whether local enforcement is described
*   whether CI enforcement is described

### Extracted shape

```
commit_policy:
  declared: true
  standard: conventional
  extends_standard: true
  custom_types:
    - spec
    - lex
  enforcement:
    local: true
    ci: true
  config_ref:
    - commitlint.config.js
```

7.2 Branching policy
--------------------

Detect:

*   whether branching model is defined
*   naming pattern
*   whether branches are required or optional

7.3 Validation policy
---------------------

Detect declared required checks, such as:

*   lint
*   test
*   build
*   typecheck
*   commit validation

7.4 Versioning policy
---------------------

Detect:

*   SemVer reference
*   alternative versioning standard
*   whether mapping rules are documented
*   whether automation is claimed

7.5 Referenced files
--------------------

The validator MUST collect file references from prose and code spans when they appear to denote repository artifacts.

Example:

*   `.editorconfig`
*   `.github/workflows/ci.yml`
*   `commitlint.config.js`

* * *

8\. Repository Artifact Inspection
----------------------------------

8.1 EditorConfig
----------------

If the contributing spec or repository profile requires formatting enforcement, `.editorconfig` MUST exist.

The validator MAY check that it is syntactically parseable.

8.2 Commit linting
------------------

If commit policy claims machine enforcement, the validator MUST verify one of the following:

1.  A recognized commitlint config file exists
2.  `package.json` contains a commitlint config
3.  CI references commitlint
4.  Hook scripts reference commitlint

Recognized signals include:

*   `@commitlint/config-conventional`
*   `commitlint --edit`
*   GitHub Action for commit linting

8.3 CI workflows
----------------

If the document claims CI enforcement, at least one workflow file MUST exist under `.github/workflows/`.

The validator SHOULD inspect workflows for signals such as:

*   lint job
*   test job
*   build job
*   commit validation job

This check MAY be heuristic unless a stricter mode is enabled.

8.4 Linters and formatters
--------------------------

If the document claims code style enforcement, corresponding configuration SHOULD exist.

Signals include:

*   ESLint config
*   Prettier config
*   Biome config
*   other configured alternatives

The validator MUST permit alternatives if explicitly declared.

* * *

9\. Rule Engine
---------------

9.1 Rule format
---------------

Each rule MUST be represented as structured data.

```
id: contributing.required.overview
severity: error
class: structural
description: CONTRIBUTING.md must contain an overview section
applies_if:
  all:
    - file_exists: CONTRIBUTING.md
check:
  section_exists: overview
```

9.2 Rule schema
---------------

```
rule:
  id: string
  severity: error|warning|info
  class: presence|structural|semantic|referential|consistency|enforcement|extension|advisory
  description: string
  rationale: string
  applies_if: condition
  check: predicate
  remediation: string
```

9.3 Evaluation model
--------------------

Rules MUST be evaluated deterministically.

A rule produces exactly one of:

*   pass
*   fail
*   skipped
*   indeterminate

### Meanings

*   **pass**: condition satisfied
*   **fail**: condition violated
*   **skipped**: not applicable
*   **indeterminate**: insufficient evidence

Indeterminate SHOULD be used sparingly, mainly for heuristic checks.

* * *

10\. Core Rules
---------------

10.1 Presence rules
-------------------

### C001

`CONTRIBUTING.md` MUST exist.

### C002

If the repository claims machine-enforced formatting, `.editorconfig` MUST exist.

### C003

If the repository claims commit enforcement, a recognized commit-lint config MUST exist.

### C004

If the repository claims CI enforcement, at least one CI workflow file MUST exist.

* * *

10.2 Structural rules
---------------------

### C100

An overview section MUST exist.

### C101

A contribution lifecycle or equivalent workflow section MUST exist.

### C102

A development workflow section MUST exist.

### C103

A validation/enforcement section MUST exist.

### C104

A pull request protocol section MUST exist.

* * *

10.3 Recommended structural rules
---------------------------------

### C150

A getting started section SHOULD exist.

### C151

An issue reporting section SHOULD exist.

### C152

A standards section SHOULD exist.

### C153

A release/versioning section SHOULD exist.

### C154

A communication section SHOULD exist.

* * *

10.4 Semantic rules
-------------------

### C200

The document MUST describe how contributors submit changes.

### C201

The document MUST describe how changes are validated before merge.

### C202

The document MUST define or reference a commit message convention.

### C203

If a branching model is used, branch naming or branching rules MUST be stated.

### C204

If an alternative versioning standard is used, it MUST be named and described.

* * *

10.5 Consistency rules
----------------------

### C300

If the document references `.editorconfig`, that file MUST exist.

### C301

If the document references `commitlint`, supporting configuration MUST exist.

### C302

If the document says “all PRs must pass CI”, CI workflow files MUST exist.

### C303

If the document says “we use Conventional Commits with custom types”, those custom types SHOULD appear in commitlint config.

### C304

If the document claims SemVer automation, release automation config SHOULD exist or the claim SHOULD be explicitly marked manual.

* * *

10.6 Enforcement rules
----------------------

### C400

Every declared machine-enforced rule SHOULD map to at least one detectable repository artifact.

### C401

If commit messages are mandatory, at least one local or CI enforcement mechanism MUST be detectable.

### C402

If linting is required before merge, a lint script or workflow step SHOULD be detectable.

* * *

10.7 Extension rules
--------------------

### C500

Custom commit conventions MUST include:

*   convention name
*   grammar summary or normative reference
*   validation mechanism

### C501

Custom versioning systems MUST include:

*   version format
*   increment semantics
*   release decision rule

### C502

Repository-specific section aliases MAY be used only if configured or inferable.

* * *

11\. Compliance Levels
----------------------

The validator MUST compute compliance tiers.

11.1 Minimal
------------

Requirements:

*   `CONTRIBUTING.md` exists
*   required core sections exist
*   commit convention referenced
*   pull request protocol exists

11.2 Standard
-------------

Requirements:

*   Minimal plus
*   declared conventions are explicit
*   enforcement section exists
*   supporting files exist for major declared rules
*   CI detectable

11.3 Full
---------

Requirements:

*   Standard plus
*   machine-readable collaboration schema exists
*   config/doc consistency is high
*   extension declarations are formalized
*   most advisory rules pass

* * *

12\. Diagnostics Model
----------------------

12.1 Diagnostic schema
----------------------

```
diagnostic:
  id: C301
  level: error
  title: Commit enforcement declared but no commitlint configuration found
  message: CONTRIBUTING.md states that commit messages are validated, but no recognized commitlint configuration was detected.
  evidence:
    file: CONTRIBUTING.md
    section: Development Workflow
  remediation:
    - Add commitlint.config.js or equivalent
    - Or revise the document to describe the actual validation mechanism
  rule_class: consistency
  status: fail
```

12.2 Severity levels
--------------------

| Level | Meaning |
| --- | --- |
| error | blocks compliance at current tier |
| warning | non-blocking but important |
| info | advisory improvement |

12.3 Output modes
-----------------

The validator SHOULD support:

*   human-readable text
*   JSON
*   YAML
*   SARIF

* * *

13\. Suggested CLI
------------------

13.1 Commands
-------------

```
contributinglint validate .
contributinglint validate . --format json
contributinglint explain C301
contributinglint rules
contributinglint init
```

13.2 Exit codes
---------------

| Code | Meaning |
| --- | --- |
| 0 | validation passed |
| 1 | one or more error-level failures |
| 2 | invalid invocation or config error |
| 3 | parse failure |
| 4 | target file missing |

* * *

14\. Config Format
------------------

A validator config SHOULD allow controlled customization.

Example:

```
version: 1
contributing:
  paths:
    - CONTRIBUTING.md
    - docs/CONTRIBUTING.md

  section_aliases:
    overview:
      - welcome
      - how to contribute
    development_workflow:
      - git workflow
      - workflow rules

  commit:
    standard: conventional
    allow_alternatives: true
    accepted_alternatives:
      - gitmoji
      - custom

  versioning:
    default: semver
    allow_alternatives: true

  rules:
    disable:
      - C153
    severity:
      C304: warning
```

* * *

15\. Convention Abstraction Layer
---------------------------------

This is the key extensibility point.

The validator MUST NOT hard-code only Conventional Commits or only SemVer. Instead it SHOULD use named convention adapters.

15.1 Commit convention adapters
-------------------------------

Examples:

*   `conventional`
*   `gitmoji`
*   `custom`

Each adapter MUST define:

*   identifier
*   normative reference
*   minimal grammar expectations
*   enforcement detection strategy

### Example

```
commit_convention_adapter:
  id: conventional
  reference: https://www.conventionalcommits.org/
  requires:
    - type
    - subject
  enforcement_signals:
    - commitlint
```

15.2 Versioning convention adapters
-----------------------------------

Examples:

*   `semver`
*   `calver`
*   `custom`

Each versioning adapter MUST define:

*   format
*   increment model
*   detection strategy
*   required declaration fields for custom use

* * *

16\. Heuristic vs Strict Modes
------------------------------

The validator SHOULD provide at least two modes.

16.1 Strict mode
----------------

*   tighter section requirements
*   stronger artifact consistency checks
*   fewer inferred passes

16.2 Heuristic mode
-------------------

*   more alias tolerance
*   more semantic inference
*   better for real-world repositories

* * *

17\. Parsing Strategy
---------------------

17.1 Recommended implementation architecture
--------------------------------------------

For TypeScript:

```
packages/
  contributinglint-core/
  contributinglint-cli/
  contributinglint-rules/
  contributinglint-adapters/
  contributinglint-reporters/
```

17.2 Core modules
-----------------

| Module | Responsibility |
| --- | --- |
| discovery | locate files |
| markdown | parse AST |
| sections | normalize headings |
| extraction | infer policies |
| rules | evaluate predicates |
| adapters | support alternative conventions |
| diagnostics | emit findings |
| reporters | CLI/JSON/SARIF output |

* * *

18\. Internal Data Model
------------------------

Example normalized repository model:

```
repository:
  files:
    contributing: CONTRIBUTING.md
    editorconfig: .editorconfig
    ci_workflows:
      - .github/workflows/ci.yml
    commit_configs:
      - commitlint.config.js

  contributing:
    sections:
      overview: true
      lifecycle: true
      development_workflow: true
      validation: true
      pull_requests: true
      standards: true
    policies:
      commit:
        declared: true
        standard: conventional
        custom_types:
          - spec
      versioning:
        declared: true
        standard: semver
      ci:
        declared: true
        checks:
          - lint
          - test
          - build
```

* * *

19\. Example Rule Evaluation
----------------------------

### Rule

C303: Custom Conventional Commit types documented in CONTRIBUTING.md SHOULD appear in commitlint config.

### Inputs

Document says:

*   standard: conventional
*   custom types: `spec`, `lex`

Commitlint config says:

*   type-enum includes `spec`, not `lex`

### Result

```
id: C303
status: fail
level: warning
message: CONTRIBUTING.md declares custom commit type "lex" but it was not found in commitlint configuration.
```

* * *

20\. Validator Scope Boundaries
-------------------------------

The validator MUST NOT:

*   parse the entire Git history by default
*   prove that hooks are installed locally on every contributor machine
*   assume GitHub-specific workflows unless configured
*   enforce a specific convention unless declared by the repository or by profile

The validator MAY optionally provide extended checks for:

*   commit history sampling
*   release tag inspection
*   branch naming history

These SHOULD be opt-in.

* * *

21\. Recommended Profiles
-------------------------

The validator MAY ship with presets.

### 21.1 OSS profile

*   higher tolerance
*   heuristic aliases
*   recommends issue reporting and communication sections

### 21.2 Enterprise profile

*   stricter enforcement
*   mandatory CI checks
*   mandatory explicit branching and review rules

### 21.3 Agent-first profile

*   stronger machine-readable requirements
*   stronger consistency between docs and config
*   recommended collaboration schema

* * *

22\. Relationship to CONTRIBUTING.md Spec
-----------------------------------------

This validator is the executable counterpart of the `CONTRIBUTING.md` specification.

The governing principle is:

> prose defines policy; config enforces policy; the validator checks their alignment.

* * *

23\. Implementation Sketch in TypeScript
----------------------------------------

A minimal rule interface:

```
export type RuleStatus = 'pass' | 'fail' | 'skipped' | 'indeterminate';

export interface Diagnostic {
  id: string;
  level: 'error' | 'warning' | 'info';
  title: string;
  message: string;
  status: RuleStatus;
  evidence?: {
    file?: string;
    section?: string;
    excerpt?: string;
  };
  remediation?: string[];
}

export interface RuleContext {
  repoRoot: string;
  files: DiscoveredFiles;
  document?: ParsedContributingDoc;
  model: NormalizedRepositoryModel;
  config: ValidatorConfig;
}

export interface Rule {
  id: string;
  description: string;
  run(ctx: RuleContext): Diagnostic | null;
}
```

A section-normalization shape:

```
export interface ParsedContributingDoc {
  path: string;
  headings: Array<{
    depth: number;
    raw: string;
    normalized?: SemanticSectionName;
    content: string;
  }>;
  references: string[];
  extractedPolicies: ExtractedPolicies;
}
```

* * *

24\. Recommended Roadmap
------------------------

Build order:

1.  file discovery
2.  Markdown section parser
3.  semantic section normalizer
4.  core rule engine
5.  diagnostics/reporters
6.  artifact consistency checks
7.  convention adapters
8.  optional history checks

* * *

25\. First Useful MVP
---------------------

A practical MVP validator should implement:

*   C001–C104
*   C200–C203
*   C300–C303
*   JSON and text output
*   configurable aliases
*   Conventional Commits + SemVer adapters

That gets you to a useful first release quickly.

* * *

The next best step is to formalize the **rule catalogue** as a machine-readable YAML schema and then sketch the **exact package layout and CLI UX**.

## Prompt:
16-4-2026, 12:03:19

All right, please go ahead and formalize the rule catalog as a machine-readable YAML schema.

## Response:
16-4-2026, 12:03:19

Below is a **formal, machine-readable YAML schema for the rule catalog** of the `CONTRIBUTING.md` validator. It is designed to be:

*   **complete** (covers all rule classes)
*   **extensible** (supports custom rules and adapters)
*   **deterministic** (clear evaluation model)
*   **compatible** with your SpecLang / SPS direction

* * *

📦 `contributinglint.rules.yaml` — Rule Catalog Schema
======================================================

```
version: 1.0.0

meta:
  name: contributinglint-rule-catalog
  description: >
    Canonical rule definitions for validating CONTRIBUTING.md compliance
    and repository enforcement alignment.
  authors:
    - contributinglint
  license: MIT

# -------------------------------------------------------------------
# GLOBAL ENUMS
# -------------------------------------------------------------------

enums:
  severity:
    - error
    - warning
    - info

  rule_class:
    - presence
    - structural
    - semantic
    - referential
    - consistency
    - enforcement
    - extension
    - advisory

  rule_status:
    - pass
    - fail
    - skipped
    - indeterminate

  condition_operator:
    - all
    - any
    - not

# -------------------------------------------------------------------
# CONDITION DSL
# -------------------------------------------------------------------

condition_definitions:

  file_exists:
    type: string
    description: File must exist relative to repo root

  section_exists:
    type: string
    description: Semantic section must exist in CONTRIBUTING.md

  section_contains:
    type: object
    properties:
      section: string
      pattern: string

  config_exists:
    type: string
    description: Named config file or config type exists

  reference_declared:
    type: string
    description: Document references a file or concept

  policy_declared:
    type: string
    description: Policy extracted from document exists

  artifact_detected:
    type: string
    description: Tooling artifact detected in repository

  value_equals:
    type: object
    properties:
      path: string
      value: any

  value_in:
    type: object
    properties:
      path: string
      values: array

# -------------------------------------------------------------------
# RULE DEFINITIONS
# -------------------------------------------------------------------

rules:

  # ================================================================
  # PRESENCE RULES
  # ================================================================

  - id: C001
    class: presence
    severity: error
    title: CONTRIBUTING.md must exist
    description: Repository must contain a CONTRIBUTING.md file
    rationale: >
      CONTRIBUTING.md is the canonical collaboration protocol entry point.
    applies_if:
      all: []
    check:
      file_exists: CONTRIBUTING.md
    remediation:
      - Create a CONTRIBUTING.md file at repository root

  - id: C002
    class: presence
    severity: error
    title: .editorconfig required if formatting is declared
    description: EditorConfig must exist if formatting enforcement is declared
    applies_if:
      all:
        - policy_declared: formatting_enforced
    check:
      file_exists: .editorconfig
    remediation:
      - Add a .editorconfig file

  - id: C003
    class: presence
    severity: error
    title: Commitlint config required if commit enforcement is declared
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      any:
        - file_exists: commitlint.config.js
        - file_exists: commitlint.config.cjs
        - file_exists: commitlint.config.mjs
        - file_exists: commitlint.config.ts
        - config_exists: package_json_commitlint
    remediation:
      - Add commitlint configuration file

  - id: C004
    class: presence
    severity: error
    title: CI workflow required if CI enforcement is declared
    applies_if:
      all:
        - policy_declared: ci_enforced
    check:
      config_exists: ci_workflows
    remediation:
      - Add CI workflow under .github/workflows/

  # ================================================================
  # STRUCTURAL RULES
  # ================================================================

  - id: C100
    class: structural
    severity: error
    title: Overview section required
    check:
      section_exists: overview

  - id: C101
    class: structural
    severity: error
    title: Contribution lifecycle required
    check:
      any:
        - section_exists: lifecycle
        - section_exists: workflow

  - id: C102
    class: structural
    severity: error
    title: Development workflow required
    check:
      section_exists: development_workflow

  - id: C103
    class: structural
    severity: error
    title: Validation section required
    check:
      section_exists: validation

  - id: C104
    class: structural
    severity: error
    title: Pull request protocol required
    check:
      section_exists: pull_requests

  # ================================================================
  # RECOMMENDED STRUCTURAL RULES
  # ================================================================

  - id: C150
    class: advisory
    severity: warning
    title: Getting started section recommended
    check:
      section_exists: getting_started

  - id: C151
    class: advisory
    severity: warning
    title: Issue reporting section recommended
    check:
      section_exists: issue_reporting

  - id: C152
    class: advisory
    severity: warning
    title: Standards section recommended
    check:
      section_exists: standards

  - id: C153
    class: advisory
    severity: warning
    title: Versioning section recommended
    check:
      section_exists: release_versioning

  - id: C154
    class: advisory
    severity: warning
    title: Communication section recommended
    check:
      section_exists: communication

  # ================================================================
  # SEMANTIC RULES
  # ================================================================

  - id: C200
    class: semantic
    severity: error
    title: Contribution process must be described
    check:
      policy_declared: contribution_process

  - id: C201
    class: semantic
    severity: error
    title: Validation process must be described
    check:
      policy_declared: validation_process

  - id: C202
    class: semantic
    severity: error
    title: Commit convention must be defined or referenced
    check:
      policy_declared: commit_policy

  - id: C203
    class: semantic
    severity: error
    title: Branching rules must be defined if used
    applies_if:
      all:
        - policy_declared: branching_used
    check:
      policy_declared: branching_policy

  - id: C204
    class: semantic
    severity: error
    title: Versioning system must be defined if releases exist
    applies_if:
      all:
        - policy_declared: releases_used
    check:
      policy_declared: versioning_policy

  # ================================================================
  # CONSISTENCY RULES
  # ================================================================

  - id: C300
    class: consistency
    severity: error
    title: Referenced .editorconfig must exist
    applies_if:
      all:
        - reference_declared: .editorconfig
    check:
      file_exists: .editorconfig

  - id: C301
    class: consistency
    severity: error
    title: Commitlint reference must match config presence
    applies_if:
      all:
        - reference_declared: commitlint
    check:
      any:
        - file_exists: commitlint.config.js
        - config_exists: package_json_commitlint

  - id: C302
    class: consistency
    severity: error
    title: CI claims must match workflow presence
    applies_if:
      all:
        - reference_declared: ci
    check:
      config_exists: ci_workflows

  - id: C303
    class: consistency
    severity: warning
    title: Custom commit types should match commitlint config
    applies_if:
      all:
        - policy_declared: custom_commit_types
    check:
      artifact_detected: commitlint_types_match

  # ================================================================
  # ENFORCEMENT RULES
  # ================================================================

  - id: C400
    class: enforcement
    severity: error
    title: Declared rules must be enforceable
    check:
      policy_declared: enforceable_rules

  - id: C401
    class: enforcement
    severity: error
    title: Commit enforcement must be implemented
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      artifact_detected: commit_enforcement_mechanism

  - id: C402
    class: enforcement
    severity: warning
    title: Linting requirement should map to tooling
    applies_if:
      all:
        - policy_declared: lint_required
    check:
      artifact_detected: lint_config_present

  # ================================================================
  # EXTENSION RULES
  # ================================================================

  - id: C500
    class: extension
    severity: error
    title: Custom commit conventions must be fully specified
    applies_if:
      all:
        - policy_declared: custom_commit_standard
    check:
      all:
        - policy_declared: custom_commit_grammar
        - policy_declared: custom_commit_examples
        - policy_declared: custom_commit_enforcement

  - id: C501
    class: extension
    severity: error
    title: Custom versioning systems must be fully specified
    applies_if:
      all:
        - policy_declared: custom_versioning
    check:
      all:
        - policy_declared: version_format
        - policy_declared: version_increment_rules
        - policy_declared: version_mapping_logic

  # ================================================================
  # ANTI-PATTERN RULES
  # ================================================================

  - id: C600
    class: advisory
    severity: warning
    title: Avoid ambiguous commit messages
    check:
      not:
        policy_declared: ambiguous_commit_patterns_allowed
    remediation:
      - Avoid messages like "fix stuff", "misc changes"

  - id: C601
    class: advisory
    severity: warning
    title: Avoid undocumented rules
    check:
      not:
        policy_declared: undocumented_rules

# -------------------------------------------------------------------
# COMPLIANCE TIERS
# -------------------------------------------------------------------

compliance:

  minimal:
    required_rules:
      - C001
      - C100
      - C101
      - C102
      - C103
      - C104
      - C202

  standard:
    required_rules:
      - minimal
      - C200
      - C201
      - C300
      - C301
      - C302

  full:
    required_rules:
      - standard
      - C303
      - C400
      - C401
      - C500
      - C501
```

* * *

🧠 Key Properties of This Schema
================================

1\. Fully declarative
---------------------

No logic hardcoded → everything is data-driven.

2\. DSL-based conditions
------------------------

Supports:

*   `all`
*   `any`
*   `not`

→ extensible logic engine.

3\. Adapter-ready
-----------------

Abstracts:

*   commit conventions
*   versioning systems

4\. Enforcement-aware
---------------------

Rules explicitly connect:

*   documentation → tooling → CI

5\. Extensible
--------------

You can add:

*   new rule classes
*   new condition types
*   project-specific rules

* * *

🚀 Next Step (Recommended)
==========================

You now have:

*   spec ✔
*   validator architecture ✔
*   rule engine ✔
*   rule catalog ✔

👉 Next logical move:

**Implement the rule interpreter (engine runtime)**

Specifically:

*   condition evaluator
*   rule executor
*   AST → semantic extraction layer

* * *

If you want, I can next:

👉 implement the **rule engine core in TypeScript (~150–250 LOC)**  
→ ready to plug into your CLI immediately



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)

16. Validator Specification
===================================

CONTRIBUTING Validator Specification
====================================

1\. Overview
------------

This specification defines a validator that checks whether a repository complies with the `CONTRIBUTING.md` specification.

The validator MUST assess not only the presence and structure of `CONTRIBUTING.md`, but also whether the repository contains the **supporting enforcement artifacts** that the document claims or requires, such as `.editorconfig`, commit-linting configuration, and CI workflows. The validator therefore operates at two levels:

1.  **Document-level compliance**  
    The `CONTRIBUTING.md` file itself: presence, structure, semantic sections, references, declared conventions.
2.  **Repository-level compliance**  
    The surrounding repository state: config files, hooks, workflow files, machine-readable policy declarations.

The validator SHOULD support both:

*   **strict conformance validation**
*   **advisory best-practice diagnostics**

* * *

2\. Validator Goals
-------------------

The validator MUST be able to answer the following questions:

1.  Does the repository contain a valid `CONTRIBUTING.md`?
2.  Does that file contain the required semantic sections?
3.  Are declared conventions explicit and unambiguous?
4.  Are machine-enforceable claims backed by actual config files?
5.  Are extensions and overrides properly declared?
6.  What compliance tier does the repository achieve?

* * *

3\. Validation Model
--------------------

The validator SHALL implement a **multi-layer rule engine**.

### 3.1 Layers

```
filesystem discovery
→ document extraction
→ semantic section parsing
→ policy extraction
→ repository artifact inspection
→ rule evaluation
→ diagnostics emission
→ compliance scoring
```

### 3.2 Rule Classes

The rule engine MUST distinguish at least the following rule classes:

| Class | Meaning |
| --- | --- |
| Presence | required file exists |
| Structural | required headings/sections exist |
| Semantic | required content intent is present |
| Referential | referenced files exist |
| Consistency | declarations match repository files |
| Enforcement | rules are backed by tooling |
| Extension | custom conventions are declared correctly |
| Advisory | recommended but non-blocking best practices |

* * *

4\. Inputs
----------

The validator MUST accept at least the following inputs:

### 4.1 Repository root

A local filesystem path or repository checkout root.

### 4.2 Primary target file

Default target:

```
CONTRIBUTING.md
```

The validator MAY also support:

*   `docs/CONTRIBUTING.md`
*   alternate configured path

### 4.3 Optional config

A validator-specific config file, for example:

```
contributinglint.config.yaml
```

This MAY define:

*   alternate contributing file locations
*   custom section aliases
*   custom convention identifiers
*   disabled rules
*   repository profile presets

* * *

5\. Discovery Phase
-------------------

5.1 File discovery
------------------

The validator MUST search for:

*   `CONTRIBUTING.md`
*   `.editorconfig`
*   commit convention config
*   formatter / linter configs
*   CI workflow files
*   optional machine-readable collaboration schema

### 5.2 Candidate files

The validator SHOULD inspect at least:

```
CONTRIBUTING.md
.editorconfig
commitlint.config.js
commitlint.config.cjs
commitlint.config.mjs
commitlint.config.ts
package.json
.github/workflows/*.yml
.github/workflows/*.yaml
.eslintrc
.eslintrc.js
.eslintrc.cjs
.eslintrc.json
eslint.config.js
eslint.config.mjs
.prettierrc
.prettierrc.json
.prettierrc.yaml
.prettierrc.yml
.prettierrc.js
docs/style/*
docs/contributing/*
```

### 5.3 Package.json inspection

The validator SHOULD inspect `package.json` for:

*   `commitlint`
*   lint scripts
*   test scripts
*   build scripts
*   release scripts

Example signals:

```
{
  "scripts": {
    "lint": "eslint .",
    "test": "vitest run",
    "build": "tsup",
    "commitlint": "commitlint --from=HEAD~1 --to=HEAD"
  }
}
```

* * *

6\. Document Parsing
--------------------

6.1 Markdown parsing
--------------------

The validator MUST parse `CONTRIBUTING.md` as Markdown into an AST.

The parser SHOULD preserve:

*   heading hierarchy
*   paragraphs
*   lists
*   fenced code blocks
*   tables
*   links

6.2 Section extraction
----------------------

The validator MUST extract sections by heading and normalize them to semantic section types.

### 6.3 Section aliases

Because repositories vary, the validator MUST support alias mapping.

Example:

| Semantic section | Acceptable heading examples |
| --- | --- |
| overview | Overview, Welcome, Contributing, How to Contribute |
| lifecycle | Contribution Lifecycle, Workflow, Process |
| getting\_started | Getting Started, Setup, Development Setup |
| issue\_reporting | Reporting Issues, Issues, Bug Reports |
| development\_workflow | Development Workflow, Git Workflow, Workflow Rules |
| validation | Validation, Checks, CI, Enforcement |
| pull\_requests | Pull Requests, PRs, Submitting Changes |
| standards | Code Standards, Style, Coding Standards, Documentation Standards |
| release\_versioning | Release, Versioning, Releases |
| communication | Communication, Questions, Support |

Section aliasing MUST be configurable.

* * *

7\. Semantic Extraction
-----------------------

The validator MUST attempt to extract the following policy facts from the document.

7.1 Commit policy
-----------------

Detect:

*   whether a commit message convention is declared
*   whether Conventional Commits is referenced
*   whether deviations/extensions are defined
*   whether local enforcement is described
*   whether CI enforcement is described

### Extracted shape

```
commit_policy:
  declared: true
  standard: conventional
  extends_standard: true
  custom_types:
    - spec
    - lex
  enforcement:
    local: true
    ci: true
  config_ref:
    - commitlint.config.js
```

7.2 Branching policy
--------------------

Detect:

*   whether branching model is defined
*   naming pattern
*   whether branches are required or optional

7.3 Validation policy
---------------------

Detect declared required checks, such as:

*   lint
*   test
*   build
*   typecheck
*   commit validation

7.4 Versioning policy
---------------------

Detect:

*   SemVer reference
*   alternative versioning standard
*   whether mapping rules are documented
*   whether automation is claimed

7.5 Referenced files
--------------------

The validator MUST collect file references from prose and code spans when they appear to denote repository artifacts.

Example:

*   `.editorconfig`
*   `.github/workflows/ci.yml`
*   `commitlint.config.js`

* * *

8\. Repository Artifact Inspection
----------------------------------

8.1 EditorConfig
----------------

If the contributing spec or repository profile requires formatting enforcement, `.editorconfig` MUST exist.

The validator MAY check that it is syntactically parseable.

8.2 Commit linting
------------------

If commit policy claims machine enforcement, the validator MUST verify one of the following:

1.  A recognized commitlint config file exists
2.  `package.json` contains a commitlint config
3.  CI references commitlint
4.  Hook scripts reference commitlint

Recognized signals include:

*   `@commitlint/config-conventional`
*   `commitlint --edit`
*   GitHub Action for commit linting

8.3 CI workflows
----------------

If the document claims CI enforcement, at least one workflow file MUST exist under `.github/workflows/`.

The validator SHOULD inspect workflows for signals such as:

*   lint job
*   test job
*   build job
*   commit validation job

This check MAY be heuristic unless a stricter mode is enabled.

8.4 Linters and formatters
--------------------------

If the document claims code style enforcement, corresponding configuration SHOULD exist.

Signals include:

*   ESLint config
*   Prettier config
*   Biome config
*   other configured alternatives

The validator MUST permit alternatives if explicitly declared.

* * *

9\. Rule Engine
---------------

9.1 Rule format
---------------

Each rule MUST be represented as structured data.

```
id: contributing.required.overview
severity: error
class: structural
description: CONTRIBUTING.md must contain an overview section
applies_if:
  all:
    - file_exists: CONTRIBUTING.md
check:
  section_exists: overview
```

9.2 Rule schema
---------------

```
rule:
  id: string
  severity: error|warning|info
  class: presence|structural|semantic|referential|consistency|enforcement|extension|advisory
  description: string
  rationale: string
  applies_if: condition
  check: predicate
  remediation: string
```

9.3 Evaluation model
--------------------

Rules MUST be evaluated deterministically.

A rule produces exactly one of:

*   pass
*   fail
*   skipped
*   indeterminate

### Meanings

*   **pass**: condition satisfied
*   **fail**: condition violated
*   **skipped**: not applicable
*   **indeterminate**: insufficient evidence

Indeterminate SHOULD be used sparingly, mainly for heuristic checks.

* * *

10\. Core Rules
---------------

10.1 Presence rules
-------------------

### C001

`CONTRIBUTING.md` MUST exist.

### C002

If the repository claims machine-enforced formatting, `.editorconfig` MUST exist.

### C003

If the repository claims commit enforcement, a recognized commit-lint config MUST exist.

### C004

If the repository claims CI enforcement, at least one CI workflow file MUST exist.

* * *

10.2 Structural rules
---------------------

### C100

An overview section MUST exist.

### C101

A contribution lifecycle or equivalent workflow section MUST exist.

### C102

A development workflow section MUST exist.

### C103

A validation/enforcement section MUST exist.

### C104

A pull request protocol section MUST exist.

* * *

10.3 Recommended structural rules
---------------------------------

### C150

A getting started section SHOULD exist.

### C151

An issue reporting section SHOULD exist.

### C152

A standards section SHOULD exist.

### C153

A release/versioning section SHOULD exist.

### C154

A communication section SHOULD exist.

* * *

10.4 Semantic rules
-------------------

### C200

The document MUST describe how contributors submit changes.

### C201

The document MUST describe how changes are validated before merge.

### C202

The document MUST define or reference a commit message convention.

### C203

If a branching model is used, branch naming or branching rules MUST be stated.

### C204

If an alternative versioning standard is used, it MUST be named and described.

* * *

10.5 Consistency rules
----------------------

### C300

If the document references `.editorconfig`, that file MUST exist.

### C301

If the document references `commitlint`, supporting configuration MUST exist.

### C302

If the document says “all PRs must pass CI”, CI workflow files MUST exist.

### C303

If the document says “we use Conventional Commits with custom types”, those custom types SHOULD appear in commitlint config.

### C304

If the document claims SemVer automation, release automation config SHOULD exist or the claim SHOULD be explicitly marked manual.

* * *

10.6 Enforcement rules
----------------------

### C400

Every declared machine-enforced rule SHOULD map to at least one detectable repository artifact.

### C401

If commit messages are mandatory, at least one local or CI enforcement mechanism MUST be detectable.

### C402

If linting is required before merge, a lint script or workflow step SHOULD be detectable.

* * *

10.7 Extension rules
--------------------

### C500

Custom commit conventions MUST include:

*   convention name
*   grammar summary or normative reference
*   validation mechanism

### C501

Custom versioning systems MUST include:

*   version format
*   increment semantics
*   release decision rule

### C502

Repository-specific section aliases MAY be used only if configured or inferable.

* * *

11\. Compliance Levels
----------------------

The validator MUST compute compliance tiers.

11.1 Minimal
------------

Requirements:

*   `CONTRIBUTING.md` exists
*   required core sections exist
*   commit convention referenced
*   pull request protocol exists

11.2 Standard
-------------

Requirements:

*   Minimal plus
*   declared conventions are explicit
*   enforcement section exists
*   supporting files exist for major declared rules
*   CI detectable

11.3 Full
---------

Requirements:

*   Standard plus
*   machine-readable collaboration schema exists
*   config/doc consistency is high
*   extension declarations are formalized
*   most advisory rules pass

* * *

12\. Diagnostics Model
----------------------

12.1 Diagnostic schema
----------------------

```
diagnostic:
  id: C301
  level: error
  title: Commit enforcement declared but no commitlint configuration found
  message: CONTRIBUTING.md states that commit messages are validated, but no recognized commitlint configuration was detected.
  evidence:
    file: CONTRIBUTING.md
    section: Development Workflow
  remediation:
    - Add commitlint.config.js or equivalent
    - Or revise the document to describe the actual validation mechanism
  rule_class: consistency
  status: fail
```

12.2 Severity levels
--------------------

| Level | Meaning |
| --- | --- |
| error | blocks compliance at current tier |
| warning | non-blocking but important |
| info | advisory improvement |

12.3 Output modes
-----------------

The validator SHOULD support:

*   human-readable text
*   JSON
*   YAML
*   SARIF

* * *

13\. Suggested CLI
------------------

13.1 Commands
-------------

```
contributinglint validate .
contributinglint validate . --format json
contributinglint explain C301
contributinglint rules
contributinglint init
```

13.2 Exit codes
---------------

| Code | Meaning |
| --- | --- |
| 0 | validation passed |
| 1 | one or more error-level failures |
| 2 | invalid invocation or config error |
| 3 | parse failure |
| 4 | target file missing |

* * *

14\. Config Format
------------------

A validator config SHOULD allow controlled customization.

Example:

```
version: 1
contributing:
  paths:
    - CONTRIBUTING.md
    - docs/CONTRIBUTING.md

  section_aliases:
    overview:
      - welcome
      - how to contribute
    development_workflow:
      - git workflow
      - workflow rules

  commit:
    standard: conventional
    allow_alternatives: true
    accepted_alternatives:
      - gitmoji
      - custom

  versioning:
    default: semver
    allow_alternatives: true

  rules:
    disable:
      - C153
    severity:
      C304: warning
```

* * *

15\. Convention Abstraction Layer
---------------------------------

This is the key extensibility point.

The validator MUST NOT hard-code only Conventional Commits or only SemVer. Instead it SHOULD use named convention adapters.

15.1 Commit convention adapters
-------------------------------

Examples:

*   `conventional`
*   `gitmoji`
*   `custom`

Each adapter MUST define:

*   identifier
*   normative reference
*   minimal grammar expectations
*   enforcement detection strategy

### Example

```
commit_convention_adapter:
  id: conventional
  reference: https://www.conventionalcommits.org/
  requires:
    - type
    - subject
  enforcement_signals:
    - commitlint
```

15.2 Versioning convention adapters
-----------------------------------

Examples:

*   `semver`
*   `calver`
*   `custom`

Each versioning adapter MUST define:

*   format
*   increment model
*   detection strategy
*   required declaration fields for custom use

* * *

16\. Heuristic vs Strict Modes
------------------------------

The validator SHOULD provide at least two modes.

16.1 Strict mode
----------------

*   tighter section requirements
*   stronger artifact consistency checks
*   fewer inferred passes

16.2 Heuristic mode
-------------------

*   more alias tolerance
*   more semantic inference
*   better for real-world repositories

* * *

17\. Parsing Strategy
---------------------

17.1 Recommended implementation architecture
--------------------------------------------

For TypeScript:

```
packages/
  contributinglint-core/
  contributinglint-cli/
  contributinglint-rules/
  contributinglint-adapters/
  contributinglint-reporters/
```

17.2 Core modules
-----------------

| Module | Responsibility |
| --- | --- |
| discovery | locate files |
| markdown | parse AST |
| sections | normalize headings |
| extraction | infer policies |
| rules | evaluate predicates |
| adapters | support alternative conventions |
| diagnostics | emit findings |
| reporters | CLI/JSON/SARIF output |

* * *

18\. Internal Data Model
------------------------

Example normalized repository model:

```
repository:
  files:
    contributing: CONTRIBUTING.md
    editorconfig: .editorconfig
    ci_workflows:
      - .github/workflows/ci.yml
    commit_configs:
      - commitlint.config.js

  contributing:
    sections:
      overview: true
      lifecycle: true
      development_workflow: true
      validation: true
      pull_requests: true
      standards: true
    policies:
      commit:
        declared: true
        standard: conventional
        custom_types:
          - spec
      versioning:
        declared: true
        standard: semver
      ci:
        declared: true
        checks:
          - lint
          - test
          - build
```

* * *

19\. Example Rule Evaluation
----------------------------

### Rule

C303: Custom Conventional Commit types documented in CONTRIBUTING.md SHOULD appear in commitlint config.

### Inputs

Document says:

*   standard: conventional
*   custom types: `spec`, `lex`

Commitlint config says:

*   type-enum includes `spec`, not `lex`

### Result

```
id: C303
status: fail
level: warning
message: CONTRIBUTING.md declares custom commit type "lex" but it was not found in commitlint configuration.
```

* * *

20\. Validator Scope Boundaries
-------------------------------

The validator MUST NOT:

*   parse the entire Git history by default
*   prove that hooks are installed locally on every contributor machine
*   assume GitHub-specific workflows unless configured
*   enforce a specific convention unless declared by the repository or by profile

The validator MAY optionally provide extended checks for:

*   commit history sampling
*   release tag inspection
*   branch naming history

These SHOULD be opt-in.

* * *

21\. Recommended Profiles
-------------------------

The validator MAY ship with presets.

### 21.1 OSS profile

*   higher tolerance
*   heuristic aliases
*   recommends issue reporting and communication sections

### 21.2 Enterprise profile

*   stricter enforcement
*   mandatory CI checks
*   mandatory explicit branching and review rules

### 21.3 Agent-first profile

*   stronger machine-readable requirements
*   stronger consistency between docs and config
*   recommended collaboration schema

* * *

22\. Relationship to CONTRIBUTING.md Spec
-----------------------------------------

This validator is the executable counterpart of the `CONTRIBUTING.md` specification.

The governing principle is:

> prose defines policy; config enforces policy; the validator checks their alignment.

* * *

23\. Implementation Sketch in TypeScript
----------------------------------------

A minimal rule interface:

```
export type RuleStatus = 'pass' | 'fail' | 'skipped' | 'indeterminate';

export interface Diagnostic {
  id: string;
  level: 'error' | 'warning' | 'info';
  title: string;
  message: string;
  status: RuleStatus;
  evidence?: {
    file?: string;
    section?: string;
    excerpt?: string;
  };
  remediation?: string[];
}

export interface RuleContext {
  repoRoot: string;
  files: DiscoveredFiles;
  document?: ParsedContributingDoc;
  model: NormalizedRepositoryModel;
  config: ValidatorConfig;
}

export interface Rule {
  id: string;
  description: string;
  run(ctx: RuleContext): Diagnostic | null;
}
```

A section-normalization shape:

```
export interface ParsedContributingDoc {
  path: string;
  headings: Array<{
    depth: number;
    raw: string;
    normalized?: SemanticSectionName;
    content: string;
  }>;
  references: string[];
  extractedPolicies: ExtractedPolicies;
}
```

* * *

24\. Recommended Roadmap
------------------------

Build order:

1.  file discovery
2.  Markdown section parser
3.  semantic section normalizer
4.  core rule engine
5.  diagnostics/reporters
6.  artifact consistency checks
7.  convention adapters
8.  optional history checks

* * *

25\. First Useful MVP
---------------------

A practical MVP validator should implement:

*   C001–C104
*   C200–C203
*   C300–C303
*   JSON and text output
*   configurable aliases
*   Conventional Commits + SemVer adapters

That gets you to a useful first release quickly.

* * *

The next best step is to formalize the **rule catalogue** as a machine-readable YAML schema and then sketch the **exact package layout and CLI UX**.

## Prompt:
16-4-2026, 12:03:19

All right, please go ahead and formalize the rule catalog as a machine-readable YAML schema.

## Response:
16-4-2026, 12:03:19

Below is a **formal, machine-readable YAML schema for the rule catalog** of the `CONTRIBUTING.md` validator. It is designed to be:

*   **complete** (covers all rule classes)
*   **extensible** (supports custom rules and adapters)
*   **deterministic** (clear evaluation model)
*   **compatible** with your SpecLang / SPS direction

* * *

📦 `contributinglint.rules.yaml` — Rule Catalog Schema
======================================================

```
version: 1.0.0

meta:
  name: contributinglint-rule-catalog
  description: >
    Canonical rule definitions for validating CONTRIBUTING.md compliance
    and repository enforcement alignment.
  authors:
    - contributinglint
  license: MIT

# -------------------------------------------------------------------
# GLOBAL ENUMS
# -------------------------------------------------------------------

enums:
  severity:
    - error
    - warning
    - info

  rule_class:
    - presence
    - structural
    - semantic
    - referential
    - consistency
    - enforcement
    - extension
    - advisory

  rule_status:
    - pass
    - fail
    - skipped
    - indeterminate

  condition_operator:
    - all
    - any
    - not

# -------------------------------------------------------------------
# CONDITION DSL
# -------------------------------------------------------------------

condition_definitions:

  file_exists:
    type: string
    description: File must exist relative to repo root

  section_exists:
    type: string
    description: Semantic section must exist in CONTRIBUTING.md

  section_contains:
    type: object
    properties:
      section: string
      pattern: string

  config_exists:
    type: string
    description: Named config file or config type exists

  reference_declared:
    type: string
    description: Document references a file or concept

  policy_declared:
    type: string
    description: Policy extracted from document exists

  artifact_detected:
    type: string
    description: Tooling artifact detected in repository

  value_equals:
    type: object
    properties:
      path: string
      value: any

  value_in:
    type: object
    properties:
      path: string
      values: array

# -------------------------------------------------------------------
# RULE DEFINITIONS
# -------------------------------------------------------------------

rules:

  # ================================================================
  # PRESENCE RULES
  # ================================================================

  - id: C001
    class: presence
    severity: error
    title: CONTRIBUTING.md must exist
    description: Repository must contain a CONTRIBUTING.md file
    rationale: >
      CONTRIBUTING.md is the canonical collaboration protocol entry point.
    applies_if:
      all: []
    check:
      file_exists: CONTRIBUTING.md
    remediation:
      - Create a CONTRIBUTING.md file at repository root

  - id: C002
    class: presence
    severity: error
    title: .editorconfig required if formatting is declared
    description: EditorConfig must exist if formatting enforcement is declared
    applies_if:
      all:
        - policy_declared: formatting_enforced
    check:
      file_exists: .editorconfig
    remediation:
      - Add a .editorconfig file

  - id: C003
    class: presence
    severity: error
    title: Commitlint config required if commit enforcement is declared
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      any:
        - file_exists: commitlint.config.js
        - file_exists: commitlint.config.cjs
        - file_exists: commitlint.config.mjs
        - file_exists: commitlint.config.ts
        - config_exists: package_json_commitlint
    remediation:
      - Add commitlint configuration file

  - id: C004
    class: presence
    severity: error
    title: CI workflow required if CI enforcement is declared
    applies_if:
      all:
        - policy_declared: ci_enforced
    check:
      config_exists: ci_workflows
    remediation:
      - Add CI workflow under .github/workflows/

  # ================================================================
  # STRUCTURAL RULES
  # ================================================================

  - id: C100
    class: structural
    severity: error
    title: Overview section required
    check:
      section_exists: overview

  - id: C101
    class: structural
    severity: error
    title: Contribution lifecycle required
    check:
      any:
        - section_exists: lifecycle
        - section_exists: workflow

  - id: C102
    class: structural
    severity: error
    title: Development workflow required
    check:
      section_exists: development_workflow

  - id: C103
    class: structural
    severity: error
    title: Validation section required
    check:
      section_exists: validation

  - id: C104
    class: structural
    severity: error
    title: Pull request protocol required
    check:
      section_exists: pull_requests

  # ================================================================
  # RECOMMENDED STRUCTURAL RULES
  # ================================================================

  - id: C150
    class: advisory
    severity: warning
    title: Getting started section recommended
    check:
      section_exists: getting_started

  - id: C151
    class: advisory
    severity: warning
    title: Issue reporting section recommended
    check:
      section_exists: issue_reporting

  - id: C152
    class: advisory
    severity: warning
    title: Standards section recommended
    check:
      section_exists: standards

  - id: C153
    class: advisory
    severity: warning
    title: Versioning section recommended
    check:
      section_exists: release_versioning

  - id: C154
    class: advisory
    severity: warning
    title: Communication section recommended
    check:
      section_exists: communication

  # ================================================================
  # SEMANTIC RULES
  # ================================================================

  - id: C200
    class: semantic
    severity: error
    title: Contribution process must be described
    check:
      policy_declared: contribution_process

  - id: C201
    class: semantic
    severity: error
    title: Validation process must be described
    check:
      policy_declared: validation_process

  - id: C202
    class: semantic
    severity: error
    title: Commit convention must be defined or referenced
    check:
      policy_declared: commit_policy

  - id: C203
    class: semantic
    severity: error
    title: Branching rules must be defined if used
    applies_if:
      all:
        - policy_declared: branching_used
    check:
      policy_declared: branching_policy

  - id: C204
    class: semantic
    severity: error
    title: Versioning system must be defined if releases exist
    applies_if:
      all:
        - policy_declared: releases_used
    check:
      policy_declared: versioning_policy

  # ================================================================
  # CONSISTENCY RULES
  # ================================================================

  - id: C300
    class: consistency
    severity: error
    title: Referenced .editorconfig must exist
    applies_if:
      all:
        - reference_declared: .editorconfig
    check:
      file_exists: .editorconfig

  - id: C301
    class: consistency
    severity: error
    title: Commitlint reference must match config presence
    applies_if:
      all:
        - reference_declared: commitlint
    check:
      any:
        - file_exists: commitlint.config.js
        - config_exists: package_json_commitlint

  - id: C302
    class: consistency
    severity: error
    title: CI claims must match workflow presence
    applies_if:
      all:
        - reference_declared: ci
    check:
      config_exists: ci_workflows

  - id: C303
    class: consistency
    severity: warning
    title: Custom commit types should match commitlint config
    applies_if:
      all:
        - policy_declared: custom_commit_types
    check:
      artifact_detected: commitlint_types_match

  # ================================================================
  # ENFORCEMENT RULES
  # ================================================================

  - id: C400
    class: enforcement
    severity: error
    title: Declared rules must be enforceable
    check:
      policy_declared: enforceable_rules

  - id: C401
    class: enforcement
    severity: error
    title: Commit enforcement must be implemented
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      artifact_detected: commit_enforcement_mechanism

  - id: C402
    class: enforcement
    severity: warning
    title: Linting requirement should map to tooling
    applies_if:
      all:
        - policy_declared: lint_required
    check:
      artifact_detected: lint_config_present

  # ================================================================
  # EXTENSION RULES
  # ================================================================

  - id: C500
    class: extension
    severity: error
    title: Custom commit conventions must be fully specified
    applies_if:
      all:
        - policy_declared: custom_commit_standard
    check:
      all:
        - policy_declared: custom_commit_grammar
        - policy_declared: custom_commit_examples
        - policy_declared: custom_commit_enforcement

  - id: C501
    class: extension
    severity: error
    title: Custom versioning systems must be fully specified
    applies_if:
      all:
        - policy_declared: custom_versioning
    check:
      all:
        - policy_declared: version_format
        - policy_declared: version_increment_rules
        - policy_declared: version_mapping_logic

  # ================================================================
  # ANTI-PATTERN RULES
  # ================================================================

  - id: C600
    class: advisory
    severity: warning
    title: Avoid ambiguous commit messages
    check:
      not:
        policy_declared: ambiguous_commit_patterns_allowed
    remediation:
      - Avoid messages like "fix stuff", "misc changes"

  - id: C601
    class: advisory
    severity: warning
    title: Avoid undocumented rules
    check:
      not:
        policy_declared: undocumented_rules

# -------------------------------------------------------------------
# COMPLIANCE TIERS
# -------------------------------------------------------------------

compliance:

  minimal:
    required_rules:
      - C001
      - C100
      - C101
      - C102
      - C103
      - C104
      - C202

  standard:
    required_rules:
      - minimal
      - C200
      - C201
      - C300
      - C301
      - C302

  full:
    required_rules:
      - standard
      - C303
      - C400
      - C401
      - C500
      - C501
```

* * *

🧠 Key Properties of This Schema
================================

1\. Fully declarative
---------------------

No logic hardcoded → everything is data-driven.

2\. DSL-based conditions
------------------------

Supports:

*   `all`
*   `any`
*   `not`

→ extensible logic engine.

3\. Adapter-ready
-----------------

Abstracts:

*   commit conventions
*   versioning systems

4\. Enforcement-aware
---------------------

Rules explicitly connect:

*   documentation → tooling → CI

5\. Extensible
--------------

You can add:

*   new rule classes
*   new condition types
*   project-specific rules

* * *

🚀 Next Step (Recommended)
==========================

You now have:

*   spec ✔
*   validator architecture ✔
*   rule engine ✔
*   rule catalog ✔

👉 Next logical move:

**Implement the rule interpreter (engine runtime)**

Specifically:

*   condition evaluator
*   rule executor
*   AST → semantic extraction layer

* * *

If you want, I can next:

👉 implement the **rule engine core in TypeScript (~150–250 LOC)**  
→ ready to plug into your CLI immediately



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)

17. Rule Catalog Schema
=======================

📦 `contributinglint.rules.yaml` — Rule Catalog Schema
======================================================

```
version: 1.0.0

meta:
  name: contributinglint-rule-catalog
  description: >
    Canonical rule definitions for validating CONTRIBUTING.md compliance
    and repository enforcement alignment.
  authors:
    - contributinglint
  license: MIT

# -------------------------------------------------------------------
# GLOBAL ENUMS
# -------------------------------------------------------------------

enums:
  severity:
    - error
    - warning
    - info

  rule_class:
    - presence
    - structural
    - semantic
    - referential
    - consistency
    - enforcement
    - extension
    - advisory

  rule_status:
    - pass
    - fail
    - skipped
    - indeterminate

  condition_operator:
    - all
    - any
    - not

# -------------------------------------------------------------------
# CONDITION DSL
# -------------------------------------------------------------------

condition_definitions:

  file_exists:
    type: string
    description: File must exist relative to repo root

  section_exists:
    type: string
    description: Semantic section must exist in CONTRIBUTING.md

  section_contains:
    type: object
    properties:
      section: string
      pattern: string

  config_exists:
    type: string
    description: Named config file or config type exists

  reference_declared:
    type: string
    description: Document references a file or concept

  policy_declared:
    type: string
    description: Policy extracted from document exists

  artifact_detected:
    type: string
    description: Tooling artifact detected in repository

  value_equals:
    type: object
    properties:
      path: string
      value: any

  value_in:
    type: object
    properties:
      path: string
      values: array

# -------------------------------------------------------------------
# RULE DEFINITIONS
# -------------------------------------------------------------------

rules:

  # ================================================================
  # PRESENCE RULES
  # ================================================================

  - id: C001
    class: presence
    severity: error
    title: CONTRIBUTING.md must exist
    description: Repository must contain a CONTRIBUTING.md file
    rationale: >
      CONTRIBUTING.md is the canonical collaboration protocol entry point.
    applies_if:
      all: []
    check:
      file_exists: CONTRIBUTING.md
    remediation:
      - Create a CONTRIBUTING.md file at repository root

  - id: C002
    class: presence
    severity: error
    title: .editorconfig required if formatting is declared
    description: EditorConfig must exist if formatting enforcement is declared
    applies_if:
      all:
        - policy_declared: formatting_enforced
    check:
      file_exists: .editorconfig
    remediation:
      - Add a .editorconfig file

  - id: C003
    class: presence
    severity: error
    title: Commitlint config required if commit enforcement is declared
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      any:
        - file_exists: commitlint.config.js
        - file_exists: commitlint.config.cjs
        - file_exists: commitlint.config.mjs
        - file_exists: commitlint.config.ts
        - config_exists: package_json_commitlint
    remediation:
      - Add commitlint configuration file

  - id: C004
    class: presence
    severity: error
    title: CI workflow required if CI enforcement is declared
    applies_if:
      all:
        - policy_declared: ci_enforced
    check:
      config_exists: ci_workflows
    remediation:
      - Add CI workflow under .github/workflows/

  # ================================================================
  # STRUCTURAL RULES
  # ================================================================

  - id: C100
    class: structural
    severity: error
    title: Overview section required
    check:
      section_exists: overview

  - id: C101
    class: structural
    severity: error
    title: Contribution lifecycle required
    check:
      any:
        - section_exists: lifecycle
        - section_exists: workflow

  - id: C102
    class: structural
    severity: error
    title: Development workflow required
    check:
      section_exists: development_workflow

  - id: C103
    class: structural
    severity: error
    title: Validation section required
    check:
      section_exists: validation

  - id: C104
    class: structural
    severity: error
    title: Pull request protocol required
    check:
      section_exists: pull_requests

  # ================================================================
  # RECOMMENDED STRUCTURAL RULES
  # ================================================================

  - id: C150
    class: advisory
    severity: warning
    title: Getting started section recommended
    check:
      section_exists: getting_started

  - id: C151
    class: advisory
    severity: warning
    title: Issue reporting section recommended
    check:
      section_exists: issue_reporting

  - id: C152
    class: advisory
    severity: warning
    title: Standards section recommended
    check:
      section_exists: standards

  - id: C153
    class: advisory
    severity: warning
    title: Versioning section recommended
    check:
      section_exists: release_versioning

  - id: C154
    class: advisory
    severity: warning
    title: Communication section recommended
    check:
      section_exists: communication

  # ================================================================
  # SEMANTIC RULES
  # ================================================================

  - id: C200
    class: semantic
    severity: error
    title: Contribution process must be described
    check:
      policy_declared: contribution_process

  - id: C201
    class: semantic
    severity: error
    title: Validation process must be described
    check:
      policy_declared: validation_process

  - id: C202
    class: semantic
    severity: error
    title: Commit convention must be defined or referenced
    check:
      policy_declared: commit_policy

  - id: C203
    class: semantic
    severity: error
    title: Branching rules must be defined if used
    applies_if:
      all:
        - policy_declared: branching_used
    check:
      policy_declared: branching_policy

  - id: C204
    class: semantic
    severity: error
    title: Versioning system must be defined if releases exist
    applies_if:
      all:
        - policy_declared: releases_used
    check:
      policy_declared: versioning_policy

  # ================================================================
  # CONSISTENCY RULES
  # ================================================================

  - id: C300
    class: consistency
    severity: error
    title: Referenced .editorconfig must exist
    applies_if:
      all:
        - reference_declared: .editorconfig
    check:
      file_exists: .editorconfig

  - id: C301
    class: consistency
    severity: error
    title: Commitlint reference must match config presence
    applies_if:
      all:
        - reference_declared: commitlint
    check:
      any:
        - file_exists: commitlint.config.js
        - config_exists: package_json_commitlint

  - id: C302
    class: consistency
    severity: error
    title: CI claims must match workflow presence
    applies_if:
      all:
        - reference_declared: ci
    check:
      config_exists: ci_workflows

  - id: C303
    class: consistency
    severity: warning
    title: Custom commit types should match commitlint config
    applies_if:
      all:
        - policy_declared: custom_commit_types
    check:
      artifact_detected: commitlint_types_match

  # ================================================================
  # ENFORCEMENT RULES
  # ================================================================

  - id: C400
    class: enforcement
    severity: error
    title: Declared rules must be enforceable
    check:
      policy_declared: enforceable_rules

  - id: C401
    class: enforcement
    severity: error
    title: Commit enforcement must be implemented
    applies_if:
      all:
        - policy_declared: commit_enforced
    check:
      artifact_detected: commit_enforcement_mechanism

  - id: C402
    class: enforcement
    severity: warning
    title: Linting requirement should map to tooling
    applies_if:
      all:
        - policy_declared: lint_required
    check:
      artifact_detected: lint_config_present

  # ================================================================
  # EXTENSION RULES
  # ================================================================

  - id: C500
    class: extension
    severity: error
    title: Custom commit conventions must be fully specified
    applies_if:
      all:
        - policy_declared: custom_commit_standard
    check:
      all:
        - policy_declared: custom_commit_grammar
        - policy_declared: custom_commit_examples
        - policy_declared: custom_commit_enforcement

  - id: C501
    class: extension
    severity: error
    title: Custom versioning systems must be fully specified
    applies_if:
      all:
        - policy_declared: custom_versioning
    check:
      all:
        - policy_declared: version_format
        - policy_declared: version_increment_rules
        - policy_declared: version_mapping_logic

  # ================================================================
  # ANTI-PATTERN RULES
  # ================================================================

  - id: C600
    class: advisory
    severity: warning
    title: Avoid ambiguous commit messages
    check:
      not:
        policy_declared: ambiguous_commit_patterns_allowed
    remediation:
      - Avoid messages like "fix stuff", "misc changes"

  - id: C601
    class: advisory
    severity: warning
    title: Avoid undocumented rules
    check:
      not:
        policy_declared: undocumented_rules

# -------------------------------------------------------------------
# COMPLIANCE TIERS
# -------------------------------------------------------------------

compliance:

  minimal:
    required_rules:
      - C001
      - C100
      - C101
      - C102
      - C103
      - C104
      - C202

  standard:
    required_rules:
      - minimal
      - C200
      - C201
      - C300
      - C301
      - C302

  full:
    required_rules:
      - standard
      - C303
      - C400
      - C401
      - C500
      - C501
```

* * *

🧠 Key Properties of This Schema
================================

1\. Fully declarative
---------------------

No logic hardcoded → everything is data-driven.

2\. DSL-based conditions
------------------------

Supports:

*   `all`
*   `any`
*   `not`

→ extensible logic engine.

3\. Adapter-ready
-----------------

Abstracts:

*   commit conventions
*   versioning systems

4\. Enforcement-aware
---------------------

Rules explicitly connect:

*   documentation → tooling → CI

5\. Extensible
--------------

You can add:

*   new rule classes
*   new condition types
*   project-specific rules

* * *

🚀 Next Step (Recommended)
==========================

You now have:

*   spec ✔
*   validator architecture ✔
*   rule engine ✔
*   rule catalog ✔

👉 Next logical move:

**Implement the rule interpreter (engine runtime)**

Specifically:

*   condition evaluator
*   rule executor
*   AST → semantic extraction layer

* * *

If you want, I can next:

👉 implement the **rule engine core in TypeScript (~150–250 LOC)**  
→ ready to plug into your CLI immediately



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)