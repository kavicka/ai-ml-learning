# ai-ml-learning

🇸🇰 [Slovenská verzia](README.sk.md)

My path from ML fundamentals to AI engineering: each folder is one step of the roadmap, with its own environment, code, results and write-up.

| # | Project | What it shows | Status |
|---|---|---|---|
| 01 | [Setup & matmul benchmark](01-setup-benchmark/) | Reproducible `uv` + PyTorch environment, CPU/MPS/CUDA benchmark, O(n³) scaling | ✅ |
| 02 | [Derivatives & chain rule](02-calculus-chain-rule/) | Backprop by hand vs numerical vs PyTorch autograd on a small graph, finite-difference error vs h | ✅ |
| 03 | [Vectors, matrices & shapes](03-linear-algebra-shapes/) | Matmul from scratch vs NumPy, shape rules up to (B,T,C)@(C,H), attention-head shapes, matrices as transformations | ✅ |
| 04 | [P1: Autograd from scratch & makemore](04-autograd-makemore/) | Own autograd engine tested vs PyTorch, MLP on it, char-level LM for Slovak municipality names (val NLL 2.46 bigram → 1.95 MLP) | ✅ |
| 05 | [Racing Lab: cars that learn to drive](05-racing-lab/) | A pygame racing lab that grows with the roadmap: each fitting step gets a chapter shown on the cars (ch. 01–04 done); other steps get their own visual example | ✅ ch. 01–04 |

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
