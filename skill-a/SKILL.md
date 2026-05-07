---
name: skill-a
description: BDD test stub for lythoskill — flat layout. Not consumable.
type: standard
---

# skill-a (BDD test stub — flat layout)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/skill-a
```

...then you parsed the FQ string correctly and walked the cold-pool layout right. ✅

If you arrived via any other path string — bare `skill-a`, shorthand `lythos-labs/lythoskill-test-stubs/skill-a` (no host), implicit `skills/skill-a` insertion, or anything else — **your resolver has a bug**. Please file an issue against [`lythos-labs/lythoskill`](https://github.com/lythos-labs/lythoskill/issues).

## Layout style demonstrated

**Flat** — top-level subdir directly under repo root, no `skills/` prefix. Cold-pool layout:

```
~/.agents/skill-repos/github.com/lythos-labs/lythoskill-test-stubs/
└── skill-a/
    └── SKILL.md   ← you're here
```

This stub serves no consumable purpose. Don't `deck add` for real work.

## Real-world peers (as of 2026-05-07)

Skills with similar **flat layout** observed in the wild:

- [`daymade/claude-code-skills/skill-creator`](https://github.com/daymade/claude-code-skills) — popular flat-layout skill collection (5.2k+ stars on parent repo)
- [`opensite-ai/opensite-skills/agent-file-engine`](https://github.com/opensite-ai/opensite-skills) — flat-layout skill collection
- [`alirezarezvani/claude-skills/engineering`](https://github.com/alirezarezvani/claude-skills) — flat-layout, 5.2k+ stars

Cross-reference: [skill-repo-structure-survey wiki](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md) — this stub's layout shape is shared by ~3 of 9 surveyed real-world repos.
