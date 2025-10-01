# Constructed Proof Corpora

Each JSONL file stores a list of problem/proof records with fields:
- `problem_name`
- `informal_statement`
- `formal_statement`
- `informal_proof`
- `formal_proof` variants (Efficient Recursive Proving enabled vs no ERP)
- metadata about generation success (`success`, `success_stage`, etc.)

## Directories
- `curated_quacky/` – Hand-selected proofs suitable for demonstration-quality reasoning.
- `generated_quacky/` – Wider pool of generated proofs captured during RL training.
- `minif2f/` – MiniF2F benchmark outputs for cross-benchmark evaluation.

DeepSeek files share the same schema and serve as baseline comparisons against the ProofSeek model outputs.
