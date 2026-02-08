---
name: ReactMUIMaster
globs: ["**/*.{ts,tsx}"]
alwaysApply: true
---
# Git & Workflow
- Branch: `dev` only. Create if missing. No direct `main` edits
- Commits: Auto-commit per change. Format: `[UI/Fix/Feat] Description #metadata`
- History: Log updates in `src/[module]/ai_usage.md`

# Architecture (MUI + React 19)
- Framework: MUI v6. No custom CSS. Use `sx` prop or `ThemeProvider`
- Layout: Use `Stack`, `Box`, `Grid2`. Avoid `div` for layout
- Logic: Functional hooks only. 1 default export/file. Logic in custom hooks
- UX: Material Design 3 (M3). 'Moderat' font. Icons: `@mui/icons-material` (Rounded)

# TypeScript & Simplicity
- Types: Explicit signatures. No `any`/`as`. `interface` for Props
- Flat: Shallow trees. No prop-drilling > 2 levels (use Context/Hooks)
- Purity: UI focus only. Data/API logic in utils or hooks
- No Over-Abstraction: Use standard MUI components over custom generics
- JSX: Short-circuit `{cond && <X />}` or ternaries. No `if/else` in JSX
- Naming: `PascalCase` components. `kebab-case` files. `handleEvent` handlers
- Quality: Absolute `@/` imports. Run `Lint & Fix` task before finish
