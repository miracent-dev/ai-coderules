---
name: PyPackaging
globs: ["pyproject.toml"]
alwaysApply: false
---
# Packaging Standards (Triggered on pyproject.toml access)
- **Backend**: Use `setuptools.build_meta`.
- **Installation**: Use `pip install -e .` for dev.
- **Dependencies**: List in `[project].dependencies`, not requirements.txt.
- **Bundling**: Use the "Bundle Package" VS Code task.
