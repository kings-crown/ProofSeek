# ProofSeek

ProofSeek provides the resources behind the "Neural Theorem Proving: Generating and Structuring Proofs for Formal Verification" study. It bundles curated datasets, experiment notebooks, and supplementary figures so the full pipeline from supervised fine-tuning (SFT) through reinforcement learning (RL) is reproducible.

## Repository Layout
- `notebooks/` – Jupyter notebooks used to run SFT (`sft_training.ipynb`) and RL (`rl_training.ipynb`) experiments.
- `data/constructed_proofs/` – JSONL exports of curated and generated proof corpora across Quacky and MiniF2F benchmarks.
- `assets/` – Figures for the manuscript, including dataset composition summaries.
- `docs/` – Auxiliary documentation such as the formalization notes.
- `logs/wandb/` – Weights & Biases run artifacts capturing training diagnostics.

## Datasets
| Split | File | Description |
| --- | --- | --- |
| Quacky (curated) | `data/constructed_proofs/curated_quacky/ProofSeek_curated_quacky_erp.jsonl` | ProofSeek formalizations with Efficient Recursive Proving (ERP) enabled. |
| Quacky (curated, no ERP) | `data/constructed_proofs/curated_quacky/ProofSeek_curated_quacky_noerp.jsonl` | Same as above without Efficient Recursive Proving (no ERP), enabling ablations. |
| Quacky (generated) | `data/constructed_proofs/generated_quacky/ProofSeek_quacky_generated_erp.jsonl` | Synthetic proofs generated during RL with ERP active. |
| Quacky (generated, no ERP) | `data/constructed_proofs/generated_quacky/ProofSeek_quacky_generated_noerp.jsonl` | Synthetic proofs generated during RL without ERP control. |
| MiniF2F | `data/constructed_proofs/minif2f/ProofSeek_minif2f.jsonl` | ProofSeek outputs on the MiniF2F benchmark. |
| MiniF2F (no ERP) | `data/constructed_proofs/minif2f/ProofSeek_noerp_minif2f.jsonl` | Variant without Efficient Recursive Proving for comparison. |
| DeepSeek counterparts | `data/constructed_proofs/**/DeepSeek_*.jsonl` | Parallel runs generated using DeepSeek for baseline comparison.

The SFT dataset is available on Hugging Face: [kings-crown/FVELer_PISA_NotProven](https://huggingface.co/datasets/kings-crown/FVELer_PISA_NotProven). The RL dataset is at [kings-crown/FVELer_PISA_Proven](https://huggingface.co/datasets/kings-crown/FVELer_PISA_Proven).

## Getting Started
1. Create a Python 3.10+ environment and install baseline dependencies:
   ```bash
   pip install torch transformers datasets pandas jinja2 wandb
   ```
2. Launch the notebooks under `notebooks/` to reproduce the SFT and RL runs.
3. If you use the provided W&B artifacts, set `WANDB_MODE=offline` to avoid accidental uploads.

## Contributing
Please keep large artifacts in `data/constructed_proofs/` compressed when possible and document new experiments in this README. Figures should live under `assets/`, and new training logs should include a short note inside `logs/` describing the run context.
