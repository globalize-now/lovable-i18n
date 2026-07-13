# lovable-i18n

Add multi-language support (i18n) to a [Lovable](https://lovable.dev) app using [Lingui](https://lingui.dev).

This repository is a **standalone, single-file agent skill** for the Lovable platform agent (not
Claude Code). The entire skill is `SKILL.md` at the repository root.

## Why this repo exists

`lovable-i18n` is maintained in the [`globalization-skills`](https://github.com/globalize-now/globalize-skills)
monorepo under `skills/lovable-i18n/`. Lovable imports skills by pointing at a GitHub repo, and its
import works reliably against a repository **root** but not against a **subdirectory**. This repo
is a standalone extraction so the skill sits at the root and can be imported directly.

The monorepo remains the canonical source — changes should be made there and mirrored here.

## Import into Lovable

In your Lovable workspace: **Settings → Skills → import from GitHub**, and point at **this repo
(the root — no subdirectory)**. Alternatively, upload `SKILL.md` or a zip of this repo.

Once imported, ask Lovable to "add i18n", "make my app multilingual", "add Spanish/French/German
support", "add a language switcher", or "connect Globalize" to trigger the skill.

## What the skill does

- **Setup for both Lovable stacks** — Vite SPA and TanStack Start (SSR).
- **Wraps hardcoded strings** for translation and maintains **PO catalogs**.
- Adds a **GitHub Actions workflow** that keeps message catalogs in sync (extraction).
- Writes **coding rules** into the target app's `AGENTS.md` so future edits stay i18n-correct.
- **Connects the [Globalize.now](https://globalize.now) translation platform** (via its MCP
  connector, with CLI/dashboard fallbacks).

## License

[MIT](./LICENSE)
