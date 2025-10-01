# Logs

This folder contains Weights & Biases (W&B) exports from the main SFT and RL training runs. Each subdirectory matches the run name on W&B and contains:
- `wandb-metadata.json` – environment configuration captured by W&B.
- `.wandb` binary – metrics and artifacts (ignore in git using `.gitignore`).
- `debug.log` – console logs streamed by the W&B client.

Keep raw W&B exports here and summarize new runs in this file for traceability.
