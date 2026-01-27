# AGENTS.md - Coding Agent Guidelines

This document provides guidelines for AI coding agents working in this repository.

## Project Overview

- **Framework**: Astro 5.x (static site generator)
- **Language**: TypeScript (strict mode)
- **Styling**: Tailwind CSS 3.x
- **Package Manager**: pnpm (required - never use npm or yarn)
- **Type**: Single-viewport Personal Portfolio (Bold & Modern)

## Build Commands

```bash
# Development server (only run when explicitly requested)
pnpm run dev

# Production build (use this for validation instead of dev server)
pnpm run build

# Preview production build locally
pnpm run preview

# Direct Astro CLI access
pnpm run astro <command>
```

### Important Notes

- **Prefer `pnpm run build`** over `pnpm run dev` for validation
- No ESLint or Prettier configured - maintain consistency with existing code
- No testing framework configured - tests not currently available

## Project Structure

```
src/
├── components/     # Reusable Astro components (PascalCase.astro)
├── layouts/        # Page layout templates
└── pages/          # File-based routing (each file = a route)
public/             # Static assets served at root
```

## Code Style Guidelines

### Aesthetic Direction (Bold & Modern)

- **Single Viewport**: All content must fit within `100vh` (`overflow: hidden` on body).
- **Typography**: 
  - `font-display` (Syne) for headings (bold, confident).
  - `font-sans` (Inter) for body text.
- **Visuals**:
  - Dark theme (`bg-zinc-950`).
  - Vivid gradients (`violet-400`, `fuchsia-400`, `cyan-400`).
  - Geometric background elements with heavy blur.
  - Large, prominent avatar with creative framing.

### Astro Components

Components follow this structure:

```astro
---
// 1. TypeScript interfaces for props
interface Props {
  title: string;
  description?: string;
}

// 2. Destructure props with defaults
const { title, description = "Default value" } = Astro.props;

// 3. Additional logic/data
---

<!-- 4. HTML template -->
<section class="h-screen ...">
  <h1>{title}</h1>
</section>

<!-- 5. Optional scoped or global styles -->
<style is:global>
  /* styles */
</style>
```

### TypeScript

- Use `interface Props` for component props (not `type`)
- Destructure `Astro.props` at the top of frontmatter
- Provide sensible defaults for optional props
- Define separate interfaces for complex nested types

### Imports

- Use ES module syntax (`import`/`export`)
- Include `.astro` extension for Astro components
- Order: layouts first, then components, then utilities/types

### Tailwind CSS

- Use utility classes directly in markup
- **Colors**:
  - Background: `bg-zinc-950`
  - Text: `text-zinc-100` (primary), `text-zinc-400` (secondary), `text-zinc-500` (muted)
  - Accents: `violet-500`, `fuchsia-500`, `cyan-500`
- **Fonts**:
  - Headings: `font-display` (Syne)
  - Body: `font-sans` (Inter)

### Formatting

- **Indentation**: 4 spaces in Astro/HTML files
- **Quotes**: Single quotes for JavaScript strings
- **Line endings**: LF (configured in .gitattributes)
- **Trailing commas**: Use in arrays and objects

### HTML/Accessibility

- Use semantic HTML elements
- Include `aria-label` for icon-only links
- Add `alt` attributes to all images
- External links should have `target="_blank"`

## Git Workflow

- Use conventional commits: `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `style:`
- Keep commits atomic and focused
- Never push without explicit confirmation
- Default branch: `main`

## Background Tasks

- Never start dev server unless explicitly requested
- Stop dev servers before ending conversation
- Use `pnpm run build` to validate changes

## Common Patterns

### Gradient Text

```html
<span class="bg-gradient-to-r from-violet-400 via-fuchsia-400 to-cyan-400 bg-clip-text text-transparent">
  Bold Text
</span>
```

### Blurred Background Orbs

```html
<div class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-violet-500/10 rounded-full blur-[120px]"></div>
```

### Social Icon Button

```html
<a href="#" class="p-3 bg-zinc-900/50 border border-zinc-800 rounded-full text-zinc-400 hover:text-white hover:border-violet-500/50 hover:bg-violet-500/10 transition-all duration-300 backdrop-blur-sm">
  <svg>...</svg>
</a>
```
