---
name: helloh
description: Open Harness - PAI-inspired GAN loop with Learn step. Use when you need to iterate on a task until it converges on a target metric using REAL test results. Activation phrases: "run GAN loop", "iterate to convergence", "auto-improve", "improve skill", "make it better", "optimize this", "convergence check", "check progress"
negative_boundaries: Do NOT use for one-off tasks without measurable targets, do NOT use for tasks that don't have runnable tests/benchmarks, do NOT skip the Learn step
---

# Helloh (Open Harness)

PAI-inspired Generator-Evaluator loop with the critical **Learn** step. The "oh" stands for **Open Harness**.

## Philosophy

Based on PAI's Foundational Algorithm:

```
Observe → Think → Plan → Build → Execute → Verify → **Learn** → Improve
```

The **Learn** step is what makes iteration effective - evaluator findings feed back to generator.

## When to Use

- When you have a task that needs iteration until convergence
- When there's a measurable target metric (test pass rate, benchmark time, etc.)
- When you want TRUE iteration - not pre-planned iterations
- When you want REAL metrics from actual test execution

Activation phrases: "run GAN loop", "iterate to convergence", "auto-improve", "improve skill", "make it better", "optimize this", "convergence check", "check progress"

## The Helloh Algorithm

```
LOOP (iteration = 1 to max_iterations):
  1. GENERATOR → Implement/fix based on task + previous LEARN findings
  2. EXECUTE   → Run tests/benchmarks
  3. VERIFY    → Get REAL metric from test output
  4. LEARN     → If metric < target: evaluator findings → feed to GENERATOR
  5. CONVERGE  → If metric >= target: STOP, converged

STOP conditions:
  - metric >= target (converged)
  - iteration >= max_iterations (force stop)
  - metric stale for 2 iterations (diminishing returns)
```

## Key Difference: True vs Planned Iteration

| Planned (what we did before) | True (what helloh does) |
|-------------------------------|------------------------|
| Pre-plan 10 iterations | Only know iteration N after seeing N-1 |
| Fake metric (25%, 45%...) | Parse REAL test output |
| Follow predetermined path | Dynamic - depends on evaluator |

## How to Use

### Basic Usage

```
/helloh
```

Continues from where helloh_LOOP.md left off.

### With Task

```
/helloh
task: fix the flaky test in orderbook
target_metric: test_pass_rate ≥ 99%
max_iterations: 10
```

### Steps Executed

1. Read current helloh_LOOP.md to understand context
2. GENERATOR: Implement/fix based on task + previous LEARN findings
3. EXECUTE: Run tests and parse REAL metric from output
4. VERIFY: Compare metric to target
5. LEARN: If metric < target, record findings for next iteration
6. Update helloh_LOOP.md with iteration results
7. If metric >= target: CONVERGED → stop
8. If iteration >= max: Force stop with warning

## What Gets Tracked

### helloh_LOOP.md Updates

- Iteration number
- REAL metric value (parsed from test output)
- Findings (if any - from evaluator)
- Convergence status

### Convergence Detection

| Condition | Action |
|-----------|--------|
| metric ≥ target | CONVERGED - stop |
| iteration >= max | Force stop - warning |
| metric stale for 2 iterations | CONVERGED (diminishing returns) |

## Integration

This skill works with:

- **PAI Primitives**: Memory, Skill System, Hooks
- **helloh_LOOP.md**: Iteration history and state
- **Real Tests**: Parses actual test output, not fake

## Examples

### Example 1: Fix Failing Test

```
Input:
  task: fix volume_rounded_to_1_decimal test
  target_metric: test_pass_rate ≥ 99%

Process:
  Iteration 1:
    - Run tests: 95.5% (1 failing)
    - LEARN: "volume rounding wrong precision"
    - Fix: change *100 to *10
    - Run tests: 100%
    - CONVERGED
```

### Example 2: Multiple Iterations

```
Input:
  task: optimize matching engine latency
  target_metric: p99_latency < 1ms

Process:
  Iteration 1: 5ms → "need algorithm optimization"
  Iteration 2: 3ms → "need better data structures"  
  Iteration 3: 1.5ms → "close, need fine-tuning"
  Iteration 4: 0.8ms → CONVERGED
```

## Retrospective

After completion, fill in:

| Question | Answer |
|----------|--------|
| Did iteration converge? | |
| How many iterations? | |
| What was the final metric? | |
| What would we do differently? | |

## Files Modified

- `helloh_LOOP.md` - GAN state + convergence log + iteration history

## Usage

```bash
/helloh
```

Or with parameters:

```
/helloh
task: fix failing test
target_metric: test_pass_rate ≥ 99%
max_iterations: 10
```

---

_Helloh: True iteration with Learn step_