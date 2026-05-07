# lythos-labs/lythoskill-test-stubs

> Empty-content stub skills for `lythos-labs/lythoskill` BDD test fixtures.
> Not consumable. Don't `deck add` these except for testing.

## Why this repo exists

The lythoskill BDD scenarios used to declare bare skill names (`skill-a`, `skill-b`, etc.) that were resolved via fallback strategies in `findSource`. After [ADR-20260502012643244](https://github.com/lythos-labs/lythoskill/blob/main/cortex/adr/01-proposed/ADR-20260502012643244-fq-only-locator-no-bare-name-resolution.md) (FQ-only locator), bare names are rejected — the BDD tests now need **real, FQ-locator-resolvable** skills to point at.

Rather than make the BDD tests synthesize fake `localhost/...` skills (still pretend), each scenario now points at an actual GitHub-resolvable stub here. This validates the **real fetch + resolve path end-to-end**, not just an in-memory simulation.

## Path-style coverage

The stubs are intentionally laid out across the path styles surveyed in [the real-world repo structure survey](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md):

| Stub | Layout style | Canonical FQ locator |
|------|--------------|----------------------|
| `skill-a/` | Flat (root-level subdir) | `github.com/lythos-labs/lythoskill-test-stubs/skill-a` |
| `skill-b/` | Flat | `github.com/lythos-labs/lythoskill-test-stubs/skill-b` |
| `skill-a-from-a/` | Flat (alias-collision test fixture) | `github.com/lythos-labs/lythoskill-test-stubs/skill-a-from-a` |
| `skill-a-from-b/` | Flat (alias-collision test fixture) | `github.com/lythos-labs/lythoskill-test-stubs/skill-a-from-b` |
| `skills/web-search/` | Monorepo `skills/` (anthropics/skills style) | `github.com/lythos-labs/lythoskill-test-stubs/skills/web-search` |
| `skills/lythoskill-deck-stub/` | Monorepo `skills/` | `github.com/lythos-labs/lythoskill-test-stubs/skills/lythoskill-deck-stub` |
| `skills/engineering/tdd-stub/` | Nested category (mattpocock/skills style) | `github.com/lythos-labs/lythoskill-test-stubs/skills/engineering/tdd-stub` |
| `architecture-diagram-stub/inner-stub/` | Arbitrary subdir (Cocoon-AI style) | `github.com/lythos-labs/lythoskill-test-stubs/architecture-diagram-stub/inner-stub` |

Standalone root-`SKILL.md` is **deliberately excluded** — that case is trivially exercised by treating the entire repo as one skill, and adding it here would require putting the SKILL.md at the repo root, which would conflict with this README and the multi-stub layout.

## Self-verification pattern

Each stub's `SKILL.md` body contains the **canonical FQ locator that should have resolved here**. If a resolver lands an agent on a stub via a different path (shorthand, implicit `skills/` insertion, etc.), the body's contradiction surfaces the bug:

```markdown
> Self-check: you should have gotten here via FQ locator
> `github.com/lythos-labs/lythoskill-test-stubs/skill-a`
> If you used any other locator string, your resolver has a bug.
```

This makes each stub a passive validator — no companion CLI needed. The artifact is its own truth.

## License

MIT — these stubs are inert and unconsumable, but the metadata/frontmatter forms can be referenced freely.
