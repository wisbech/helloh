---
name: helloh-loop
description: Core GAN loop iteration skill. Use when you need to run the Generator-Evaluator-Learn cycle with auto-generated metrics. Activation phrases: "run loop", "iterate", "next iteration", "GAN cycle", "improve iteration"
negative_boundaries: Do NOT skip the Learn step, Do NOT use fake metrics, Do NOT pre-plan iterations
---

# Helloh Loop

Core GAN (Generator-Evaluator) loop with auto-generated metrics. This is the engine that drives iteration.

## When to Use

- When running the main GAN iteration cycle
- When implementing the Learn step feedback loop
- When parsing REAL metrics from test output

Activation phrases: "run loop", "iterate", "next iteration", "GAN cycle", "improve iteration"

## The Core Loop

```
LOOP (while !converged && iteration < max):
  1. GENERATOR → Implement based on task + LEARN findings
  2. EXECUTE   → Run tests/benchmarks
  3. VERIFY    → Parse REAL metric from output
  4. LEARN     → If metric < target: feed findings to GENERATOR
  5. CONVERGE  → If metric >= target: STOP
```

## Key Features

### Auto-Generated Metrics

- Parse test output for REAL values
- Not pre-determined percentages
- Self-measured improvement

### The Learn Step

The critical differentiator:
- Evaluator findings → Generator input
- Each iteration knows what to do AFTER seeing previous result
- True iteration, not planned

### Convergence Rules

| Condition | Action |
|-----------|--------|
| metric ≥ target | CONVERGED - stop |
| iteration >= max | Force stop - warning |
| metric stale for 2 iterations | CONVERGED (diminishing returns) |

## Usage

```
/helloh:loop
task: implement feature X
target_metric: test_pass_rate ≥ 99%
max_iterations: 10
```

Or continue from helloh_LOOP.md:

```
/helloh:loop
```

## Output Format

Updates helloh_LOOP.md:
```
## Iteration Log
| # | Action | Metric | Status |
|---|--------|--------|--------|
| 1 | init   | 50%    | iterate |
| 2 | fix A  | 75%    | iterate |
| 3 | fix B  | 100%   | converged |
```

## Examples

### Single Iteration
```
Input: task=fix test, target=99%
Action: Run tests → 95% → LEARN: "rounding issue" → Fix → Run → 100% → CONVERGED
```

### Multiple Iterations
```
Iteration 1: 50% → LEARN: "missing import"
Iteration 2: 75% → LEARN: "wrong assertion"
Iteration 3: 90% → LEARN: "edge case"
Iteration 4: 100% → CONVERGED
```

## Integration

- Works with `/helloh` for full workflow
- Uses helloh_LOOP.md for state
- Parses actual test output for metrics

---

_See also: /helloh, /helloh:status, /helloh:improve_