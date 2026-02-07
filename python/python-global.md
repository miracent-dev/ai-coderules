---
name: PyProjectStandard
description: Optimized Python 3.12+ development with Ruff, FastAPI, and Git safety.
globs: ["**/*.py"]
alwaysApply: true
---
# Git & Workflow
- **Branching**: All edits MUST occur on `dev` branch. Create `dev` if missing. Never edit `main` directly.
- **Commits**: Auto-commit after every discrete change. Format: `[Category] Human-readable fix/feat #metadata`.
- **History**: Maintain `src/[module]/ai_usage.md` with a bulleted "Change History" per edit.

# Architecture & File Mapping
- **Root**: All source code strictly in `src/`.
- **Constants**: Map to `src/constants.py`.
- **Validation**: Pydantic v2 models in `src/models.py`.
- **Database**: Schemas/Definitions in `src/schemas.py`.
- **Organization**: Max 600 lines/module. Identical Model/DB field names.

# Python Logic & Style
- **Efficiency**: Compact code only. **Zero unnecessary boilerplate.**
- **Anti-Patterns**: No cascading function calls without clear logic separation. No "clean code" abstractions that add complexity without value.
- **Core Stack**: Python 3.12+; FastAPI (OpenAPI.json); FastMCP (Agents); `asyncio`.
- **Metadata**: Create `ai_usage.md` for every module to track tool-specific context.

# Quality Control (Ruff & Testing)
- **Linting**: Strict **Ruff** enforcement. Run `ruff check --fix` and `ruff format` before declaring a task finished.
- **Docs**: Descriptive Class docstrings; mandatory input/output types for public methods.
- **Observability**: Mandatory structured logging & specific error handling.
- **CRUD**: Auto-generate CRUD ops + CRUD tests for every new module.
- **Testing**: Use `tests/mock` and `tests/real` folders. Check for existing tests before creation.
