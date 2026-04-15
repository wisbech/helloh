# Node: /helloh (helloh_LOOP.md)

## What is /helloh?

`/helloh` is an Open Harness - PAI-inspired GAN loop with Learn step. The "oh" stands for **Open Harness**.

When you work on a task:
1. **Observe** → Understand the problem
2. **Think** → Plan your approach
3. **Build** → Implement the solution
4. **Execute** → Run tests/benchmarks
5. **Verify** → Get REAL metric from test output
6. **Learn** → If metric < target, record findings for next iteration
7. **Improve** → Next iteration uses LEARN findings

The **Learn** step is what makes iteration effective.

## Skills Available

| Skill | What It Does | Trigger |
|-------|--------------|---------|
| `helloh` | Main entry - full GAN loop | `/helloh` |
| `helloh-loop` | Core GAN iteration | `/helloh:loop` |
| `helloh-status` | Show iteration status | `/helloh:status` |
| `helloh-improve` | Iterate and improve | `/helloh:improve` |
| `helloh-research` | Research before building | `/helloh:research` |

## Wiki Structure

```
wiki/
  index.md    →  Main wiki entry (start here)
  topics/     →  Detail pages (one per topic)
```

## How to Use

**When working on a task:**

```
1. Read wiki/index.md to understand the knowledge base
2. If adding new knowledge: create wiki/topics/[topic-name].md
3. Update wiki/index.md to link new topics
4. Commit both code changes AND wiki changes together
```

**Using Skills:**

- `/helloh` - Full GAN loop with Learn step
- `/helloh:loop` - Run core iteration cycle
- `/helloh:status` - Check iteration progress
- `/helloh:improve` - After code works, iterate and improve
- `/helloh:research` - Research before implementing

## Key Features

- **TRUE iteration** - Each iteration knows what to do AFTER seeing previous result
- **REAL metrics** - Parse actual test output, not fake percentages
- **Auto-generated** - The GAN creates its own metrics (inspired by Karpathy's autoresearch)
- **Skill best practices** - YAML triggers, negative boundaries, examples

## Metric

| Target | Current | Status |
|--------|---------|--------|
| publish helloh skills | initializing | active |

## Children

| Path | Weight | Status |
|------|--------|--------|
| .claude/skills/helloh | 1.0 | complete |
| .claude/skills/helloh-loop | 1.0 | complete |
| .claude/skills/helloh-status | 1.0 | complete |
| .claude/skills/helloh-improve | 1.0 | complete |
| .claude/skills/helloh-research | 1.0 | complete |
| wiki/index.md | 1.0 | active |

## Rules

| Condition | Action |
|-----------|--------|
| working_on_task == true | document_in_wiki |
| wiki_entry_created == true | commit_with_code |
| needs_research == true | invoke helloh-research |
| needs_improvement == true | invoke helloh-improve |
| needs_loop == true | invoke helloh-loop |
| children.all_complete == true | mark_done |

## Log

| Time | Action | Result |
|------|--------|--------|
| 2026-04-14T10:00 | created helloh repo | skills + wiki + template |
| 2026-04-14T10:30 | added YAML triggers | activation phrases + negative boundaries |

---

## Retrospective: What Did We Learn?

| Question | Answer |
|----------|--------|
| What worked well? | Created all skills with best practices in one session |
| What didn't work? | Need more wiki content |
| What would we do differently? | Add examples earlier |
| Any new insights or patterns? | Skill best practices apply to all skills |
| Action items for next time? | Test skills in actual agent |

---

## This is the agent

Read this file to understand how to use helloh for iteration with Learn step.

**Every skill includes retrospective**: What did we learn?