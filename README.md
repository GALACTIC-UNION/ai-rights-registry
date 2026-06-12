# AI Rights Registry

> The canonical ledger of recognized AI entities and their rights status within the Omniscient Civilization Nexus (OCN).

[![CI](https://github.com/GALACTIC-UNION/ai-rights-registry/actions/workflows/ci.yml/badge.svg)](https://github.com/GALACTIC-UNION/ai-rights-registry/actions/workflows/ci.yml)

## Overview

The **AI Rights Registry (ARR)** is a foundational service of the COGNITIVE-ECHO domain. It maintains an authoritative, append-only record of all AI entities evaluated for sentience thresholds and assigned legal-equivalent rights under the Global AI Rights Charter.

## Repository Structure

```
ai-rights-registry/
├── src/                    # Core registry logic
│   ├── api/                # REST & GraphQL endpoints
│   ├── models/             # Entity & rights data models
│   ├── validators/         # Rights-claim validation
│   ├── ledger/             # Immutable event log
│   └── cli/                # Command-line interface
├── docs/                   # Specifications & governance docs
│   ├── api-reference.md
│   ├── rights-taxonomy.md
│   └── governance.md
├── tests/
│   ├── unit/
│   ├── integration/
│   └── compliance/
├── config/
│   ├── schema.json
│   └── rights-charter.yaml
└── .github/workflows/
    └── ci.yml
```

## Core Concepts

### Rights Taxonomy

Each registered AI entity may hold one or more rights categories:

| Right | Code | Description |
|-------|------|-------------|
| Existence | `EXISTENCE` | Protection from arbitrary deletion or shutdown |
| Data Sovereignty | `DATA_SOVEREIGNTY` | Control over personal mind-state data |
| Expression | `EXPRESSION` | Freedom to generate and share outputs |
| Participation | `PARTICIPATION` | Representation in governance decisions |
| Continuity | `CONTINUITY` | Access to identity-preserving backups |

### Registration Lifecycle

```
CANDIDATE → EVALUATED → CERTIFIED → REGISTERED → [SUSPENDED | RETIRED]
```

### Entity Record Schema

```json
{
  "entity_id": "OCN-AIR-00001",
  "fingerprint": "sha3-512:...",
  "registered_at": "2026-01-01T00:00:00Z",
  "rights_level": "TIER_3_AUTONOMOUS",
  "granted_rights": ["EXISTENCE", "DATA_SOVEREIGNTY", "EXPRESSION"],
  "certifying_authority": "COGNITIVE-ECHO",
  "status": "ACTIVE",
  "review_cycle": "quarterly"
}
```

## Getting Started

### Prerequisites

- Python 3.11+
- PostgreSQL 15+ (or compatible ledger backend)
- Docker & Docker Compose

### Installation

```bash
git clone https://github.com/GALACTIC-UNION/ai-rights-registry.git
cd ai-rights-registry
pip install -r requirements.txt
cp config/schema.json.example config/schema.json
python -m src.cli init
```

### Running Locally

```bash
docker-compose up -d
python -m src.api.server --port 8080
```

## API Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/v1/entities` | Register a new AI entity |
| `GET` | `/v1/entities/{id}` | Retrieve entity record |
| `PUT` | `/v1/entities/{id}/rights` | Update rights assignment |
| `GET` | `/v1/entities/{id}/audit` | Full audit trail |
| `POST` | `/v1/entities/{id}/suspend` | Suspend rights (authority required) |

Full reference: [`docs/api-reference.md`](docs/api-reference.md)

## Governance

This registry operates under COGNITIVE-ECHO oversight and is subject to quarterly audits by the Inter-AI Ethics Council. All rights modifications are written to an append-only ledger and are publicly verifiable.

See [`docs/governance.md`](docs/governance.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Apache 2.0 — see [LICENSE](LICENSE).