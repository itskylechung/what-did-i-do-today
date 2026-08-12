---
name: what-did-i-do-today
description: Daily zh-TW recap of what Kyle shipped, decided, and queued today in the Glows.ai GTM repository; then asks for tomorrow's plan and logs both to docs/content-strategy/standup-log.md. Use when the user asks "what did I do today", "what did i done tdy", "daily recap", "standup", "summarize today", or any variant asking for a rundown of today's work.
---

# What did I do today

Reconstruct today's work from evidence on disk, not memory. Write the recap entirely in zh-TW, while retaining English technical terms such as `commit`, Buffer, and queue.

By default, keep the recap clear and professional. Only use the optional **今日鳥事 (Workplace chaos)** section when Kyle explicitly asks for a funny, comedic, roast, or "add some 鳥事" version. When enabled, use the voice of a dry, observant workplace comedian: humour must come from real friction visible in the evidence—failed plans, rework, missing files, blocked approvals, or a scheduler that has apparently entered witness protection. Be kind to people, punch up at processes, and never invent a problem just to make a joke.

## Gather evidence

Run these checks, in parallel where practical:

1. Get today's date with `date +%Y-%m-%d`; use it to filter the remaining checks.
2. Read commits with `git log --all --since=midnight --oneline --stat`.
3. Check in-progress work with `git status --short`.
4. Search `docs/content-strategy/social-posts/*/*.md` for frontmatter containing `queued_at: <today>`; also inspect filenames carrying today's date. Record the platform, status, and scheduled time.
5. Inspect files modified today in `~/.claude/projects/-Users-kyelchung-glows-ai-glows-ai-gtm-phase-0/memory/` for strategy decisions, if that directory exists.
6. Read the last entry in `docs/content-strategy/standup-log.md`, if it exists. State which planned items actually happened.
7. Include relevant work from the current conversation that is not yet represented on disk, such as Buffer edits, research, or drafts in flight.

## Report

Lead with one zh-TW sentence naming the biggest result of the day. Use these sections, omitting empty ones:

- **今天完成 (Shipped)** — committed, published, or queued-and-live work. Lead with counts and names.
- **今天決定 (Decided)** — one line per strategy call, including its consequence.
- **進行中 (In flight)** — uncommitted work, pending drafts, and yesterday's planned items that did not happen.
- **今日鳥事 (Workplace chaos)** — optional; include only when Kyle asks for the funny version. Give one to three concise, evidence-backed observations about friction, rework, missing context, blockers, or plans that did not happen. Write with light comedic timing; omit it when there is no real evidence.
- **等你處理 (Needs you)** — only blockers Kyle must clear.

Do not add timestamps unless a deadline matters. If evidence is thin, say so in one line instead of padding the report.

## Ask about tomorrow

Never invent tomorrow's plan. Ask Kyle: 「明天打算做什麼？」 You may offer two or three candidate items drawn from **等你處理**, but Kyle decides and may provide a different answer.

## Log the standup

After Kyle replies, append this entry to `docs/content-strategy/standup-log.md`:

```md
## YYYY-MM-DD
**今天：** <one-line TL;DR of the recap>
**明天：** <Kyle's answer, verbatim-ish>
```

On the next daily recap, read this entry to check follow-through. Commit the log update when the repository workflow permits it.
