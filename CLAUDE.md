# CLAUDE.md - Helloh Project

Helloh is an Open Harness - PAI-inspired GAN loop with Learn step.

## Quick Start

```
Type /helloh to invoke the main skill
```

## Skills

- `/helloh` - Full GAN loop with Learn step
- `/helloh:loop` - Core iteration engine
- `/helloh:status` - Check iteration progress
- `/helloh:improve` - Iterate and improve code
- `/helloh:research` - Research before building

## Wiki

The knowledge base lives in `wiki/`:
- `wiki/index.md` - Main entry
- `wiki/topics/` - Individual topics

## helloh_LOOP.md

The iteration state is tracked in `helloh_LOOP.md`:
- Current metric and target
- Iteration history
- Convergence status

## How to use

1. Read `helloh_LOOP.md` for context
2. Use `/helloh` for full GAN loop
3. Document insights in `wiki/topics/`
4. Commit code + wiki together

## Key Principle

**True iteration with Learn step - each iteration knows what to do AFTER seeing the previous result.**

---

_Run `/helloh` to get started_