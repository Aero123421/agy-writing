# agy-writing

An agent skill that delegates user-facing writing tasks to Gemini via the `agy` (Antigravity) CLI — with strict rules that keep the calling agent in control of technical and factual decisions.

## What it does

When a user explicitly asks to use `agy` / Antigravity / Gemini for writing work, this skill instructs the agent to:

- Verify `agy` is installed and authenticated, and copy a real model ID from `agy models` (never guess)
- Run `agy --mode=accept-edits --model "<MODEL_ID>" --print "<PROMPT>"` from the project directory
- Write prompts that specify purpose, audience, language/tone, exact files allowed, and what to preserve (facts, names, numbers, URLs, identifiers, placeholders)
- Inspect `git diff` afterwards, discard unrelated edits, and report what changed

Use cases: Japanese rewriting and proofreading, business documents and email, UX writing and UI microcopy, copywriting, localization, prose in documentation.

## Install

```bash
npx skills add Aero123421/agy-writing
```

Or manually:

```bash
git clone --depth 1 https://github.com/Aero123421/agy-writing ~/.agents/skills/agy-writing
```

## Requirements

- `agy` CLI (Google Antigravity) installed and authenticated
- An agent that supports Agent Skills (`SKILL.md`): Codex, Claude Code, Cursor, Gemini CLI, OpenCode, Devin, and others

## 日本語

`agy`（Antigravity）CLI経由でGeminiに文章作成・校正を委譲するスキル。日本語の書き換え、ビジネス文書、UXライティング、ローカライズ等に対応。技術的判断はエージェント側に残し、Geminiは文章のみ担当する安全設計。

インストール: `npx skills add Aero123421/agy-writing`

## License

MIT
