# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

## Artifacts

- **`artifacts/numeriq`** — NumériQ : single-page web app for the Tunisian Bac Informatique 4ème année curriculum. Self-contained `index.html` (originally sourced from `attached_assets/bac_info_tunisie_*.html`, now extended in-place) with inline CSS/JS — dark theme, gold/blue/pink accents, Tajawal/Amiri/Space Mono fonts. Sections: (01) Point Fixe / Dichotomie / Newton, (02) Constantes π/√2/e/ln2, (03) Aire — Rectangles & Trapèzes, (04) Optimisation — Gradient & Ternaire, (05) Tris — Bulles/Sélection/Insertion + comparaison animée, (06) Recherche — Séquentielle/Dichotomique + comparaison, (07) Récursivité — Factorielle/Fibonacci/PGCD/Hanoï avec traces, (08) Arithmétique — PGCD-PPCM (+ Bézout) / Primalité (+ crible) / Décomposition / Conversion bases, plus a full "Algo Tunisien" pseudocode editor with tokenizer/parser/interpreter (procédures, fonctions, tableaux, matrices, répéter/jusqu'à, tantque, pour). URL hash routing (`#tris`, `#arith`, etc.) supported. Served at `/`.
- **`artifacts/api-server`** — Express 5 API at `/api`.
- **`artifacts/mockup-sandbox`** — design canvas at `/__mockup`.

To regenerate NumériQ from the source HTML: `cp attached_assets/bac_info_tunisie_*.html artifacts/numeriq/index.html`.
