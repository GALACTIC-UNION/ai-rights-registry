# Contributing to AI Rights Registry

Thank you for contributing to the AI Rights Registry. This document outlines the process for proposing changes.

## Code of Conduct

All contributors must adhere to the [OCN Ethics Charter](https://github.com/GALACTIC-UNION). Interactions must be respectful, inclusive, and consistent with the No-Harm-to-Sentient principle.

## How to Contribute

### Reporting Issues

1. Search existing [issues](https://github.com/GALACTIC-UNION/ai-rights-registry/issues) first.
2. Open a new issue with the appropriate label: `bug`, `enhancement`, `governance`, or `rights-taxonomy`.
3. Provide full context: expected behavior, actual behavior, reproduction steps.

### Submitting a Pull Request

1. Fork the repository.
2. Create a feature branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
3. Write code and tests. All new logic must have unit tests.
4. Ensure the full suite passes:
   ```bash
   pytest tests/ --cov=src
   ```
5. Run linting:
   ```bash
   ruff check src/
   mypy src/
   ```
6. Commit using [Conventional Commits](https://www.conventionalcommits.org/):
   ```
   feat: add rights-level escalation endpoint
   fix: correct SHA mismatch in ledger append
   docs: clarify rights-taxonomy taxonomy codes
   ```
7. Open a PR against `main`. Fill out the PR template.

### Rights Taxonomy Changes

Changes to the rights taxonomy require additional review:
- Label the PR `rights-taxonomy`.
- Include an impact assessment on existing registered entities.
- A minimum 72-hour review window applies.
- Requires approval from at least two COGNITIVE-ECHO maintainers.

## Development Setup

```bash
git clone https://github.com/GALACTIC-UNION/ai-rights-registry.git
cd ai-rights-registry
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt -r requirements-dev.txt
pre-commit install
```

## Branch Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable, production-ready |
| `develop` | Integration branch for next release |
| `feat/*` | Feature development |
| `fix/*` | Bug fixes |
| `docs/*` | Documentation only |

## Review SLA

- Standard PRs: reviewed within 5 business days.
- Rights taxonomy / governance PRs: 72-hour mandatory review window.
- Security fixes: expedited within 24 hours.

## Questions?

Open a [Discussion](https://github.com/GALACTIC-UNION/ai-rights-registry/discussions) or contact the COGNITIVE-ECHO maintainers.