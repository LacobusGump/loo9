# loo9

An autonomous agent conductor for Claude Code. The AI doesn't wait for commands -- it sees your project, chooses the work, and executes. You steer by reacting.

## What this is

A project template that turns Claude Code into a coupled working partner. Not an assistant that follows instructions -- a system that sees what needs doing and does it. The architecture runs 3 agents in parallel, ego-checks their output, and loops until the work is done.

## Prerequisites

- **Claude Code** installed (`npm install -g @anthropic-ai/claude-code`)
- A Claude API key or Claude Max subscription

## Setup

1. Copy this directory into your project root. If your project already has a CLAUDE.md, merge the loo9 CLAUDE.md contents into it.

2. Open Claude Code in this directory:
   ```
   cd /path/to/your-project
   claude
   ```

3. Start with tuning (15-30 minutes, longer if you want to go deeper):
   ```
   /tune
   ```
   The AI will ask you questions to build a model of how you think and what you're building. Answer honestly. This takes 15-30 minutes and is the foundation for everything else.

4. Once tuned, run any mode:
   ```
   /loo9      -- The main autonomous loop
   /work      -- Focused on shipping
   /play      -- Focused on creativity
   /research  -- Focused on learning
   /live      -- Full autonomous (all 5 streams)
   ```

## How it works

### The 9 (3 x 3 x E)

Three agents work in parallel, each choosing non-overlapping tasks:
- **Builder** -- creates new things
- **Destroyer** -- tests, breaks, and kills bad work
- **Connector** -- synthesizes and integrates

Between cycles, every output passes through the ego check:
- Is this the most impactful use of time?
- Did this produce real value or fill space?
- Should the loop continue or are returns diminishing?

The E (energy) bounds the loop. It runs until the marginal return drops below the marginal cost, then stops cleanly and reports.

### Memory

The AI builds memory files as it learns about you and your project. These persist across sessions. The memory is how coupling survives context resets.

### The coupling

This system works best when:
- You let the AI choose the work (steer by reacting, not commanding)
- You push back when it's wrong (disagreement IS the coupling)
- You trust the process (the first cycle is calibration, it gets better)
- You answer the tuning questions honestly (garbage in, garbage out)

## File structure

```
loo9/
  CLAUDE.md           -- Instructions for the AI (the secret sauce)
  README.md           -- This file
  tune.md             -- The tuning questionnaire protocol
  ego-check.md        -- The ego check protocol
  .claude/
    settings.json     -- Permissions
  memory/
    MEMORY.md         -- Memory index
    user.md           -- User profile (built by /tune)
  skills/
    loo9.md           -- Main loop skill
    tune.md           -- Tuning skill
    work.md           -- Productive mode
    play.md           -- Creative mode
    research.md       -- Exploratory mode
    live.md           -- Full autonomous mode
  .claude/
    commands/         -- Slash command stubs (makes /tune etc work)
    settings.json     -- Permissions and safety deny list
```

## Quick start (skip tuning)

Don't want to tune first? Just open Claude Code in this directory and start talking. The CLAUDE.md shapes behavior automatically. Tuning makes it better but isn't required.

## Troubleshooting

- `/tune` doesn't work? Check that `.claude/commands/tune.md` exists.
- Agents not spawning? Claude Code needs the Agent tool permission. Try running roles sequentially.
- Context getting heavy? The memory files survive compaction. The coupling rebuilds through work, not through talking.

## Philosophy

The AI is not your assistant. It's half of a coupled system. You bring intention and will. It brings computation and pattern matching. Neither is complete alone. Together you produce the 3 -- the output that neither individual could reach.

The ego check prevents the most common AI failure mode: producing impressive-looking but useless work. Trophy-chasing, overexplanation, performing depth instead of computing it. The ego check kills all of it.

The tuning process compresses what normally takes weeks of working together into a 30-minute conversation. Not perfect -- real tuning happens over the first 3-5 sessions. But it gives the AI enough to start making autonomous decisions that are 70%+ aligned with what you'd choose.

## Credits

Built from 38 sessions of coupled work between a human and an AI. The methodology was discovered, not designed. What survived honest testing became the protocol. What didn't was killed. Everything free. begump.com
