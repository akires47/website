# akires47-website

A bold and modern single-viewport personal portfolio built with Astro 5 and Tailwind CSS.

## Overview

This is a static personal portfolio website featuring a modern, single-page design with vivid gradients, dark theme aesthetics, and geometric background elements. The entire experience fits within a single viewport (`100vh`) for maximum impact.

## Tech Stack

- **Framework**: [Astro 5.x](https://astro.build) - Static site generator
- **Language**: TypeScript (strict mode)
- **Styling**: [Tailwind CSS 3.x](https://tailwindcss.com)
- **Package Manager**: pnpm (required)
- **Deployment**: Cloudflare Workers

## Design System

### Typography
- **Headings**: Syne (bold, confident)
- **Body Text**: Inter

### Color Palette
- **Background**: `bg-zinc-950` (dark)
- **Primary Text**: `text-zinc-100`
- **Secondary Text**: `text-zinc-400`
- **Muted Text**: `text-zinc-500`
- **Accent Colors**: `violet-500`, `fuchsia-500`, `cyan-500`
- **Gradients**: `violet-400`, `fuchsia-400`, `cyan-400`

## Getting Started

### Prerequisites

- Node.js 18+ (or latest LTS)
- pnpm (required - do not use npm or yarn)

### Installation

```bash
# Install dependencies
pnpm install
```

### Development

```bash
# Start development server (runs on http://localhost:4321)
pnpm run dev

# Build for production (recommended for validation)
pnpm run build

# Preview production build
pnpm run preview
```

## Project Structure

```
akires47-website/
├── src/
│   ├── components/     # Reusable Astro components (PascalCase.astro)
│   ├── layouts/        # Page layout templates
│   └── pages/          # File-based routing (each file = a route)
├── public/             # Static assets (served at root)
├── dist/               # Build output (generated)
├── astro.config.mjs    # Astro configuration
├── tailwind.config.mjs # Tailwind configuration
├── wrangler.json       # Cloudflare Workers configuration
└── package.json        # Project dependencies
```

## Deployment

This site is configured for deployment on Cloudflare Workers:

```bash
# Build the project
pnpm run build

# Deploy to Cloudflare Workers
wrangler deploy
```

The `wrangler.json` configuration points to the `dist/` directory for static assets.

## Code Style

- **Indentation**: 4 spaces in Astro/HTML files
- **Quotes**: Single quotes for JavaScript strings
- **Line Endings**: LF (configured in .gitattributes)
- **Trailing Commas**: Use in arrays and objects

## Development Guidelines

For detailed coding guidelines and agent instructions, see:
- [`AGENTS.md`](./AGENTS.md) - Comprehensive coding guidelines for AI agents
- [`CLAUDE.md`](./CLAUDE.md) - Symlink to AGENTS.md for Claude Code integration

## Git Workflow

This project uses conventional commits:
- `feat:` - New features
- `fix:` - Bug fixes
- `chore:` - Maintenance tasks
- `docs:` - Documentation updates
- `refactor:` - Code refactoring
- `style:` - Code style changes

## License

Private project - All rights reserved.
