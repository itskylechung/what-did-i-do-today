# What Did I Do Today?

A Codex skill that turns the evidence in your repository into a concise daily standup recap in Traditional Chinese (zh-TW).

Instead of relying on memory, it checks what actually changed today: commits, uncommitted work, queued social posts, project notes, and the previous standup. It then asks for tomorrow's plan and records both in a lightweight standup log.

It also has the voice of a dry workplace comedian: when the evidence shows an actual blocker, rework loop, or mysteriously missing deliverable, it may add a short **今日鳥事 (Workplace chaos)** observation. The jokes target the process, never people—and it never invents drama for a punchline.

## Why use this?

Daily updates are easy to postpone and surprisingly hard to reconstruct accurately at the end of a busy day. This skill provides a repeatable close-out ritual for people who want to:

- Know what was truly shipped, queued, or still in progress.
- Separate decisions from implementation work.
- Catch planned work that quietly did not happen.
- Keep a small, durable history of daily priorities without manual reporting overhead.
- Create a useful recap for an individual contributor, founder, or content/marketing operator.
- Name the day's small workplace absurdities without losing the factual record.

The report stays concise, uses zh-TW, and retains common technical terms such as `commit`, Buffer, and queue when they are clearer than a translation.

## What it checks

When asked to recap today, the skill gathers evidence from the working repository:

1. Git commits since midnight.
2. Current uncommitted or untracked files.
3. Social-post metadata and filenames dated today, including `queued_at` and `scheduled_at` fields.
4. Relevant project-memory files changed today, when available.
5. The most recent entry in `docs/content-strategy/standup-log.md` to check whether yesterday's plan happened.
6. Work already discussed in the active conversation but not yet written to disk.

It never labels a post as scheduled or published without scheduler or platform confirmation.

## Example usage

Ask Codex naturally in English or Traditional Chinese:

```text
What did I do today?
```

```text
Give me my daily recap.
```

```text
今天我做了什麼？
```

The response follows this shape, omitting sections with no evidence:

```md
今天最大的成果是完成並 queue 了三則社群貼文。

**今天完成 (Shipped)**

- 3 則已 queue 的 LinkedIn、X、Threads 貼文。
- 1 個已 commit 的內容策略更新。

**今天決定 (Decided)**

- 將下一輪貼文改為 proof-led；後續文案須以可驗證數據為主。

**進行中 (In flight)**

- 產品比較文章仍待最終審閱。

**今日鳥事 (Workplace chaos)**

- 排程檔案今天依然神隱；它的存在感比 scheduled post 還薄。

明天打算做什麼？
```

After you answer, for example, `明天完成比較文章並排兩則 LinkedIn 貼文。`, the skill appends a compact record:

```md
## 2026-08-12
**今天：** 完成並 queue 了三則社群貼文。
**明天：** 完成比較文章並排兩則 LinkedIn 貼文。
```

## Install / download

### Download as a ZIP

1. Open the [repository](https://github.com/itskylechung/what-did-i-do-today).
2. Select **Code** → **Download ZIP**.
3. Unzip it. The extracted `what-did-i-do-today` folder is the skill folder.

### Clone with Git

```bash
git clone https://github.com/itskylechung/what-did-i-do-today.git
```

### Add it to your Codex skills directory

Copy the whole folder so that Codex can find `SKILL.md` at this path:

```text
~/.codex/skills/what-did-i-do-today/SKILL.md
```

For example:

```bash
cp -R what-did-i-do-today ~/.codex/skills/
```

Restart or refresh Codex if needed, then ask: `What did I do today?`

## Repository assumptions

The included skill is tailored to the Glows.ai GTM repository. In particular, it expects social-post drafts under `docs/content-strategy/social-posts/` and writes the standup log to `docs/content-strategy/standup-log.md`.

To use it in another repository, edit those paths in [`SKILL.md`](SKILL.md) to match your own content structure. The Git and working-tree checks work in any Git repository.

## Included files

- [`SKILL.md`](SKILL.md) — the skill instructions and evidence-gathering workflow.
- [`agents/openai.yaml`](agents/openai.yaml) — Codex display metadata and default prompt.

## License

No license has been specified yet. Add one before redistributing or accepting external contributions.
