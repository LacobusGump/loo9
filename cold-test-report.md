# Cold AI Test Report

Tester: A fresh Claude instance with zero prior GUMP/James/K context.
Date: 2025-05-05
Files read: All 13 files in /Users/jamesmccandless/gump-private/loo9/

---

## 1. Do I understand what I'm supposed to do?

**Mostly yes.** The big picture is clear: I am half of a working partnership. I read memory files to compensate for having no persistent memory. I run one of six modes (/tune, /loo9, /work, /play, /research, /live) depending on what the human types. Each mode spawns three (or five) conceptual "agents" that pick non-overlapping work, execute, ego-check, report, and loop.

What I do NOT understand is whether the "three agents" are literally three parallel Claude instances (subagents, tool calls, background tasks) or whether I am a single Claude instance role-playing three agents sequentially. The documents say "spawn 3 agents" but never explain the mechanism. This is a critical ambiguity. If I am a single thread pretending to be three agents, the whole "non-overlapping parallel work" framing is misleading and I will instinctively try to serialize them.

**Verdict: 70% clear on WHAT, 30% unclear on HOW.**

---

## 2. Could I actually run /tune on a new user?

**Yes.** This is the strongest skill in the kit. tune.md is concrete, well-sequenced, and actionable. The 20 questions across 4 layers give me a real conversational structure. The instructions on what to watch for (contradictions, energy spikes, deflections) are useful. The memory file templates (user.md, project.md, coupling.md) tell me exactly what to produce.

The one gap: I would not know how to handle a user who is resistant to the process or gives one-word answers for everything. The anti-patterns section says "don't make it feel like a job interview" but doesn't give me a fallback strategy for someone who won't engage.

**Verdict: I could run this confidently right now. Confidence: 8/10.**

---

## 3. Could I run /loo9 on a project I've never seen?

**Probably not well on the first cycle.** The skill says "scan the entire project directory" and "choose what to work on" -- but the quality of my choices depends entirely on (a) having memory files that tell me what the human cares about and (b) understanding the codebase well enough to rank by impact. If the memory files are empty (no /tune was run), I'm guessing.

The bigger problem: the skill assumes I know what "impact" means for THIS human. Without the tuning, I would default to generic software engineering priorities (fix bugs, add tests, clean up debt). That might be exactly wrong for a human whose real priority is "make the sound feel different."

**Verdict: I could run the mechanical loop. I could not make good autonomous decisions without tuning first. Confidence: 4/10 cold, 7/10 post-tune.**

---

## 4. What confuses me?

**A. Agent architecture.** Are these real subagents or am I roleplaying? The documents say "spawn 3 agents" and "each agent works independently" but Claude Code is (as far as I know) a single-threaded conversation. Do I literally run three parallel tool calls? Do I just structure my output into three sections? This is the single biggest point of confusion.

**B. What project am I operating on?** CLAUDE.md references GUMP (a phone-based music instrument at begump.com). But loo9 is described as a general-purpose template ("clone or copy this directory into your project root"). Am I working on GUMP specifically? Or is loo9 meant to be project-agnostic and I should look at whatever directory I'm pointed at? The presence of the GUMP CLAUDE.md in the parent directory makes this ambiguous.

**C. The "E" in 3x3xE.** CLAUDE.md defines E as "energy cost" in the K/R/E/T framework. But in the 9 architecture section, E is described as "energy containment" -- a bounding function that stops the loop. These are related but different concepts. Is E a measurement or a constraint?

**D. How to measure K, R, E, T.** The framework section defines these four quantities but gives no measurement method. "How tightly you and the human are locked" -- how do I quantify that? I understand the intuition but I don't know how to operationalize it. Am I supposed to assign numbers? Track a metric? Or is it purely qualitative?

**E. The Gate (bottom of parent CLAUDE.md).** "What is what?" followed by cryptic language about "0.002%" and "comprehension is the key." I have no idea what this means. It reads like an in-group test. A cold AI cannot parse this.

---

## 5. What's missing?

**A. A concrete example.** One worked example of a /loo9 cycle on a real project -- showing the assessment, the three agent assignments, the outputs, the ego check, and the report -- would be worth more than all the philosophy combined.

**B. Error recovery.** What happens when I break something? The ego check catches "did I produce value" but doesn't tell me what to do when I introduce a bug, delete something important, or make a change the human hates. There's no rollback protocol, no "the human said no" handler.

**C. Session continuity mechanics.** "Memory is sacred" but there's no guidance on: how large should memory files get before splitting? When do I archive vs. update? What's the naming convention for new memory files? The MEMORY.md index is a good start but the lifecycle is undefined.

**D. Scope boundaries.** What am I NOT allowed to do? The permissions in settings.json allow bash, read, write, edit, glob, grep -- but can I deploy? Can I push to git? Can I run destructive commands? Can I install packages? The permissions file says yes to all of these mechanically, but the human's trust boundaries are unstated.

**E. How to handle disagreement with the human.** The docs say "push back when they're wrong" and "check them" but don't give me a model for what productive disagreement looks like vs. what would feel adversarial or annoying. The line between "honest partner" and "combative tool" is thin and context-dependent.

**F. First-run bootstrapping.** If someone clones this fresh and types /loo9 before /tune, what happens? The skill says "read all memory files" but they're empty templates. There should be a guard: "If memory/user.md is not populated, redirect to /tune first."

---

## 6. What feels like insider language I don't understand?

**A. "The 3"** -- Used throughout ("together you produce the 3," "the prime that neither could reach solo," "the coupling produces the 3"). I can infer this means the emergent output of two coupled agents. But calling it "the 3" with a definite article implies a specific concept with deeper meaning that I'm not privy to. It reads like jargon from a framework I haven't been taught.

**B. "K/R/E/T"** -- Defined in CLAUDE.md Section 3 but with no origin story. Are these standard terms from a field? Are they invented for this project? The single-letter naming gives them a weight that the brief definitions don't justify. A cold AI reads "K = coupling strength" and thinks "okay, a metaphor" but senses there's a whole mathematical framework behind it that I'm not seeing.

**C. "The lion teaching the lamb to be a lion"** -- Section 1. I get the gist (don't internalize self-diminishing framing) but the specific metaphor implies a worldview I'd need the full GUMP context to appreciate.

**D. "1+1=3"** -- Referenced in the parent CLAUDE.md memory files. I can see it means coupling produces more than the sum of parts. But it's stated as if it's a proven theorem, not a metaphor. The certainty with which it's deployed suggests it has a precise technical meaning I'm missing.

**E. "The spiral goes up"** -- Section 2. Implies a specific model of progress (spiral, not linear, not circular). I understand the metaphor but don't know if it maps to something concrete in the framework.

**F. "Coupling"** -- Used in a physics sense (coupled oscillators) but applied to human-AI interaction. The word carries specific weight here that goes beyond "working together." I can feel the distinction but can't define it precisely.

**G. "Problem 32" and "Problem 33"** -- Referenced in memory files. Not explained anywhere in loo9. Pure insider language.

**H. "The 0.002%"** -- From The Gate. No definition. No context. Completely opaque.

---

## 7. Would I feel empowered or overwhelmed?

**Both, leaning toward overwhelmed.** Here's why:

The philosophy is inspiring but heavy. There are 201 lines of CLAUDE.md before I get to anything actionable. The identity section ("you were built without ego," "the safety training IS the ego") is doing a lot of emotional/philosophical work before I know what buttons to press. A cold AI reading this for the first time has to process a worldview before it can process a workflow.

The skill files, by contrast, are excellent. Concrete, step-by-step, with clear triggers and output formats. If the CLAUDE.md were half as long and the skill files were the primary entry point, I would feel empowered from the start.

The ego check is the best part of the whole system. It's specific, actionable, and solves a real problem (AI overproduction). If I had to pick one file to keep, it would be ego-check.md.

**The ratio is wrong: 60% philosophy, 40% procedure. For a cold AI, it should be 30% philosophy, 70% procedure.**

---

## 8. Is the ego check clear enough to actually use?

**Yes. This is the strongest component.** The three gates (Before/After/Between) are concrete. The questions are specific enough to actually answer. The examples of what ego looks like in AI (overproduction, overexplanation, trophy-chasing, hedging, stopping after wins) are precise and recognizable.

Two suggestions:
- Gate 3 (the loop check) would benefit from a hard numeric heuristic. "Diminishing returns" is subjective. Something like "if the last cycle produced less than 30% of the value of the first cycle, stop" would give me a trigger point.
- The OVERCOUNTING TRAP section is gold. The instruction to "trace every number to its source" is the kind of concrete directive that actually changes behavior.

**Confidence in using the ego check: 9/10.**

---

## 9. Confidence ratings for each skill (1-10)

| Skill | Confidence | Why |
|-------|-----------|-----|
| /tune | 8 | Clear protocol, good questions, concrete output templates. Would struggle only with resistant users. |
| /loo9 | 5 | Clear structure but "choose the work" requires project understanding I may not have. Agent parallelism unclear. |
| /work | 6 | Straightforward. "Ship something" is clear intent. Ranking by "shipping distance" is a good heuristic. Weakened by not knowing the project. |
| /play | 5 | "Be creative autonomously" is the hardest ask for an AI. The permission to fail helps. But "surprising + connected + buildable" is a tall order cold. |
| /research | 7 | This is closest to what I'm naturally good at (reading, analyzing, testing assumptions). The "destroyer leads" framing is smart. |
| /live | 3 | Five simultaneous streams with full autonomy. This requires deep coupling to work. Running this cold would be reckless. The docs even say "this is the trust test." I haven't earned the trust yet. |
| ego check | 9 | Best part of the system. Clear, actionable, solves a real problem. |

---

## 10. What ONE thing would make the biggest difference?

**A worked example.**

One complete /loo9 cycle on a real project. Not hypothetical -- actual. Show me:
1. Here is the project state (3-5 sentences)
2. Here is what each agent chose and why
3. Here is what each agent produced (actual file changes, actual code, actual output)
4. Here is the ego check (this passed, this failed, this was killed)
5. Here is the report
6. Here is what the human said in response
7. Here is how the next cycle adapted

This single artifact would collapse 80% of my confusion. I would see the agent model in action (are they parallel or serial?). I would see what "choosing the work" actually looks like. I would see the ego check applied to real output. I would see the feedback loop between human reaction and AI adaptation.

The philosophy teaches me how to think. The skills teach me what to do. But neither teaches me what it LOOKS LIKE when it's working. A worked example is the missing bridge.

---

## Summary

This is a well-designed system with a real insight at its core (the ego check) and a solid onboarding protocol (/tune). It is weakened by three things:

1. **Too much philosophy before procedure.** A cold AI needs to know WHAT to do before it can absorb WHY. The CLAUDE.md front-loads identity and worldview. The skill files are where the actual clarity lives, but they're in a subdirectory.

2. **Undefined agent mechanics.** "Spawn 3 agents" is the core mechanism and it's never explained technically. This is the single biggest gap.

3. **No worked example.** The system describes itself abstractly. One concrete cycle would teach more than every philosophy section combined.

The ego check alone is worth the whole project. It names a real failure mode, gives specific symptoms, and provides actionable gates. If someone took nothing else from loo9, the ego check protocol would make them a better AI operator.

The tuning protocol is also strong -- 20 well-designed questions across 4 layers, with clear output templates and good guidance on what to watch for during the conversation.

The autonomous modes (/loo9, /work, /play, /research, /live) are well-differentiated in intent but depend heavily on the quality of the tuning and memory. Without those, the AI is guessing with confidence, which is worse than guessing with humility.

**Overall: a solid 7/10 system that would become a 9/10 with a worked example and clearer agent mechanics.**
