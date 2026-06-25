# FocalBoost-IDS

An engineered focal-loss LightGBM model for intrusion detection in
resource-constrained IoT networks.

## Overview
FocalBoost-IDS replaces LightGBM's default log-loss with a fabricated
focal-loss training objective (custom first- and second-order gradients)
to handle the severe benign-vs-attack class imbalance in IoT traffic,
combined with SHAP-guided feature pruning for low-latency edge deployment.

## Engineering contribution (F/M/R/S)
- [F] Fabricate: focal-loss objective for LightGBM
- [R] Remove: SHAP-ranked feature pruning (~30–40% of features)

## Data
- Public benchmark: CICIoT2023 (Neto et al., 2023)
- Primary: locally captured IoT traffic (flow features via CICFlowMeter)

## Method
1. Lock an unmodified LightGBM baseline (fixed seed, fixed splits).
2. Train FocalBoost-IDS on identical splits.
3. Compare with AUC-PR, Macro-F1, attack recall, model size, latency;
   Wilcoxon signed-rank test over 5 folds.

## Reproducibility
- Seed: 42
- 5-fold stratified CV + held-out test, repeated over 3 seeds
- See `requirements.txt` for pinned versions

## Status
Research proposal stage — code in progress.

## License
MIT

## Citation
[Your name]. (2026). FocalBoost-IDS [Source code]. GitHub.
