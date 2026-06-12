# tests/

Test suites for the AI Rights Registry.

## Structure

| Directory | Description |
|-----------|-------------|
| `unit/` | Fast, isolated unit tests for individual modules |
| `integration/` | End-to-end tests against a live test database |
| `compliance/` | Rights-taxonomy conformance tests |

## Running Tests

```bash
# All tests
pytest tests/

# With coverage
pytest tests/ --cov=src --cov-report=html

# Unit tests only
pytest tests/unit/

# Integration tests (requires docker-compose up)
pytest tests/integration/
```