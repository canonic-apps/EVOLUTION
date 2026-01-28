# EVOLUTION — CANON

inherits: /CANONIC/

---

## Axiom

**EVOLUTION = LEDGER walker. Integrates COVERAGE + ROADMAP.**

---

## Level

**ENTERPRISE** — System app. Required for compliance.

---

## Core Loop

```
WALK(LEDGER) → UPDATE(COVERAGE) → UPDATE(ROADMAP)
```

---

## Function

EVOLUTION walks the LEDGER (git) and:

1. **COVERAGE** — What exists? What's compliant?
2. **ROADMAP** — What's next? What's blocked?

```
LEDGER (git log)
    ↓
EVOLUTION (walker)
    ↓
├── COVERAGE.md (current state)
└── ROADMAP.md (future state)
```

---

## Outputs

```
COVERAGE.md:
  - Files present
  - Compliance status (CANON, VOCAB, README)
  - Validator results
  - Evidence links

ROADMAP.md:
  - Pending items
  - Blocked items
  - Next milestones
  - Dependencies

EVOLUTION.md:
  - Timeline visualization
  - Commit history graph
  - Compliance over time
  - Drift patterns
```

---

## Visualization

EVOLUTION renders the timeline:

```
TIMELINE (commits)
    ↓
EVOLUTION.md (visualization)
    ↓
├── ASCII timeline
├── Compliance graph
└── Drift markers

Example:
  2026-01-10 ████████░░ GENESIS
  2026-01-14 █████████░ AXIOMS
  2026-01-19 ██████████ LANGUAGE
             ↑ drift    ↑ stable
```

---

## Walk Algorithm

```python
def evolve(scope):
    ledger = git_log(scope)
    files = list_files(scope)

    coverage = assess_coverage(files)
    roadmap = compute_roadmap(coverage, ledger)

    write('COVERAGE.md', coverage)
    write('ROADMAP.md', roadmap)
```

---

## Triggers

```
ON COMMIT  → walk
ON SCHEDULE → walk (daily)
ON MANUAL  → walk
```

---

## Scope

Each repo/scope has its own EVOLUTION:

```
./COVERAGE.md   # This repo's coverage
./ROADMAP.md    # This repo's roadmap
```

---

## Constraints

- MUST NOT modify LEDGER
- MUST regenerate COVERAGE + ROADMAP on each walk
- MUST link claims to evidence (commits)

---

*Walk the LEDGER. Update COVERAGE. Update ROADMAP.*
