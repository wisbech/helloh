# Helloh Config - Drop into any project

You are an AI assistant helping with this project. Drop this file into any project to enable helloh skills.

## What is Helloh?

Helloh is an Open Harness - a PAI-inspired GAN loop system with the critical **Learn** step.

## How It Works

```
LOOP (iteration = 1 to max_iterations):
  1. GENERATOR → Implement based on task + previous LEARN findings
  2. EXECUTE   → Run tests/benchmarks
  3. VERIFY    → Get REAL metric from test output
  4. LEARN     → If metric < target: feed findings to GENERATOR
  5. CONVERGE  → If metric >= target: STOP
```

## Quick Start

1. Drop this `helloh_CONFIG.md` in your project root
2. Create `.claude/skills/` with skill files
3. Run `/helloh` to start iterating

## Skills to Create

| Skill | Trigger | Purpose |
|-------|---------|---------|
| helloh | `/helloh` | Main entry point |
| helloh-loop | `/helloh:loop` | Core iteration |
| helloh-status | `/helloh:status` | Check progress |
| helloh-improve | `/helloh:improve` | Iterate & improve |
| helloh-research | `/helloh:research` | Research first |

## Config Sections

### Metric
| Target | Current | Status |
|--------|---------|--------|
| [your goal] | [value] | [status] |

### Children (sub-tasks)
| Path | Weight | Status |
|------|--------|--------|
| ./task | 1.0 | pending |

### Rules
| Condition | Action |
|-----------|--------|
| [when] | [do this] |

### Log
| Time | Action | Result |
|------|--------|--------|
| [timestamp] | [what] | [result] |

## Key Principles

- **TRUE iteration** - Each iteration knows what to do AFTER seeing previous result
- **REAL metrics** - Parse actual test output, not fake percentages
- **Learn step** - Evaluator findings feed back to generator
- **Document learnings** - Every iteration produces knowledge