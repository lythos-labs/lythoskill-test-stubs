---
name: tdd-stub
description: BDD test stub — nested-category layout. Not consumable.
type: standard
---

# tdd-stub (BDD test stub — nested category layout)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/skills/engineering/tdd-stub
```

...then you parsed the **three-segment skill subpath** correctly (`skills/engineering/tdd-stub`). ✅

If you arrived via:
- `github.com/lythos-labs/lythoskill-test-stubs/skills/tdd-stub` — your resolver dropped the `engineering/` middle segment, **bug**
- Any flatter form — **bug**

## Layout style demonstrated

**Nested category** — `skills/<category>/<skill>/SKILL.md`, the mattpocock/skills style. Cold-pool layout:

```
~/.agents/skill-repos/github.com/lythos-labs/lythoskill-test-stubs/
└── skills/
    └── engineering/
        └── tdd-stub/
            └── SKILL.md   ← you're here
```

This stub is named `-stub` to keep it distinct from the real `tdd` skill in mattpocock/skills.

Don't consume.

## Real-world peers (as of 2026-05-07)

The **nested category** layout is rarer than flat or monorepo, but the canonical example is:

- [`mattpocock/skills/skills/engineering/tdd`](https://github.com/mattpocock/skills) — the real `tdd` skill (don't confuse with this stub — different FQ locator). Same author has multiple skills nested under `skills/<category>/<skill>/`, e.g., `skills/engineering/diagnose`, etc.

Cross-reference: [skill-repo-structure-survey wiki](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md) — only 1 of 9 surveyed real-world repos uses this nested style. As more authors organize skills by category, this layout may grow.
