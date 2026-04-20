# Core Workflow

This skill assumes the standard WordPress Core development workflow centered on the `wordpress-develop` repository.

## Typical Local Setup

WordPress Core development commonly uses:

- Node.js 20.x
- npm 10.x
- Docker or a compatible container environment

Typical setup commands:

```bash
npm install
npm run build:dev
npm run env:start
npm run env:install
```

Typical watch workflow:

```bash
npm run dev
```

## Common Daily Commands

- Start the local environment: `npm run env:start`
- Stop the local environment: `npm run env:stop`
- Restart after config changes: `npm run env:restart`
- Reset containers and database: `npm run env:reset`
- Run WP-CLI in the local environment: `npm run env:cli -- <command>`
- View local environment logs: `npm run env:logs`

## Working Rules

- Edit source files, not generated output.
- Use the build or watch workflow when changes require copying or rebuilding assets.
- Prefer repo-defined scripts over ad hoc local commands when the repository already provides a standard entry point.