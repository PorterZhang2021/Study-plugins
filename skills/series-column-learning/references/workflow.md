# Complete Workflow Guide

## User Preferences (Must Obey)

1. **Workplace scenario derivation only** — Reject "interview version" vs "work version" dual tracks. Everything must be derived from real work scenarios.
2. **Understand before writing** — Never write answers to notes before user confirms understanding
3. **Depth in notes** — Discussion depth must be reflected in final notes, not simplified
4. **Supplement unexpanded content** — If article mentions but doesn't explain (e.g. 3PC, TCC), supplement with explanations
5. **Add questions for insights** — When deep understanding emerges during discussion, add new questions to cover it
6. **Patience with hard topics** — Some concepts (isolation levels, consensus algorithms) need multiple rounds. Do not rush.

## Learning Flow (5 Steps)

### Step 1: Design Questions

- Base questions strictly on article content
- Two types:
  - **Conceptual**: Cover all core knowledge points
  - **Application**: Connect concepts to workplace scenarios
- For content mentioned but not expanded in article, plan to supplement before asking
- During discussion, if deep understanding emerges, add new questions

### Step 2: Explain Principles

- One question at a time
- Use concrete workplace examples
- For difficult concepts, use step-by-step explanation with visual/text diagrams
- Check understanding before proceeding
- Do NOT write to notes yet

### Step 3: User Organizes Answer

- User explains in their own words
- Accept informal speech
- Must derive from workplace scenarios

### Step 4: Discussion & Correction

- Correct misunderstandings
- Discuss edge cases: "What if network breaks?" "What if client crashes?"
- Do NOT proceed until truly understood
- Common pattern: User says "I kind of get it" → Keep explaining with different examples

### Step 5: Write to Notes

- Write only after user confirmation
- Reflect discussion depth
- Match question numbers one-to-one
- Adjust numbers when adding questions

## Note Format Specification

### Filename
```
[NN] [Article Title]-笔记.md
```

### Structure
```markdown
# [NN] [Title]-笔记

## 核心知识点
(Brief summary of article core points)

## 练习题（概念题）
### [Category]
#### 题N
> Question text

**答案：**
(Detailed answer reflecting discussion depth)

## 练习题（应用题）
#### 题N
> Question text

**答案：**
(Detailed answer reflecting discussion depth)
```

### Answer Quality Standards

- Must reflect actual discussion depth
- Cannot be one-liners
- Must include edge cases discussed
- Must correct common misconceptions that were clarified

## Common Mistakes to Avoid

| Mistake | Correct Approach |
|---------|---------------|
| Write answers before user understands | Wait for explicit confirmation |
| Oversimplify answers in notes | Include discussion depth and edge cases |
| Skip content article mentions but doesn't expand | Supplement with explanation, then ask |
| Use abstract definitions only | Always derive from workplace scenarios |
| Forget to add questions for deep insights | Add new questions when breakthrough understanding happens |
| Rush through difficult concepts | Use multiple examples, check repeatedly |
| Ignore user's "I kind of understand" | Probe deeper with follow-up questions |

## Git Commit Convention

- `docs:` prefix for notes and structural changes
- Example: `docs: complete chapter 04 practice questions 1-10`
- Commit at end of session or chapter
- Include completed question ranges in message

## Restart Protocol (When Context is Lost)

1. Read `AGENTS.md` in project root (if exists) for accumulated state
2. Read the latest chapter notes file to see current progress
3. Ask user: "我们上次学到哪一章了？继续还是复习？"
4. If continuing, resume from last unanswered question
