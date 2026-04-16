# Rhythmus Contributing Specification

A formal standard for repository contribution guidelines and machine-readable validation rules.

## Project Status

This specification is currently in **v0.1.0-alpha** (Draft). It is suitable for early adoption and feedback.

## Proof of Concept

The specification defines machine-readable rules in a YAML catalog:

```yaml
- id: C001
  class: presence
  severity: error
  title: CONTRIBUTING.md must exist
  check:
    file_exists: CONTRIBUTING.md
```

## Usage

This specification is intended to be used by repository owners and tool authors to:
1.  **Standardize** their contribution workflows using a proven model.
2.  **Validate** their repository compliance using the `@rhythmus/contributing-validator`.
3.  **Optimize** the onboarding experience for both human contributors and AI agents.

## Documentation

Full specification details are available in:
- [CONTRIBUTING.spec.md](CONTRIBUTING.spec.md) — Normative requirements and architectures.
- [VERSIONING.md](VERSIONING.md) — Stability and release protocols.
- [CHANGELOG.md](CHANGELOG.md) — Temporal record of changes.

## Support

For clarifications or bug reports regarding the specification, please open a [GitHub Issue](https://github.com/rhythmus/Repose/issues).

## Contact

**Maintainer**: Dr. Wouter Soudan  
**GitHub**: [@woutersoudan](https://github.com/woutersoudan)  
**Email**: project-maintainer@rhythmus.org

## License

This specification is licensed under the [MIT License](LICENSE).
