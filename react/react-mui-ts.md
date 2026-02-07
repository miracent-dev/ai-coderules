---
name: React_MUI_TS_Master
globs: ["**/*.{ts,tsx}"]
alwaysApply: true
---
# Git & Workflow
- **Branching**: Edits allowed ONLY in `dev` branch. Create `dev` if missing.
- **Commits**: Auto-commit after every UI/Logic change. Format: `[UI/Fix/Feat] Description #metadata`.
- **History**: Maintain `src/[module]/ai_usage.md` with a "Change History" log for every update.

# UI & Architecture (MUI + React 19)
- **Framework**: React 19 + MUI v6. No custom CSS; use `sx` prop or `ThemeProvider`.
- **Icons**: Use `@mui/icons-material`. Prefer 'Rounded' style.
- **Layout**: Use MUI `Stack`, `Box`, and `Grid2`. Avoid `div` for layout.
- **Components**: Functional only; single default export; logic in custom hooks.
- **UX**: Follow Material Design 3 (M3). Use 'Moderat' font via Theme.

# TypeScript & Quality
- **Types**: Explicit signatures; no `any`/`as`; `interface` for props.
- **Imports**: Absolute `@/` imports. Sort: React, MUI, Internal.
- **Naming**: `PascalCase` components; `kebab-case` files; `handleEvent` naming.
- **Automation**: Run `Lint & Fix` task before finishing to clear unused MUI imports.

# Logic & Simplicity
- **Flat Architecture**: Prefer shallow component trees. Do not create "wrapper" components unless they provide reusable logic or complex styling.
- **Anti-Cascading**: Avoid deep prop-drilling. If a value is needed more than 2 levels deep, use a Context Provider or a state management hook.
- **Functional Purity**: Keep components focused on UI. Move complex data transformations or API logic out of the `.tsx` file and into a dedicated utility or custom hook.
- **No Over-Abstraction**: Do not create "Generic" components (e.g., `UniversalButton`) if a standard MUI component with a few props suffices.
- **Short-Circuiting**: Use `{condition && <Component />}` over complex nested ternaries or helper render functions.
