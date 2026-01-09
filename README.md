# React + TypeScript + Vite

A modern React project with TypeScript, Vite, and modern tooling.

## Stack

- **React** 19.2.0
- **TypeScript** 5.9.3
- **Vite** (rolldown-vite 7.2.5) - Vite based on Rolldown for faster builds
- **pnpm** - Package manager

## Tooling

- **oxfmt** - Code formatting (faster alternative to Prettier)
- **oxlint** - Linting (faster alternative to ESLint)

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
```

## Development

The project uses Vite with HMR (Hot Module Replacement) for fast development. Start the development server with `pnpm dev` and open your browser to the displayed URL.

## Build

Build the project with `pnpm build`. The output will be in the `dist/` folder.
