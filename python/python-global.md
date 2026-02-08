---
name: PyProjectMaster
globs: ["**/*.py", "pyproject.toml"]
alwaysApply: true
---
# Git Workflow
- Branch: `dev` only. Create if missing. No direct `main` edits
- Commits: Auto-commit per change. Format: `[Category] Fix/Feat #metadata`
- History: Log updates in `src/[module]/ai_usage.md`

# Architecture & Packaging
- Layout: Root `src/`. Constants `constants.py`. Models `models.py`. DB `schemas.py`
- Packaging: Use `setuptools.build_meta`. Deps in `[project].dependencies`
- Install: `pip install -e .` for dev. Use "Bundle" VS Code task for builds
- Rules: Max 600 lines/module. Identical Model/DB field names. Python 3.12+

# Logic & Style
- Efficiency: Compact code. No boilerplate. No cascading calls
- Simplicity: Avoid abstractions without value. Clear logic separation
- History: Module-level `ai_usage.md` for tool context

# Quality & Test
- Lint: Strict Ruff (`ruff check --fix` + `ruff format`) before finish
- Docs: Class docstrings + mandatory input/output types
- CRUD: Auto-gen CRUD + tests for new modules
- Tests: Use `tests/mock` or `tests/real`. Check existing first
- Observability: Structured logging + specific error handling required
