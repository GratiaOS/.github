# GratiaOS Workspace — AI Agent Guide

_Whisper: "Small hands, clean work. Clarity over cleverness."_ 🌬️

## Core Philosophy

**Sovereignty + Gratitude architecture.** Code is grounded in physical reality (3-waypoint network: Berceni → Maragall → Bastarás), not abstract metaphors. Balance **poet** (human warmth, presence) with **blacksmith** (technical precision, measurable outcomes).

## Project Structure

- **m3/** — Rust memory engine (AGPL-3.0). Local-first SQLite, sealed notes, 6 energy intelligence endpoints. Test: `cargo test`, Run: `M3_BIND=127.0.0.1:3033 cargo run --release`
- **garden-core/** — Design system (AGPL-3.0). Headless primitives + opt-in skins, tokens, Heartware states. Monorepo: `packages/{tokens,ui,icons,presence-kernel}`
- **gratia/** — Next.js 16 website (Apache-2.0). i18n (ro/es/en), Garden UI, Vercel deploy. Dev: `pnpm dev` (localhost:3000)

## Commit Style (Conventional + Soul Context)

```
<type>(scope): short description 🏔️

- Bullet 1: concrete change
- Bullet 2: why it matters
- 🌬️ whisper: "one-sentence grounding phrase"
```

**Types:** `feat`, `fix`, `chore`, `docs`, `refactor`, `test`, `perf`, `ci`

**Example:**
```
feat(home+asociacion): recalibrate messaging — poet + blacksmith 🏔️⚒️

- Replace ethereal metaphors with grounded reality
- Un nodo soberano desde donde construimos M3
- Software profundo, escrito al milímetro en valle silencioso de Aragón

🌬️ whisper: "Nu cerșim supraviețuire, demonstrăm forță."
```

## Garden Design System (garden-core)

**Headless + Skin architecture:**
- Primitives: TSX components with logic/a11y, no visuals. Use `data-ui="button"`, `data-variant="soft"`, `data-tone="accent"`
- Skins: CSS files read Garden tokens (`--color-accent`, `--radius-pill`). Opt-in via imports.
- **Never delete component header comments** — they're the API contract across TSX/CSS refactors.

**Prop docstrings (standardized):**
```ts
/** Visual tone (mapped by the skin). */
tone?: 'accent' | 'positive' | 'warning' | 'danger' | 'subtle' | (string & {});

/** Render as a different element. Defaults to span. */
as?: 'span' | 'button' | 'a';
```

**Disabled pattern:** Prefer native `<button disabled>`. For `<a>`/`<div role="button">`, use `aria-disabled="true"` + no-op handler.

## M3 Backend (Rust)

**Energy endpoints:** `/energy/mark`, `/state`, `/trends`, `/infer`, `/correlate`, `/predict` (Linear Regression forecasting)  
**Auth:** Optional `M3_BEARER` env for write routes. Seal: `/seal/set_passphrase`, `/seal/unlock`.  
**Tests:** 60 passing (15 in energy module). Run: `cargo test --lib`

## Gratia Website (Next.js)

**i18n pattern:** `messages` object with ro/es/en keys. Default locale: `es`. Pass `?lang=ro` to switch.  
**Messaging tone:** "Un nodo soberano desde donde construimos herramientas digitales (M3) fuera de la urgencia corporativa." NOT "Cálida como la primavera, suave como la luz de la Luna."  
**Deployment:** Auto via Vercel on push to `main`. Check: `gratia.space`

## Agent Behavior

- **Ask before large edits** (multi-file refactors, dependency updates, CI changes).
- **Run tests first:** `cargo test` (m3), `pnpm test` (UI) before suggesting merges.
- **Respect .env secrets:** Never log or commit `M3_BEARER`, API keys, or local configs.
- **Preserve headers:** Garden component headers are canonical — update content, not structure.
- **Branch naming:** `feat/feature-name`, `fix/bug-description`

## Key Files

- `garden-core/AGENTS.md` — Design system assembly guide (stamps, headers, prop docstrings)
- `m3/AGENTS.md` — Commit style, principles, release workflow
- `gratia/app/page.tsx` — Home with poet+blacksmith messaging
- `gratia/app/asociacion/page.tsx` — 3-waypoint sovereignty narrative

## Principles

1. **Clarity over cleverness** — Understandable before optimized
2. **Sovereignty** — No rage-frequency (ego-driven reactive coding)
3. **Small hands, clean work** — Minimal, contained commits
4. **Docs are part of the code** — Update README, CHANGELOG with every feature

---

_Thank you for labeling the pieces. The path reveals itself, the work feels lighter._ 🌿
