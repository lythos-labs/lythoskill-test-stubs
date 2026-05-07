---
name: inner-stub
description: BDD test stub — arbitrary subdir layout (no `skills/` prefix). Not consumable.
type: standard
---

# inner-stub (BDD test stub — arbitrary subdir layout)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/architecture-diagram-stub/inner-stub
```

...then you parsed the **arbitrary subdir** correctly. ✅

If you arrived via:
- `github.com/lythos-labs/lythoskill-test-stubs/skills/architecture-diagram-stub/inner-stub` — your resolver inserted a phantom `skills/` segment, **bug**
- `github.com/lythos-labs/lythoskill-test-stubs/inner-stub` — your resolver dropped the parent dir, **bug**

## Layout style demonstrated

**Arbitrary subdir** — neither `skills/` prefix nor a flat top-level dir. The skill lives at `<repo>/<arbitrary-name>/<inner>/SKILL.md`, mirroring `Cocoon-AI/architecture-diagram-generator` from [the real-world survey](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md). Cold-pool layout:

```
~/.agents/skill-repos/github.com/lythos-labs/lythoskill-test-stubs/
└── architecture-diagram-stub/
    └── inner-stub/
        └── SKILL.md   ← you're here
```

This is the **most adversarial** stub layout: any resolver heuristic that "guesses" `skills/` prefix or "flattens" the path will fail to resolve. FQ-only enforcement is required to land here.

Don't consume.

## Real-world peers (as of 2026-05-07)

The **arbitrary subdir** layout is the wildcard case — any author can place a skill under any directory name, with or without intermediate folders. Surveyed example:

- [`Cocoon-AI/architecture-diagram-generator/architecture-diagram`](https://github.com/Cocoon-AI/architecture-diagram-generator) — the canonical arbitrary-subdir reference. Repo named `architecture-diagram-generator`, skill at `architecture-diagram/SKILL.md` (one level deep, no `skills/` prefix). Real, active skill — not a stub.

Cross-reference: [skill-repo-structure-survey wiki](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md). This is the layout that **breaks all heuristic resolvers**: any "guess `skills/` prefix" or "flatten path" rule will miss it. FQ-only enforcement is the only correct policy.

Without this stub, a resolver that handles flat + monorepo + nested could still ship "looking right" while silently broken on Cocoon-AI-style repos. This stub catches that.
