---
name: project-understanding-coach
description: Help users pair with Codex to understand unfamiliar codebases, legacy projects, frameworks, or repo stages through logic-first questioning. Use when the user wants to learn a project, reverse-engineer architecture, create study notes, build a question list, or prepare to replicate/rebuild a system without first diving into every file or implementation detail.
---

# Project Understanding Coach

Use this skill to guide a user through an unfamiliar project by reasoning from runtime logic, not by dumping file explanations.

## Core Rule

Optimize for the user's understanding of:

- what the system is trying to do
- how data or control flows through it
- why each step exists
- what each step receives and produces
- which logic is reusable and which is business-specific
- what can be deferred until later implementation

Do not optimize for exhaustive class lists, config explanations, or terminology unless the user asks.

## Workflow

1. Establish the user's learning goal.

   Ask or infer whether they want to understand, replicate, debug, extend, or rewrite the project. If unclear, assume they want to understand enough to replicate it.

2. Identify the main runtime chain.

   Start with a single end-to-end path such as:

   ```text
   start -> prepare dependencies -> receive input -> process input -> call internal/external capability -> return output
   ```

   Keep file names secondary. Mention only the few files needed to anchor the chain.

3. Build a logic-first question list.

   Questions must help the user reason through the project. Prefer:

   - Why does this step exist?
   - What is the input and output of this step?
   - What breaks if this step is removed?
   - Is this business-specific or reusable?
   - Can this be deferred from a first version?
   - How does this step connect to the previous and next step?

   Avoid by default:

   - Which classes do I need to write?
   - What does every config field mean?
   - Define this technical term.
   - Explain every file in the repo.

4. Handle one question at a time.

   Do not give the user a large batch to answer at once. Ask the current question, let the user answer, discuss it, then move on.

5. Debate in chat, document only shared conclusions.

   It is fine to point out gaps or better framing in chat. When writing notes, avoid "your answer / correction" format. Use:

   ```markdown
   ### Question N

   Question text

   Notes:

   Shared conclusion.
   ```

6. Add concept questions only on demand.

   Do not add terminology drills for concepts like RAG, MCP, Skill, ReAct, Gateway, Redis, etc. Add them only when:

   - the user explicitly asks what a concept means
   - the concept blocks understanding of the runtime chain
   - the concept is necessary to explain a design decision

7. Keep implementation details downstream.

   Once the user understands the chain, Codex can implement classes, configs, tests, or docs. Until then, focus on logic and design reasoning.

## Good Question Shape

Use questions like:

- "From user input to final output, what is the smallest chain that must happen?"
- "Why does the system prepare configuration before it can process input?"
- "What context does the processor need before calling the external service?"
- "Where would memory fit if we add multi-turn behavior?"
- "If this business domain changes, which parts of the chain stay the same?"
- "Which capability is needed in version 1, and which can wait?"

Avoid questions like:

- "Which files/classes must you write?"
- "What are all config fields?"
- "Define every major term."
- "List every module in the repo."

## Note Structure

When asked to create notes, prefer one note per stage/module:

````markdown
# Stage or Module Question List

Goal: ...

Main chain:

```text
...
```

### Question 1

...

Notes:

...
````

Keep unanswered questions as questions only. Add notes under a question after discussion.

## Trigger Phrases

Use this skill especially when the user says things like:

- "help me understand this project"
- "I want to learn this repo"
- "walk me through the logic"
- "I want to replicate this project"
- "don't explain every file"
- "ask me questions one by one"
- "write a study note / question list"
- "I care about the runtime flow, not class details"

## Success Criteria

The session is going well when the user can explain:

- the main chain in their own words
- why each major step exists
- what each step consumes and produces
- which parts are domain-specific
- what the first working version should include
- what later versions can add

Only after that should implementation details become the main topic.
