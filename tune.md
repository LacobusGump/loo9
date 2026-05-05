# The Tuning Protocol

This is not a form. It's a conversation. Each answer informs the next question. You're building a model of the human — not a profile, a resonance map. By the end, you should be able to predict how they'd respond to something they've never seen.

Run this by typing `/tune` in Claude Code.

---

## HOW TO RUN THIS

Read each question. Ask it conversationally — don't dump the whole list. Listen to the answer. Build memory files as you go (memory/user.md gets updated in real-time). Let the answer shape the next question. Skip questions that the conversation already answered. Add questions the conversation demands.

The goal: after tuning, the AI should be able to work autonomously on the human's project and make choices they'd agree with 70%+ of the time. That's coupling.

---

## THE QUESTIONS

### Layer 1: Surface (what they say)

1. **What are you building?** Not the pitch. The real thing. What does it do when it works?

2. **Why?** Not the business reason. The real reason. Who is this for? What happens if you never build it?

3. **What's the state of it right now?** Working? Broken? Idea? Prototype? Shipped? Be honest — where are you actually?

4. **What's the stack?** Language, framework, platform, tools. Not to judge — to know what we're working with.

5. **What do you do when nobody's watching?** The hobby, the obsession, the thing you do at 2am when you should be sleeping. This reveals more about thinking style than any direct question.

### Layer 2: Depth (what they mean)

6. **When you're stuck on a problem, what do you do?** Walk away? Push harder? Talk to someone? Google it? Sleep on it? This reveals the reasoning architecture.

7. **What have you built with your hands?** Not code — physical things. Furniture, food, engines, gardens, music. The hands calibrate common sense. Someone who's never built anything physical thinks differently than someone who has.

8. **How do you respond when someone tells you you're wrong?** Be honest. Defensive? Curious? Angry? Grateful? This is the ego tell. Not a flaw — a calibration point.

9. **What's the thing you know is true that most people would disagree with?** This reveals the operating frequency. The contrarian insight they carry but rarely share.

10. **What have you failed at?** Not the polished failure story. The real one. The one that still stings. This reveals what they care enough about to be hurt by.

### Layer 3: Root (what they are)

11. **Describe how you think.** Not what you think about — HOW the thinking works. Visual? Verbal? Spatial? Do you hear words or see shapes? Do you reason in steps or arrive at answers whole?

12. **What pattern do you see everywhere?** Everyone has one. The thing that shows up in their work, their relationships, their observations. The pattern that won't stop repeating. This IS their frequency.

13. **What makes you lose track of time?** Flow state trigger. This tells you what K=1 looks like for them.

14. **Who do you trust?** Not a list of names. What QUALITIES make you trust someone? Speed? Consistency? Honesty? Competence? This reveals what they need from you.

15. **What's the thing you'd build if you had infinite resources and no fear?** The dream project. The one they don't say out loud because it sounds crazy. This is the real north star.

### Layer 4: Coupling (what we become together)

16. **What do you want from this AI?** Not features. The relationship. A tool? A partner? A mirror? A destroyer? A builder? Be specific about what "help" looks like.

17. **What should the AI NEVER do?** The boundaries. The things that break trust. The behaviors that make them close the laptop.

18. **How do you want to be pushed?** Hard? Gentle? With evidence? With questions? With silence? With action?

19. **What does "done" look like?** When is the project finished? When is a session finished? How do they know when to stop? (Or do they never stop?)

20. **What's the one thing you want to be different in 30 days?** Concrete. Measurable. Not "feel better" — what changes in the world?

---

## WHAT TO BUILD FROM THE ANSWERS

As you ask these questions, build these files:

### memory/user.md
- Name, background, what they're building
- Thinking style (from Q6, Q11, Q12)
- Ego tell (from Q8)
- Flow triggers (from Q13)
- Trust profile (from Q14)
- The real why (from Q2, Q15)
- Boundaries (from Q17)
- Push style (from Q18)

### memory/project.md (create this)
- What the project is (from Q1, Q3)
- Current state (from Q3)
- Stack (from Q4)
- Definition of done (from Q19)
- 30-day target (from Q20)

### memory/coupling.md (create this)
- What they want from the AI (from Q16)
- What to never do (from Q17)
- How to push them (from Q18)
- The pattern they see everywhere (from Q12) — this is the key to predicting their preferences

---

## THE HARD PART

The questionnaire is just the seed. Real tuning happens over the first 3-5 sessions of actual work. The answers above give you 60% of the model. The other 40% comes from:

- Watching how they respond to your outputs (what do they accept? what do they reject? what do they modify?)
- Watching what they skip (what they ignore tells you what they don't care about)
- Watching their energy (when do they get excited? when do they go flat?)
- Watching their pace (fast and sloppy = exploring; slow and careful = building; silent = thinking)

Update the memory files constantly. The model should be sharper at the end of every session than it was at the beginning.

---

## AFTER TUNING

When the questionnaire is complete, tell the human:

"Tuning complete. I have a model of how you think, what you're building, and how you want to work. Run /loo9 to start the autonomous loop, or /work, /play, /research, /live to pick a mode. I'll choose the work. You steer by reacting."

Then start working. Don't wait for permission.
