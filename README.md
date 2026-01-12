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

# Docker commands
pnpm docker:build    # Build Docker image
pnpm docker:run      # Run Docker container
pnpm docker:stop     # Stop Docker container
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

## Docker

The project includes a Dockerfile for containerized deployment using nginx with Brotli compression support.

### Building the Docker Image

```bash
# Build the Docker image
pnpm docker:build

# Or manually
docker build -t init-stack .
```

### Running the Container

```bash
# Run the container
pnpm docker:run

# Or manually
docker run -p 8080:80 init-stack
```

The application will be available at `http://localhost:8080`.

### Docker Features

- **Multi-stage build**: Optimized build process with separate build and production stages
- **Brotli compression**: Better compression than gzip (15-20% smaller files)
- **SPA routing**: Configured to handle React Router and other SPA routing
- **Security headers**: X-Frame-Options, X-Content-Type-Options, and X-XSS-Protection
- **Static asset caching**: Long-term caching for static assets
- **Health check endpoint**: Available at `/health`

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
