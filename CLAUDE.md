# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Phoenix Cartographer Solutions is a professional landing page built with Astro and deployed to Cloudflare Workers. The site showcases cartography and geographic information services with a modern, responsive design.

## Development Commands

| Command | Purpose |
|---------|---------|
| `npm run dev` | Start development server at localhost:4321 |
| `npm run build` | Build for production (generates dist/_worker.js for Cloudflare Workers) |
| `npm run preview` | Preview production build locally |
| `npx wrangler deploy` | Deploy to Cloudflare Workers |
| `npx wrangler tail phoenix-cartographer-solutions` | View live Worker logs |

## Architecture

This is an Astro project configured for server-side rendering on Cloudflare Workers:

- **Framework**: Astro 5.x with `output: 'server'` mode
- **Adapter**: `@astrojs/cloudflare` for Workers deployment
- **Deployment**: Cloudflare Workers via Wrangler CLI
- **Styling**: Inline CSS within the main Astro page component

### Key Configuration

- `astro.config.mjs`: Configures Cloudflare adapter with server output
- `wrangler.toml`: Cloudflare Workers deployment configuration
- Main entry point: `dist/_worker.js/index.js` (generated during build)

### Important Notes

- The site uses `output: 'server'` (not `static`) because the Cloudflare adapter requires server-side rendering capabilities
- All styling is currently inline within `src/pages/index.astro`
- The site is a single-page application with sections for hero, services, and footer
- Live site: https://phoenix-cartographer-solutions.bytecrash.workers.dev