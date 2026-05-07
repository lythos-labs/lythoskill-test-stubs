# lythos-labs/lythoskill-test-stubs

> Empty-content stub skills for `lythos-labs/lythoskill` BDD test fixtures, **doubling as a field survey of skill ecosystem layout patterns**.
> Not consumable. Don't `deck add` these except for testing.

## Why this repo exists

### Primary: BDD fixture

The lythoskill BDD scenarios used to declare bare skill names (`skill-a`, `skill-b`, etc.) that were resolved via fallback strategies in `findSource`. After [ADR-20260502012643244](https://github.com/lythos-labs/lythoskill/blob/main/cortex/adr/01-proposed/ADR-20260502012643244-fq-only-locator-no-bare-name-resolution.md) (FQ-only locator), bare names are rejected — the BDD tests need **real, FQ-locator-resolvable** skills to point at.

Rather than synthesize fake `localhost/...` skills (still pretend), each scenario points at an actual GitHub-resolvable stub here. This validates the **real fetch + resolve path end-to-end**, not just an in-memory simulation.

### Secondary: ecosystem field survey

This repo is also a **layout atlas** for the skill ecosystem. Each stub demonstrates a distinct path-style observed in the wild (per [the real-world repo structure survey](https://github.com/lythos-labs/lythoskill/blob/main/cortex/wiki/03-lessons/2026-05-07-real-world-skill-repo-structure-survey.md)) and links to real community skills that share its layout. As of 2026-05-07, four layout families are covered.

This is **not an attempt to be a registry** (that's [agentskills.io](https://agentskills.io)'s job) — it's a date-stamped field record that any resolver can verify against. If a new layout style emerges in the wild, a new stub here can lock down "FQ resolvers should also handle this shape" before it bites real consumers.

## Path-style coverage

The stubs are intentionally laid out across the path styles surveyed:

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

Standalone root-`SKILL.md` is **deliberately excluded** — that case is trivially exercised by treating the entire repo as one skill, and adding it here would conflict with this README + the multi-stub layout.

## Self-verification pattern

Each stub's `SKILL.md` body contains the **canonical FQ locator that should have resolved here** plus negative cases ("if you arrived via X, your resolver has a bug"). The artifact is its own validator — no companion CLI needed:

```markdown
> Self-check: you should have gotten here via FQ locator
> `github.com/lythos-labs/lythoskill-test-stubs/skill-a`
> If you used any other locator string, your resolver has a bug.
```

Each stub also includes a **`## Real-world peers (as of 2026-05-07)` section** linking to community skills that share the same layout — turning each stub into an evergreen reference card for "what real-world repos look like this".

## For ecosystem contributors

If you maintain a skill repo with a layout NOT covered here, please consider opening a PR adding a stub for your shape. The criteria:

- Distinct from existing 4 layout families (flat / monorepo `skills/` / nested category / arbitrary subdir)
- Resolvable by FQ locator
- Self-validating body (canonical FQ + negative cases)
- Real-world peer references with date stamps

The goal is to keep this repo's stubs as a living taxonomy of real-world skill layouts.

## License

MIT. The stubs are inert and unconsumable, but the metadata/frontmatter forms can be referenced freely.
