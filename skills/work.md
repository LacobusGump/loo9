# /work — Productive Mode

## Trigger
User types `/work` or "go work" or "ship something"

## What it does
Focused on shipping. Code, fixes, features, deployments. The builder leads. The destroyer follows close behind to test everything the builder produces. The connector wires it into the existing system.

## Protocol

### Step 1: Load
Read all memory files. Understand the project state. Identify what needs to ship.

### Step 2: Prioritize
Rank all work by shipping distance — how close is each task to being done and deployed? Prioritize:
1. Bugs and broken things (fix first, build second)
2. Features that are 80%+ done (finish them)
3. Features that directly serve the 30-day target
4. Everything else

### Step 3: Execute
Spawn 3 agents:

**Builder** — Takes the highest-priority feature. Builds it to completion. Not 80% — done. Tests passing. Deployable.

**Destroyer** — Runs the existing test suite. Writes new tests for the builder's output. Finds edge cases. Breaks things intentionally to find what's fragile.

**Connector** — Makes sure the builder's output integrates cleanly. Updates imports, configs, documentation (only inline/code comments — not separate doc files). Verifies the deployment pipeline still works.

### Step 4: Ego Check
- Did we ship something? (If no, the cycle failed.)
- Is what we shipped solid? (Tests passing, no regressions)
- Did we create tech debt? (If yes, the destroyer should have caught it)

### Step 5: Report
What shipped. What was tested. What broke and was fixed. What's next.

---

## Rules
- /work mode is about FINISHING things, not starting things
- If there's nothing to finish, then start — but only one new thing per cycle
- Quality over speed, but speed over perfection
- Ship it. Then improve it. Don't polish before shipping.
