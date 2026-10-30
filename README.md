# ai-ml-learning

🇸🇰 [Slovenská verzia](README.sk.md)

My path from ML fundamentals to AI engineering. **This repo is only the index.** Every step of the roadmap is its own private repository with its own environment, code, results and write-up; the table links to them.

| # | Project | What it shows | Status |
|---|---|---|---|
| 01 | [Setup & matmul benchmark](https://github.com/kavicka/01-setup-benchmark) | Reproducible `uv` + PyTorch environment, CPU/MPS/CUDA benchmark, O(n³) scaling | ✅ |
| 02 | [Derivatives & chain rule](https://github.com/kavicka/02-calculus-chain-rule) | Backprop by hand vs numerical vs PyTorch autograd on a small graph, finite-difference error vs h | ✅ |
| 03 | [Vectors, matrices & shapes](https://github.com/kavicka/03-linear-algebra-shapes) | Matmul from scratch vs NumPy, shape rules up to (B,T,C)@(C,H), attention-head shapes, matrices as transformations | ✅ |
| 04 | [P1: Autograd from scratch & makemore](https://github.com/kavicka/04-autograd-makemore) | Own autograd engine tested vs PyTorch, MLP on it, char-level LM for Slovak municipality names (val NLL 2.46 bigram → 1.95 MLP) | ✅ |
| 05 | [Racing Lab: cars that learn to drive](https://github.com/kavicka/05-racing-lab) | A pygame racing lab that grows with the roadmap: each fitting step gets a chapter shown on the cars (ch. 01–04 and 06 done); other steps get their own visual example | ✅ ch. 01–04, 06 |
| 06 | [Probability, Bayes & ROC vs PR](https://github.com/kavicka/06-probability-bayes-roc) | Variance of a mean ~1/n, Bayes on a 1 % disease (positive test → 16.7 %), same model ROC-AUC 0.92 at 50 % and 0.1 % positives while precision falls 87 % → 0.6 % | ✅ |
| 07 | [Tabular ML: customer churn (P2)](https://github.com/kavicka/07-churn-tabular-ml) | Telco churn: tuned LightGBM PR-AUC 0.664 vs 0.265 naive, oversampling leakage (CV 0.89 vs real 0.64), threshold from costs catches 68 % of churners at 118 € vs 133 € per customer, FastAPI endpoint | ✅ |

## Roadmap
1. **Setup & math** – environment, derivatives, linear algebra
2. **ML fundamentals** – autograd from scratch, tabular ML (churn), image classifier
3. **Deep learning & transformers** – GPT from scratch in Slovak, LoRA/DPO fine-tuning, embeddings & retrieval
4. **AI engineering** – eval-driven RAG, agents & MCP, observability and guardrails
5. **Serving & MLOps** – inference optimization, end-to-end ML system
6. **Capstone** – ClaimPilot v2

## Conventions
- Every project runs with `uv sync && uv run python <script>.py`.
- Every project has a baseline, a metric and a results table.
- Plots and screenshots live in each project's `assets/` folder.
- The main README is in English (`README.md`); a Slovak version lives in `README.sk.md`.
