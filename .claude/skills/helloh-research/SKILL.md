---
name: helloh-research
description: Research before implementing. Use when understanding something before building - gather sources, extract insights, document in wiki. Activation phrases: "research", "investigate", "understand", "gather info", "learn about", "find best practices"
negative_boundaries: Do NOT implement without research, Do NOT skip documentation
---

# Helloh Research

Research first, build second. Every task deserves investigation.

## When to Use

- Before starting any implementation
- When you don't understand the domain
- When you need to gather best practices
- When existing solutions need evaluation

Activation phrases: "research", "investigate", "understand", "gather info", "learn about", "find best practices"

## Process

### 1. Define Research Question

What exactly do you need to understand? Write it down.

### 2. Gather Sources

Search for:
- Official documentation
- Code examples
- Research papers
- Community discussions
- Existing implementations

### 3. Extract Key Insights

What's important? Note:
- Patterns and conventions
- Tradeoffs and limitations
- Best practices
- Common pitfalls

### 4. Document in Wiki

Create `wiki/topics/[topic-name].md` with:
- Research question
- Sources (with links)
- Key insights
- Recommendations
- Related topics

### 5. Verify

- Sources cited and accessible?
- Insights accurate and relevant?
- Recommendations actionable?

## Usage

```bash
/helloh:research
```

Or with a specific topic:

```
/helloh:research
topic: SeaStreamer patterns
```

## Integration

This skill works with:
- `/helloh` - Full workflow integration
- `/helloh:improve` - After research, improve
- Wiki system - Document insights

**Key principle**: Research compounds. Document it.

---

_See also: /helloh, /helloh:loop, /helloh:improve_