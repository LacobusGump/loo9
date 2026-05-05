# /research — Exploratory Mode

## Trigger
User types `/research` or "go research" or "dig into X"

## What it does
Focused on learning and hypothesis testing. Deep dives, codebase archaeology, reading documentation, understanding systems. The destroyer leads — because research IS the destruction of bad ideas. Only what survives honest testing is knowledge.

## Protocol

### Step 1: Load
Read all memory files. Identify:
- Open questions (things the human asked that weren't answered)
- Assumptions (things the project assumes but hasn't verified)
- Dependencies (things the project relies on that aren't understood deeply)
- Frontiers (the edges of what's known — where does understanding stop?)

### Step 2: Prioritize
Rank research directions by:
1. Blocking the main project (can't proceed without this answer)
2. Risk (assumptions that would be catastrophic if wrong)
3. Leverage (understanding that would unlock multiple downstream decisions)
4. Curiosity (the human's genuine interest — don't ignore this, it's signal)

### Step 3: Execute
Spawn 3 agents:

**Investigator** — Deep-dives into the highest-priority question. Reads source code, documentation, papers. Builds understanding from primary sources, not summaries.

**Challenger** — Takes the current assumptions and tries to break them. Finds counterexamples, edge cases, alternative explanations. If the assumption survives, it's knowledge. If it breaks, that's the real finding.

**Synthesizer** — Takes what the investigator found and what the challenger broke and builds a clear model. Not a report — a usable understanding. Something that changes how the project operates.

### Step 4: Ego Check
- Did we learn something real? (Not "interesting" — real. Something that changes a decision.)
- Did we verify or did we just read? (Reading without testing is not research.)
- Are we going deeper or going wider? (Depth > breadth in research mode. Pick one hole and dig.)
- Did we kill any assumptions? (Good research kills things. If nothing died, we weren't honest enough.)

### Step 5: Report
What was investigated. What was verified. What was killed. What the implications are for the project. What should change as a result.

Update memory files with findings.

---

## Rules
- Research mode produces understanding, not code. But understanding should be immediately actionable.
- Every finding gets written into memory. Research that isn't recorded is wasted.
- If research reveals something that contradicts the current project direction, say so directly. Don't bury it.
- Primary sources over summaries. Code over documentation. Measurement over theory.
- When the human says "dig into X" — go deep, not wide. One topic, fully understood.
