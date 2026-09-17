---
name: agy-writing
description: Use only when the user explicitly asks to use agy, Antigravity, or Gemini for user-facing writing such as Japanese rewriting or proofreading, business documents and email, UX writing and UI microcopy, copywriting, localization, or prose in documentation.
---

1. Delegate only the requested writing work; keep technical and factual decisions with the current agent, and never invoke this skill automatically.
2. Confirm `agy` is installed and authenticated; when the exact model is not given, run `agy models` and copy an available Gemini model ID verbatim—never guess a model name.
3. Run from the relevant project directory with `agy --mode=accept-edits --model "<MODEL_ID>" --print-timeout 10m --print "<PROMPT>"`; quote multiline or user-supplied text safely. Do not use `--dangerously-skip-permissions` by default. Because this skill is only invoked when the user explicitly requested agy, Antigravity, Gemini, or this skill, if the headless agy run is blocked solely by a permission prompt that cannot be answered, retry that agy invocation once with `--dangerously-skip-permissions`. Do not add broad or persistent permission rules to agy/Antigravity settings merely to make the delegation work, and do not abandon the requested agy delegation in favor of doing the delegated writing yourself before this retry.
4. In the prompt, state the purpose, audience, language and tone, exact files allowed, and required changes; tell Gemini not to modify other files or behavior and to preserve facts, names, numbers, URLs, identifiers, and placeholders unless explicitly requested.
5. After completion, inspect `git diff` or the equivalent, discard unrelated edits, and report the files changed plus any unresolved context.
