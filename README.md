# CI/CD Test

![CI/CD Pipeline](https://github.com/Robettaja/CI-CD/actions/workflows/lint.yml/badge.svg)

Simple Python app demonstrating CI/CD pipeline with lint, test, build, and release stages.

![CI/CD Pipeline](https://github.com/roope/CI-CD/actions/workflows/ci-cd.yml/badge.svg)

## Pipeline Stages

1. **Lint & Test** - ruff, mypy, pytest
2. **Build** - Create sdist + wheel artifacts
3. **Test Install** - Verify package installs from artifacts
4. **Release** - Auto-create GitHub Release on version tags

## Development

```bash
# Install dev dependencies
uv sync --group dev

# Run lint checks
uv run ruff check .
uv run ruff format --check .
uv run mypy app.py test_app.py

# Run tests
uv run pytest test_app.py -v

# Build package
uv run python -m build
```

## Release

```bash
git tag v1.0.0
git push origin v1.0.0
```
