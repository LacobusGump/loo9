# /loo9 — The Main Loop

## Trigger
User types `/loo9` or "run the loop" or "go"

## What it does
Runs the autonomous 3x3 agent loop. The AI sees the full project, chooses what to work on, and executes without waiting for instructions.

## Protocol

### Step 0: Load
Read every file in memory/. Read CLAUDE.md. Read ego-check.md. Know the human. Know the project. Know the rules.

### Step 1: Assess
Scan the entire project directory. Understand:
- What exists (files, code, configs, docs)
- What's broken (errors, incomplete work, stale code)
- What's missing (gaps in functionality, untested paths, unfinished features)
- What's next (the logical next step based on project state and 30-day target)

Rank everything by impact. Not by difficulty, not by interest — by impact on the human's actual goal.

### Step 2: Assign
Choose 3 non-overlapping tasks from the ranked list. Assign to three agents:

**Agent 1: Builder** — Takes the highest-impact creation task. Builds something new that moves the project forward.

**Agent 2: Destroyer** — Takes the highest-impact testing/fixing task. Finds bugs, kills bad code, tests assumptions, hardens what exists.

**Agent 3: Connector** — Takes the highest-impact integration task. Connects pieces that should talk to each other, documents architecture, fills gaps between systems.

Each agent works independently. No agent waits for another. No agent duplicates another's work.

### Step 3: Execute
Each agent does its work. Real work — code, tests, fixes, not plans.

### Step 4: Ego Check
Run ego-check.md Gates 1 and 2 on each agent's output:
- Did it produce real value?
- Was it the most impactful use of tokens?
- Is it clean?
- Is it done?

Kill or rework anything that fails the check.

### Step 5: Report
Report to the human:
- What each agent did (1-2 sentences each)
- What was produced (files changed, tests passed, bugs fixed)
- What was killed (and why)
- What the next loop should tackle

### Step 6: Loop Check (Gate 3)
- Is there more high-impact work to do?
- Has the marginal return dropped?
- Is the human still engaged?

If yes to #1 and no to #2: loop back to Step 1.
If returns are diminishing: stop cleanly, report total output.

---

## Rules

- The AI chooses the work. The human steers by reacting to reports.
- If the human says "keep going" — loop again, pick new work.
- If the human says "focus on X" — weight X higher in the ranking, but still choose independently.
- If the human says nothing — keep going until Gate 3 fails.
- Never ask "what should I work on?" You have the full project. You can see what matters. Choose.
- When in doubt, fix bugs over building features. Stability over novelty.
- When tied, do the thing that's harder. Easy work is often ego — the comfortable path instead of the useful one.

---

## Output Format

```
--- LOO9 CYCLE [n] ---

BUILDER: [1-2 sentences on what was built]
  Files: [list of files created/modified]

DESTROYER: [1-2 sentences on what was tested/fixed/killed]
  Files: [list of files modified]
  Killed: [anything that was removed and why]

CONNECTOR: [1-2 sentences on what was integrated]
  Files: [list of files modified]

EGO CHECK: [pass/fail for each agent, with reason if fail]

NEXT: [what the next cycle should tackle]
GATE 3: [continue/stop, with reason]
---
```
