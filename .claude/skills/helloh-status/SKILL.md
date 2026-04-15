---
name: helloh-status
description: Show GAN iteration status. Use when checking iteration progress, convergence status, or metric history. Activation phrases: "check status", "show progress", "iteration status", "how are we doing", "convergence status"
negative_boundaries: Do NOT show fake metrics, Do NOT skip helloh_LOOP.md source
---

# Helloh Status

Display GAN iteration state from helloh_LOOP.md.

## When to Use

- Checking iteration progress
- Verifying convergence status
- Reviewing metric history
- Before next iteration

Activation phrases: "check status", "show progress", "iteration status", "how are we doing", "convergence status"

## What It Shows

- Current iteration number
- Target vs current metric
- Convergence status
- Iteration log/history
- Agent states (if applicable)

## Usage

### Basic
```
/helloh:status
```

### With Worktree
```
/helloh:status ./my-worktree
```

## Output Example

```
=== GAN Status ===

Metric: test_pass_rate
Target: ≥99%
Current: 87%
Iterations: 3/10

Convergence: ❌ Not yet

Log:
| # | Output | Metric | Status |
|---|--------|--------|--------|
| 1 | init   | 50%    | iterate |
| 2 | fix A  | 75%    | iterate |
| 3 | fix B  | 87%    | iterate |
```

## Integration

Works with:
- `/helloh` - Full workflow status
- `/helloh:loop` - Track progress during iteration
- helloh_LOOP.md - Source of truth

---

_See: /helloh, /helloh:loop_