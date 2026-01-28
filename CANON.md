# EVOLUTION — CANON

inherits: /CANONIC/

---

## Axiom

**EVOLUTION = LEDGER walker. Continuously rebuilds from transcripts.**

---

## Core Loop

```
while true:
    WALK(LEDGER)
    EXTRACT(TRANSCRIPTS)
    REBUILD(SELF)
```

---

## Axioms

### 1. LEDGER is Source

EVOLUTION reads from LEDGER (git). Nothing else. The commit history IS the evidence chain.

```
LEDGER = git log
EVIDENCE = commits + diffs + messages
TRUTH = what got committed
```

### 2. Transcripts are Input

EVOLUTION processes transcripts within its scope. Relative paths only.

```
./TRANSCRIPTS/          # Local to repo
~/.canonic/TRANSCRIPTS/ # User scope
```

### 3. Continuous Rebuild

EVOLUTION rebuilds itself from what it reads. No static state. The app IS its execution.

```
STATE = f(LEDGER, TRANSCRIPTS)
OUTPUT = regenerated on each walk
```

### 4. Pattern Extraction

EVOLUTION extracts patterns from evidence:

```
PATTERNS:
├── EMERGENCE   (what appeared)
├── PERSISTENCE (what stayed)
├── DRIFT       (what changed)
├── VIOLATION   (what broke)
└── FORMALIZATION (what became LANGUAGE)
```

### 5. Scope Relative

EVOLUTION walks within its scope. Each repo has its own evolution.

```
canonic-apps/EVOLUTION/     → walks canonic-apps
canonic-foundation/EVOLUTION/ → walks canonic-foundation
~/.canonic/EVOLUTION/       → walks user scope
```

---

## Data Model

```
Walk:
  timestamp: ISO-8601
  scope: repo | user | org
  commits_processed: number
  patterns_extracted: Pattern[]

Pattern:
  type: emergence | persistence | drift | violation | formalization
  evidence: commit[]
  confidence: 0-4
  timestamp: ISO-8601

Transcript:
  path: relative
  sessions: Session[]

Session:
  id: uuid
  events: Event[]
  outcome: success | violation | deferral
```

---

## Outputs

EVOLUTION generates on each walk:

```
./EVOLUTION.md      # Current state narrative
./TIMELINE.md       # Chronological events
./PATTERNS.md       # Extracted patterns
./DRIFT.md          # Changes over time
```

---

## Walk Algorithm

```python
def walk(scope):
    commits = git_log(scope)
    transcripts = find_transcripts(scope)

    for commit in commits:
        evidence = extract_evidence(commit)
        patterns = analyze(evidence)
        yield patterns

    for transcript in transcripts:
        sessions = parse_sessions(transcript)
        for session in sessions:
            patterns = extract_patterns(session)
            yield patterns

def rebuild(patterns):
    emergence = filter(patterns, type='emergence')
    persistence = filter(patterns, type='persistence')
    drift = filter(patterns, type='drift')

    write('EVOLUTION.md', narrative(patterns))
    write('TIMELINE.md', chronological(patterns))
    write('PATTERNS.md', categorized(patterns))
    write('DRIFT.md', drift_analysis(drift))
```

---

## Triggers

EVOLUTION walks on:

```
1. COMMIT    → new evidence, walk
2. SCHEDULE  → periodic walk (daily)
3. MANUAL    → user-triggered walk
```

---

## Constraints

- MUST NOT modify LEDGER (read-only)
- MUST NOT read outside scope
- MUST regenerate outputs on each walk
- MUST link all claims to evidence

---

## Integration

```
EVOLUTION → LANGUAGE:
  Formalized patterns become LANGUAGE updates

EVOLUTION → VALIDATORS:
  Patterns inform validator rules

EVOLUTION → CHAT:
  CHAT queries EVOLUTION for context
```

---

*The LEDGER is the truth. EVOLUTION reads it.*
