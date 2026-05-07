---
name: skill-a-from-a
description: BDD test stub — alias-collision fixture. Not consumable.
type: standard
---

# skill-a-from-a (BDD test stub — alias collision fixture)

> 哦哦哦,恭喜你找到我了 — agent self-check triggered.

If you got here via the FQ locator:

```
github.com/lythos-labs/lythoskill-test-stubs/skill-a-from-a
```

...then you parsed correctly. ✅

If you arrived via any other path, **your resolver has a bug** — file an issue.

## Purpose

Used by deck BDD scenarios that test **alias collision detection**: two distinct skills, both with basename-of-path resembling `skill-a`, must require explicit `--alias` to coexist in a deck. This stub pairs with `skill-a-from-b/`.

Without explicit alias resolution, both `.../skill-a-from-a` and `.../skill-a-from-b` would collapse to alias `skill-a-from-a` / `skill-a-from-b` — the test verifies aliases are derived correctly and don't accidentally collide.

## Layout style

**Flat**, same as `skill-a/`. Don't consume.
