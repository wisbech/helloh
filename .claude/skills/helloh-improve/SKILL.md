---
name: helloh-improve
description: Iterate and improve existing code. Use after initial implementation to refine, optimize, and apply skill best practices. Activation phrases: "improve this", "make it better", "refine", "optimize", "clean up", "add best practices"
negative_boundaries: Do NOT improve working code unnecessarily, Do NOT add unrequested features
---

# Helloh Improve

Systematic improvement skill that refines existing code and applies best practices.

## When to Use

- After initial implementation is done
- When code works but could be cleaner
- When performance could be better
- When applying skill best practices

Activation phrases: "improve this", "make it better", "refine", "optimize", "clean up", "add best practices"

## Process

### 1. Identify Improvement Areas

Look for:
- Code complexity
- Duplication
- Performance bottlenecks
- Missing tests
- Documentation gaps
- Edge cases

### 2. Apply Skill Best Practices

For skill files, ensure:
- YAML trigger header with explicit activation phrases
- Overview paragraph
- Step-by-step workflow
- Output format specification
- Examples and edge cases

### 3. Propose Changes

For each improvement:
- What specifically to change
- Why it matters
- Expected benefit
- Risk level

### 4. Evaluate Tradeoffs

Ask:
- Time cost vs benefit?
- Risk of breaking something?
- Long-term vs short-term gain?

### 5. Implement Improvements

Make changes:
- One improvement at a time
- Test after each change
- Commit incrementally

### 6. Verify

- Improvements measurable?
- Tests still passing?
- Code still works?

## Skill Best Practices (5 Components)

1. **YAML Header** - name, description, explicit activation phrases, negative boundaries
2. **Overview** - What the skill does, when to use it
3. **Workflow** - Step-by-step instructions
4. **Output Format** - What the skill produces
5. **Examples** - Usage examples and edge cases

## Usage

```bash
/helloh:improve
```

After initial implementation, runs improvement iterations.

## Integration

This skill works with:
- `/helloh` - GAN loop integration
- `/helloh:loop` - Core iteration
- helloh_LOOP.md - State tracking

**Key principle**: Good code becomes great through iteration.

---

_See also: /helloh, /helloh:loop, /helloh:research_