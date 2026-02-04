# Reproducibility Logs (runs + cost)

This folder contains the **reproducibility artifacts** used to audit and rerun the reported experiments in the paper.

## Files

### 1) `runs_20260131_171928.csv`
Per-run execution log for the full benchmark grid (**5 systems × 3 cases × 10 seeds = 150 runs**).

Each row corresponds to one (system, case, seed) execution and records:
- **Outcome flags** (e.g., `success`, `errors_occurred`, `errors_recovered`)
- **Validation / artifact checks** (e.g., `validator_failed`, `artifacts_ok`)
- **Fallback indicator** (e.g., `fallback_used`)
- **Runtime** (`runtime_sec`)
- Optional debug fields (e.g., traceback summaries, cached code pointers)

This file is the primary source for reproducing summary tables in the manuscript (e.g., mean runtime across cases, TSR/ERR, and audit flags).

### 2) `codegen_cost_20260131_171928.csv`
Phase-A cost log that records the **API call count and token usage** (prompt/completion tokens) for **one-time code generation per (system, case)**.

This enables **cost-separated reporting**:
- **Phase A**: one-time code generation (logged here)
- **Phase B**: seeded execution (no additional LLM calls under the reported protocol)

## Notes for reviewers / rerun instructions (high-level)
- Seeds are fixed (0–9) to support deterministic repetition of Phase-B execution.
- The paper emphasizes **log-driven auditing**: readers can inspect fallback usage, artifact checks, and runtime distribution directly from `runs_*.csv`.

If you rerun the experiments, keep the same CSV schema so results remain comparable and auditable.

