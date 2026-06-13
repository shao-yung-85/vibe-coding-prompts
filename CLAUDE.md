# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A **content-only, bilingual (Chinese-primary, English summary)** open-source collection of copy-paste-ready prompt templates for *vibe coding*. There is no build system, test suite, or application code — every change is to Markdown. The "product" is the prompts and their explanations, so editorial quality is the only thing that matters.

## Files

- `README.md` — the main deliverable. 12 prompt categories, each with 5+ templates, plus a tool comparison table, contribution section, and an English summary at the very end.
- `CLAUDE-md-template.md` — a reusable `CLAUDE.md` template (full + minimal versions) that downstream users copy into *their own* projects. Do not confuse it with this file.
- `CONTRIBUTING.md` — the authoritative spec for prompt format. Read it before adding or editing any prompt.
- `LICENSE` — MIT, author `shao-yung-85`.

## Non-negotiable content rules

Every prompt template must follow the **four-part format** defined in `CONTRIBUTING.md`:

1. **Numbered title** — states the use case in one line.
2. **Prompt body** — inside a fenced ` ``` ` code block so it's one-click copyable; user fill-ins use `[方括號]` placeholders. Must be a complete, paste-and-go prompt, not an abstract description.
3. **`**為什麼有效：**` explanation** — 2–4 sentences on *why* the prompt works (what AI behavior it triggers, what trap it avoids). This is the soul of the project and is **never** optional.

Two principles override everything else:
- **寧缺勿濫 (quality over quantity)** — reject filler. One well-explained prompt beats ten mediocre ones.
- **Every prompt must be copy-paste ready AND explain why it works.** If either is missing, it doesn't ship.

## Style conventions (match existing content)

- Chinese (Traditional) is primary; the English summary lives only at the end of `README.md`.
- Emoji are used to mark category headers and key points — purposeful, not on every line.
- The 12 category emoji are fixed and used consistently across `README.md` and `CONTRIBUTING.md`: 🚀 專案初始化 / ✨ 新增功能 / 🐛 Debug / ♻️ 重構 / 🧪 寫測試 / 🎨 UI / 🗄️ 資料庫 / 🚢 部署 / 📝 寫文件 / 🧠 通用心法 / 🛡️ 護欄 / 📋 CLAUDE.md。
- The README's table of contents uses GitHub anchor links — when renaming a heading, update the matching TOC entry and any cross-links.
- Tone: 實用優先、零廢話 (practical first, no fluff). No long prefaces.

## When adding a new category

`CONTRIBUTING.md` requires a justification plus at least 3 prompts before a new category is added. A new category must be reflected in three places: the README TOC, the README body, and the category list in `CONTRIBUTING.md`.

## Git

Branch is `main`. Commit author is `shao-yung-85 <chouhome1127@gmail.com>`. There is no remote configured yet; pushing requires the user to create the GitHub repo first. The README badges and links hard-code the `shao-yung-85` username — keep them in sync if the owner changes.
