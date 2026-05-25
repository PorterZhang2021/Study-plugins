# Question Design Patterns

## Conceptual Question Patterns

### Pattern 1: What is X? How does it work?
- For core concepts that need definition + mechanism
- Example: "什么是2PC？它的两个阶段分别做什么？"

### Pattern 2: Compare X and Y
- For concepts that are easily confused
- Example: "Raft和Paxos有什么区别？"

### Pattern 3: What problems does X have?
- For understanding limitations and trade-offs
- Example: "2PC有什么缺点？"

### Pattern 4: How to solve problem X?
- For solution-oriented concepts
- Example: "一致性Hash无法解决热点问题，怎么解决？"

### Pattern 5: Why choose X over Y?
- For technology selection scenarios
- Example: "ETCD为什么选择Raft而不是Paxos？"

## Application Question Patterns

### Pattern 1: Design a system
- Combine multiple concepts into a cohesive design
- Example: "设计一个10亿数据的存储架构，用什么分片策略？"

### Pattern 2: Debug a failure scenario
- Present a failure and ask for root cause + solution
- Example: "大促期间MQ消息积压进死信队列，怎么保证最终一致？"

### Pattern 3: Technology selection
- Given requirements, choose between options
- Example: "金融转账场景，2PC/TCC/MQ选哪个？"

## Handling Unexpanded Article Content

When article mentions but doesn't explain a concept (e.g. "solutions include 2PC, 3PC, TCC"):

1. **Identify gaps**: Which concepts are named but not explained?
2. **Supplement before asking**: Explain the concept with workplace examples
3. **Design targeted questions**: Ask specifically about the unexpanded content
4. **Add to notes**: Mark as "原文提到但未展开，需补充理解"

Example from practice:
- Article mentions 3PC and TCC but only explains 2PC in detail
- Supplemented with: 3PC's three phases + timeout mechanism, TCC's Try/Confirm/Cancel
- Added questions: 题3 (3PC原理), 题4 (TCC原理), 题5 (TCC缺点)

## Handling Deep Insights During Discussion

When user reaches deep understanding through discussion:

1. **Recognize the insight**: User grasps something not in original questions
2. **Add new question**: Create a dedicated question for this insight
3. **Adjust numbering**: Shift subsequent question numbers
4. **Write detailed answer**: Capture the full reasoning, not just conclusion

Examples from practice:
- Discussion revealed TCC和2PC cannot be mixed → Added 题6
- Discussion revealed Confirm/Cancel need idempotency → Added 题7
- Discussion revealed MVCC mechanism → Added MVCC question

## Teaching Strategies for Hard Concepts

### Transaction Isolation Levels
- Teach one level at a time, not all at once
- Use concrete before/after examples with numbers
- Compare dirty read vs non-repeatable read vs phantom read explicitly
- Use table format for summary

### Consensus Algorithms
- Start with "what problem does it solve"
- Use analogy (e.g. gossip = rumor spreading)
- Compare before explaining individual algorithms
- Emphasize engineering trade-offs over algorithm details

### Distributed Lock Implementation
- MySQL first (familiar ground), then Redis (new)
- For each: how to lock → how to unlock → what can go wrong
- Connect to the three core problems (availability, deadlock, split-brain)

### CAP/BASE Theory
- Linear relationship: CAP → PACELC → BASE
- Use decision tree for "which consistency level to choose"
- Always connect to concrete business scenarios

## Session Management

### Starting a New Chapter
1. Check if user has read the article
2. Ask user to summarize what they understood
3. Identify gaps between user's understanding and article content
4. Design questions targeting those gaps

### Continuing a Chapter
1. Read current chapter notes to find last completed question
2. Resume from next question
3. Brief recap of previous questions if needed

### Ending a Session
1. Git commit with progress summary
2. Update AGENTS.md with current progress
3. Note any unfinished questions for next session
