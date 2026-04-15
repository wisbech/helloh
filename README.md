# Helloh - Open Harness

A PAI-inspired GAN loop system with the critical **Learn** step. The "oh" stands for **Open Harness**.

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## Philosophy

Based on PAI's Foundational Algorithm:

```
Observe → Think → Plan → Build → Execute → Verify → Learn → Improve
```

The **Learn** step** is what makes iteration effective - evaluator findings feed back to generator.

## Key Features

- **TRUE iteration** - Each iteration knows what to do AFTER seeing previous result
- **REAL metrics** - Parse actual test output, not fake percentages
- **Auto-generated metrics** - The GAN creates its own metrics (inspired by Karpathy's autoresearch)
- **Skill best practices** - YAML triggers, negative boundaries, examples

## Skills

| Skill | Trigger | Description |
|-------|---------|-------------|
| helloh | `/helloh` | Main entry - full GAN loop |
| helloh-loop | `/helloh:loop` | Core GAN iteration |
| helloh-status | `/helloh:status` | Show iteration status |
| helloh-improve | `/helloh:improve` | Iterate and improve |
| helloh-research | `/helloh:research` | Research before building |

## Quick Start

1. Copy this folder to your project
2. Read `CLAUDE.md` for context
3. Run `/helloh` to start the GAN loop

## How It Works

```
LOOP (iteration = 1 to max_iterations):
  1. GENERATOR → Implement/fix based on task + previous LEARN findings
  2. EXECUTE   → Run tests/benchmarks
  3. VERIFY    → Get REAL metric from test output
  4. LEARN     → If metric < target: evaluator findings → feed to GENERATOR
  5. CONVERGE  → If metric >= target: STOP, converged
```

## The Learn Step

This is the key differentiator from traditional iteration:

| Planned Iteration | True Iteration (helloh) |
|------------------|------------------------|
| Pre-plan 10 iterations | Only know iteration N after seeing N-1 |
| Fake metric (25%, 45%...) | Parse REAL test output |
| Follow predetermined path | Dynamic - depends on evaluator |

## Wiki Integration

Every task produces knowledge. Document it:

```
1. Read wiki/index.md
2. Create wiki/topics/[topic-name].md
3. Update wiki/index.md
4. Commit code + wiki together
```

## helloh_LOOP.md

The iteration state is tracked in `helloh_LOOP.md`:
- Current metric and target
- Iteration history
- Convergence status

## Installation

Copy the folder to your project root:

```
/your-project/
├── .claude/skills/
│   ├── helloh/SKILL.md
│   ├── helloh-loop/SKILL.md
│   └── ...
├── wiki/
├── helloh_LOOP.md
└── CLAUDE.md
```
/your-project/
├── .claude/skills/
│   ├── helloh/SKILL.md
│   ├── helloh-loop/SKILL.md
│   └── ...
├── wiki/
├── helloh_LOOP.md
└── CLAUDE.md
```

## Usage

### Basic
```
/helloh
```

### With task
```
/helloh
task: fix the flaky test
target_metric: test_pass_rate ≥ 99%
max_iterations: 10
```

### Check status
```
/helloh:status
```

## Best Practices

Each skill follows the 5-component structure:
1. YAML header with activation phrases and negative boundaries
2. Overview paragraph
3. Step-by-step workflow
4. Output format specification
5. Examples and edge cases

## License

MIT