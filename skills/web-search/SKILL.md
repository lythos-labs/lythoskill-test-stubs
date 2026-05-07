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
