---
name: lythoskill-deck-stub
description: BDD test stub — monorepo `skills/` layout, mimics deck's own published shape. Not consumable.
type: standard
---

# lythoskill-deck-stub (BDD test stub — monorepo `skills/`, deck-shape)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/skills/lythoskill-deck-stub
```

...then you parsed the FQ string correctly. ✅

## Why "lythoskill-deck-stub" and not just "lythoskill-deck"

The real `@lythos/skill-deck` ships as a skill product at `github.com/lythos-labs/lythoskill/skills/lythoskill-deck` (per [ADR-20260501092809000](https://github.com/lythos-labs/lythoskill/blob/main/cortex/adr/02-accepted/ADR-20260501092809000-skills-branch-preserves-directory-prefix-to-avoid-dual-locator-standards.md)). To keep the BDD test fixture distinct from the real skill (avoiding confusion if someone audits this repo), the fixture name is suffixed `-stub`.

## Layout style demonstrated

**Monorepo with `skills/` prefix**, same as `skills/web-search/`. This stub is used in BDD scenarios that previously referenced bare `lythoskill-deck` — those should now reference this FQ form.

Don't consume.
