# React + TypeScript + Vite

A modern React project with TypeScript, Vite, and modern tooling.

## Stack

- **React** 19.2.0
- **TypeScript** 5.9.3
- **Vite** (rolldown-vite 7.2.5) - Vite based on Rolldown for faster builds
- **Tailwind CSS** 4.1.18 - Utility-first CSS framework
- **pnpm** - Package manager

## Tooling

- **oxfmt** - Code formatting (faster alternative to Prettier)
- **oxlint** - Linting (faster alternative to ESLint)
- **@vitejs/plugin-react-swc** - React plugin using SWC for faster compilation
- **Commitlint** - Conventional commit message linting
- **Lefthook** - Git hooks manager

## Scripts

```bash
# Start development server
pnpm dev

# Build project
pnpm build

# Preview production build
pnpm preview

# Format code
pnpm format

# Check formatting
pnpm format:check

# Lint code
pnpm lint

# Lint and auto-fix
pnpm lint:fix

# Type check
pnpm typecheck
```

## Development

The project uses Vite with HMR (Hot Module Replacement) for fast development. Start the development server with `pnpm dev` and the browser will automatically open at `http://localhost:5173`.

### Path Aliases

The project uses path aliases for cleaner imports:

- `@/` maps to `./src/`

Example:

```typescript
import Component from "@/components/Component";
```

## Build

Build the project with `pnpm build`. The output will be in the `dist/` folder with source maps enabled.

## Git Hooks (Lefthook)

The project uses Lefthook to run automated checks:

- **pre-commit**: Runs audit, formats code, lints, and type checks
- **commit-msg**: Validates commit messages follow conventional commit format
- **pre-push**: Runs build to ensure code compiles
- **post-checkout**: Automatically pulls latest changes when checking out main branch

### Commit Message Format

Commit messages must follow the conventional commit format:

- `feat`: New feature
- `fix`: Bug fix
- `chore`: Maintenance tasks
- `docs`: Documentation changes
- `refactor`: Code refactoring
- `test`: Test changes
- `ci`: CI/CD changes

Example: `feat: add user authentication`
