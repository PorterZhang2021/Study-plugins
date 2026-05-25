---
name: series-column-learning
description: >
  Specialized workflow for learning technical content through a structured
  "question-and-discuss" approach with a human learner. Use ONLY when the user
  is working through a serialized course, column, or tutorial series (e.g.
  极客时间专栏, 面试精讲系列, 技术课程) and wants to deeply understand the
  material by answering practice questions together. Do NOT use for: reading
  books, analyzing papers, general Q&A, or non-serialized content. Trigger
  when the user says things like "我们继续学习", "下一章", "做题", "讨论题目",
  or when they are clearly progressing through a multi-chapter course.
---

# Series Column Learning Workflow

## When to Use

- User is progressing through a **serialized course/column** with multiple chapters
- User wants to **answer practice questions** to deeply understand the material
- User prefers **workplace-scenario-driven derivation** over rote memorization
- Context has been reset and user references previous learning sessions

## When NOT to Use

- Reading a book (not a serialized column)
- Analyzing research papers
- General Q&A without structured progression
- One-off technical questions

## Core Workflow

### Phase 0: Chapter Setup (if starting new chapter)

1. Check `AGENTS.md` and previous notes for accumulated context
2. Ask user if they have read the chapter article
3. If not, wait for user to read before proceeding
4. If yes, design practice questions based on the article

### Phase 1: Question Design

- Design **conceptual questions** covering all core knowledge points from the article
- Design **application questions** that connect concepts to workplace scenarios
- For content **mentioned but not expanded** in the article, supplement with explanations before asking
- Add new questions for **deeply understood concepts** that emerged during discussion

### Phase 2: Explain Principles

- Explain one question at a time. Do NOT rush.
- Use **concrete workplace scenarios** instead of abstract terms
- For difficult concepts (e.g. transaction isolation levels), explain step by step with examples
- Wait for user to confirm understanding before moving to next question
- Do NOT write answers to notes yet

### Phase 3: User Organizes Answer

- Let user explain the concept in their own words
- Accept informal, spoken-style explanations
- Must be derived from **workplace scenarios**, not memorized definitions

### Phase 4: Discussion & Correction

- Correct misunderstandings patiently
- Discuss edge cases and boundary scenarios
- Do NOT move on until user truly understands (not "kind of" understands)
- For extreme cases (e.g. network partitions), walk through what happens

### Phase 5: Write to Notes

- Write finalized answers to the notes file ONLY after user confirms understanding
- Answers must reflect **discussion depth**, not be oversimplified
- Ensure question numbers match answers one-to-one
- Adjust question numbers when adding new questions to avoid duplicates

## Key Principles (Never Violate)

1. **Never write answers before user understands** — Always wait for confirmation
2. **Always use workplace scenarios** — Reject "interview version" vs "work version" dual tracks
3. **Discussion depth must be in notes** — One-liners are unacceptable
4. **Supplement unexpanded content** — If article mentions but doesn't explain, add it
5. **Add questions for deep insights** — Don't let hard-won understanding disappear
6. **Be patient with difficult concepts** — Some topics (isolation levels, consensus algorithms) require multiple rounds

## File Structure

```
project-root/
├── articles/          # Original course articles
├── notes/             # Learning notes
│   ├── [NN] [title]-笔记.md
│   ├── 问题总结清单.md
│   ├── 推荐书单.md
│   └── 学习流程操作手册.md
├── images/            # Article images
└── AGENTS.md          # AI assistant context (accumulated learning state)
```

## Git Commit Convention

- Prefix: `docs:` for notes and structural changes
- Include which questions were completed in commit message
- Commit at end of each session or chapter

## References

- **Detailed workflow guide**: See [references/workflow.md](references/workflow.md) for complete step-by-step instructions, user preferences, note format specifications, and common mistakes to avoid
- **Question design patterns**: See [references/patterns.md](references/patterns.md) for patterns on how to design good conceptual vs application questions, and how to handle unexpanded article content
