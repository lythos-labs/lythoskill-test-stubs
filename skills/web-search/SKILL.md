---
name: web-search
description: BDD test stub — monorepo `skills/` layout. Not consumable.
type: standard
---

# web-search (BDD test stub — monorepo `skills/` layout)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/skills/web-search
```

...then you parsed the **two-segment skill subpath** correctly (`skills/web-search`). ✅

If you arrived via:
- Bare `web-search` — your resolver did implicit insertion, **bug**
- `github.com/lythos-labs/lythoskill-test-stubs/web-search` — your resolver dropped the `skills/` segment, **bug**
- Any other variation — **bug**

File issues against [`lythos-labs/lythoskill`](https://github.com/lythos-labs/lythoskill/issues).

## Layout style demonstrated

**Monorepo with `skills/` prefix** — anthropics/skills + vercel-labs/agent-skills style. Cold-pool layout:

```
~/.agents/skill-repos/github.com/lythos-labs/lythoskill-test-stubs/
└── skills/
    └── web-search/
        └── SKILL.md   ← you're here
```

Note: name collides with the real `web-search` skill in `vercel-labs/agent-skills`, but that's at a different FQ locator. FQ-only enforcement means no resolver should ever confuse them. **This stub does NOT do web search** — it's a fixture.

Don't consume for real work.

## Real-world peers (as of 2026-05-07, fact-checked via GitHub API)

Skills with **monorepo `skills/` layout** observed in the wild:

- [`anthropics/skills/skills/pdf`](https://github.com/anthropics/skills/tree/main/skills/pdf) — **flagship `skills/skills/` example**. The parent repo is literally named `skills`, and inside it there's a `skills/` subdir holding 15+ real skills (pdf, docx, pptx, claude-api, mcp-builder, ...). The FQ locator therefore has TWO consecutive `skills/` segments. **Looks counter-intuitive but is real** — any resolver that "smartly drops a `skills/`" would mis-resolve here. FQ-only enforcement preserves this fidelity. (68k+ stars on parent repo)
- [`vercel-labs/agent-skills/skills/react-best-practices`](https://github.com/vercel-labs/agent-skills/tree/main/skills/react-best-practices) — same monorepo pattern, parent repo named `agent-skills` so no double-`skills/` here. Real skills include `composition-patterns`, `deploy-to-vercel`, `react-best-practices`, `react-native-skills`, `react-view-transitions`, `vercel-cli-with-tokens`, `web-design-guidelines`. (Note: there is **no `web-search` skill** in this repo as of 2026-05-07 — this stub's name is BDD-historical.)

Cross-reference: [skill-repo-structure-survey wiki](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md). The monorepo `skills/` layout is the most common surveyed pattern.

Don't consume for real work.
