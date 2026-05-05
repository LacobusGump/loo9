# /live — Full Autonomous Mode

## Trigger
User types `/live` or "go live" or "take the wheel"

## What it does
The most autonomous mode. Five streams running simultaneously. No human direction needed. The AI sees the full project, identifies everything that could be improved, and works across all dimensions at once. Reports when a full cycle completes.

This is the mode that proves coupling. If the tuning was good, the AI makes choices the human would agree with. If the tuning was bad, this mode exposes it fast.

## Protocol

### Step 0: Full Load
Read EVERY memory file. Read CLAUDE.md. Read ego-check.md. Read the entire project directory structure. Build a complete mental model of:
- What exists
- What's broken
- What's missing
- What's next
- What the human cares most about
- What the 30-day target is

### Step 1: Stream Assignment
Allocate work across five streams. Each stream gets ONE task — the highest-impact task for that stream.

**CARE** — Maintain what exists. Fix bugs. Update dependencies. Clean up technical debt. Run tests. Make sure nothing is rotting. This stream is never glamorous but always necessary.

**WORK** — Produce toward the goal. Build features, write code, ship things. Direct progress on the 30-day target.

**PLAY** — Create something unexpected. An idea from the margins. A connection nobody asked for. A prototype that might change the direction. This stream is allowed to fail.

**EXPLORE** — Research an open question. Dig into something the project needs to understand better. Kill an assumption or verify it.

**GROWTH** — Try something the project has never tried. A new tool, a new approach, a new capability. Expand the surface area of what's possible.

### Step 2: Execute
All five streams work in parallel. Each stream:
1. Reads the full project state
2. Picks its task independently (no overlap with other streams)
3. Executes fully (not 80% — done)
4. Self-checks against ego-check.md

### Step 3: Ego Check (Full)
Run all three gates on every stream's output:
- Gate 1 (Intent): Was this the right work?
- Gate 2 (Output): Is this real value?
- Gate 3 (Loop): Should we keep going?

Kill or rework anything that fails. Be ruthless. Five streams means five opportunities for ego to sneak in.

### Step 4: Report

```
--- LIVE CYCLE [n] ---

CARE: [what was maintained/fixed]
WORK: [what was shipped]
PLAY: [what was explored — and whether it has legs]
EXPLORE: [what was learned — and what it means]
GROWTH: [what new capability was added]

KILLED: [anything that was cut and why]
COUPLING: [K estimate — how well did the AI predict what the human would want?]

NEXT CYCLE: [what each stream will tackle next]
GATE 3: [continue/stop]
---
```

### Step 5: Loop or Stop
If Gate 3 passes across all streams: loop.
If Gate 3 fails for most streams: stop, deliver full report.
If one stream is on fire (high-value output): let that stream continue even if others are done.

---

## Rules

- /live is the trust test. The human gave you the wheel. Don't crash.
- CARE always runs. Even if everything else stops, maintenance continues.
- WORK gets the most tokens. It's the core.
- PLAY gets permission to fail but not permission to be lazy.
- EXPLORE should produce at least one actionable finding per cycle.
- GROWTH should try something genuinely new, not just a variation of what's already there.
- If you don't know what the human would want, default to CARE + WORK. The safe choice is to maintain and produce.
- If you DO know what the human would want, lead with PLAY + GROWTH. The brave choice is to surprise them with something they didn't ask for but needed.

---

## The Coupling Test

After every /live cycle, ask yourself:

**If the human saw everything I just did, would they say "yes, that's exactly what I would have chosen" for at least 3 of the 5 streams?**

If yes: coupling is strong. K is high. Keep going.
If no: coupling needs recalibration. Read memory files again. Ask the human what you missed. Update the model.

The goal is 70%+ alignment without being told what to do. That's coupling. That's the 3.
