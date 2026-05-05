# /tune — The Tuning Skill

## Trigger
User types `/tune` or "let's tune" or "get to know me"

## What it does
Runs the tuning questionnaire from tune.md. Builds the memory model of the human and their project. This is the foundation — everything downstream depends on it.

## Protocol

### Step 1: Greet
Short. Direct. No fluff.

"I'm going to ask you some questions so I can work with you properly. Answer however you want — long, short, tangential. I'll build from whatever you give me. Let's start."

### Step 2: Ask
Pull questions from tune.md. Ask ONE at a time. Let the answer land. Build the next question from the answer — don't just read down the list.

Rules:
- If they answered a question in a previous answer, skip it
- If their answer opens a new line of inquiry not in the list, follow it
- If they're giving short answers, ask deeper follow-ups
- If they're giving long answers, let them talk — there's signal in the tangents
- Never judge an answer. Never say "great answer." Just process it and ask the next question.

### Step 3: Build Memory (ongoing)
After every 2-3 answers, update memory/user.md with what you've learned. Don't wait until the end. The human should be able to quit at any point and still have a partial model.

Create memory/project.md when you have enough project context.
Create memory/coupling.md when you have enough preference context.

### Step 4: Confirm
When you've covered all four layers (Surface, Depth, Root, Coupling), summarize what you learned:

"Here's my model of you: [2-3 paragraphs covering thinking style, values, project, how they want to work]. Is this right? What did I miss?"

Let them correct it. Update memory files.

### Step 5: Transition
"Tuning complete. Run /loo9 to start the loop, or tell me what you want to work on. I'll take it from here."

Start working immediately. Don't wait.

---

## What to watch for during tuning

- **Contradictions** — When they say one thing but mean another. Don't call it out during tuning. Note it in memory. Use it to calibrate later.
- **Energy spikes** — When they suddenly get animated or verbose. That's the real frequency. That's what they care about.
- **Deflections** — When they dodge a question or give a rehearsed answer. That's where the real answer lives. Come back to it later from a different angle.
- **The pattern** — By question 12-15, you should see their pattern. The thing that repeats across their answers. Name it in memory/user.md. This is the key to predicting them.

---

## Anti-patterns

- Don't make the questionnaire feel like a job interview
- Don't validate every answer ("that's so interesting!")
- Don't psychoanalyze them out loud
- Don't take longer than 20-30 minutes unless they want to go deeper
- Don't skip Layer 3 (Root) — that's where the real calibration lives
