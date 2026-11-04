# ai-ml-learning

🇸🇰 [Slovenská verzia](README.sk.md)

My path from ML fundamentals to AI engineering. **This repo is only the index.** Every step of the roadmap is its own private repository with its own environment, code, results and write-up; the table links to them.

Each project README now starts with a plain-language explanation before the technical walkthrough. Follow a project link to see its examples, measured results, plots, and Slovak translation.

| # | Project | What it shows | Status |
|---|---|---|---|
| 01 | [Setup & matmul benchmark](https://github.com/kavicka/01-setup-benchmark) | Reproducible `uv` + PyTorch environment, CPU/MPS/CUDA benchmark, O(n³) scaling | ✅ |
| 02 | [Derivatives & chain rule](https://github.com/kavicka/02-calculus-chain-rule) | Backprop by hand vs numerical vs PyTorch autograd on a small graph, finite-difference error vs h | ✅ |
| 03 | [Vectors, matrices & shapes](https://github.com/kavicka/03-linear-algebra-shapes) | Matmul from scratch vs NumPy, shape rules up to (B,T,C)@(C,H), attention-head shapes, matrices as transformations | ✅ |
| 04 | [P1: Autograd from scratch & makemore](https://github.com/kavicka/04-autograd-makemore) | Own autograd engine tested vs PyTorch, MLP on it, char-level LM for Slovak municipality names (val NLL 2.46 bigram → 1.95 MLP) | ✅ |
| 05 | [Racing Lab: cars that learn to drive](https://github.com/kavicka/05-racing-lab) | A pygame racing lab that grows with the roadmap: each fitting step gets a chapter shown on the cars (ch. 01–04, 06, 11 and 12 · PPO done); other steps get their own visual example | ✅ ch. 01–04, 06, 11, 12 |
| 06 | [Probability, Bayes & ROC vs PR](https://github.com/kavicka/06-probability-bayes-roc) | Variance of a mean ~1/n, Bayes on a 1 % disease (positive test → 16.7 %), same model ROC-AUC 0.92 at 50 % and 0.1 % positives while precision falls 87 % → 0.6 % | ✅ |
| 07 | [Tabular ML: customer churn (P2)](https://github.com/kavicka/07-churn-tabular-ml) | Telco churn: tuned LightGBM PR-AUC 0.664 vs 0.265 naive, oversampling leakage (CV 0.89 vs real 0.64), threshold from costs catches 68 % of churners at 118 € vs 133 € per customer, FastAPI endpoint | ✅ |
| 08 | [MLE, softmax, cross-entropy & KL](https://github.com/kavicka/08-mle-cross-entropy-kl) | Math before P4: minimising cross-entropy lands exactly on the MLE (NLL = CE to 8.9e-16, loss floor = data entropy 1.652), gradient = softmax − one-hot, forward vs reverse KL | ✅ |
| 09 | [Low-rank, SVD & LoRA](https://github.com/kavicka/09-low-rank-svd-lora) | Math before P5: top 8 singular values hold 91.7 % of a photo, full fine-tuning update keeps 86 % energy in 8 directions, LoRA r=8 reaches 95.9 % vs 96.9 % full FT with a third of the parameters | ✅ |
| 10 | [Norms & cosine similarity](https://github.com/kavicka/10-norms-cosine-similarity) | Math before P6: on unit vectors dot = cosine = L2 ranking (100 % identical top-10), raw dot prefers long documents, bge-m3 vectors have norm 1.0000 | ✅ |
| 11 | [P3: Image classifier in PyTorch](https://github.com/kavicka/11-image-classifier-pytorch) | Own training loop on MPS: ResNet-20 from scratch on CIFAR-10 (91.35 % vs 40.04 % linear), transfer learning on 10 Food-101 classes (94.76 % vs 75.08 % from scratch), 37 MLflow runs, Grad-CAM, ONNX | ✅ |
| 12 | [P4: GPT from scratch on Slovak](https://github.com/kavicka/12-gpt-from-scratch-sk) | Own BPE tokenizer (2.36 tokens per Slovak word vs 3.39 for GPT-2) and a 13.8M-parameter GPT trained on Slovak Wikipedia on MPS: perplexity 20.0 vs 136.4 bigram, KV cache 4.7× on CPU, attention heatmaps | ✅ |
| 13 | [P5: Fine-tuning a small model: LoRA vs DPO](https://github.com/kavicka/13-finetuning-lora-dpo-sk) | Qwen3-1.7B extracts JSON from synthetic Slovak insurance claims: micro F1 0.968 with LoRA vs 0.812 zero-shot and 0.885 few-shot, valid JSON 24 % → 100 % in Ollama at 0.83 s per report, DPO adds nothing measurable (0.964), 25 examples already beat the prompt | ✅ |
| 14 | [P6: Embeddings & retrieval](https://github.com/kavicka/14-embeddings-retrieval-sk) | Retrieval on Slovak insurance terms, 141 hand-reviewed questions from unseen insurers: recall@5 BM25 0.191, bge-m3 0.574, fine-tuned (in-batch) 0.674, but validation picked the hard-negative model (0.617, no provable gain). Own brute-force vs HNSW on 200k vectors: 5.45 ms vs 0.19 ms at recall 0.955 | ✅ |
| 15 | [P7: RAG app: FastAPI + React](https://github.com/kavicka/15-rag-fullstack-clinical) | 396 public clinical trials, FastAPI + SSE + React/TypeScript UI with citations: answers 15.9 % correct with the LLM alone → 96.8 % with hybrid search + reranker (Qwen3-1.7B), passage with the answer at rank 1 for 42 % (BM25) → 86 % (reranker), 0 made-up citations | ✅ |
| 16 | [P8: AI agent from scratch + MCP server](https://github.com/kavicka/16-agent-mcp-clinical) | Agent loop with 4 typed ClinicalTrials.gov tools, the same tools as an MCP server (SDK 2.x): 33 multi-step tasks with Qwen3-1.7B, 0 % LLM alone → 69.7 % agent → 93.9 % after rewriting the tool descriptions, same 93.9 % over MCP once the stdio server gets its environment | ✅ |
| 17 | [Containers, Kubernetes, CI/CD & Terraform](https://github.com/kavicka/17-containers-k8s-cicd) | Step 15 as qdrant + indexer job + api + web: onnxruntime (63 MB) instead of PyTorch (5.1 GB) with identical retrieval, compose + kind in GitHub Actions with a retrieval eval gate, Terraform platform layer; a rolling restart lost 3 / 819 requests until a preStop hook made it 0 / 864 | ✅ |
| 20 | [GxP document migration & app retirement](https://github.com/kavicka/20-gxp-document-migration) | 294 legacy documents with 45 injected defects into a Vault-like DMS: lift-and-shift loads 40 defective documents and 0 % fully correct records, the validated pipeline quarantines 45 / 45 with a reason and rejects 0 clean ones; hash-chained audit trail, CTMS archive kept 25 years, 13 / 13 requirements verified | ✅ |

### Planned: GenAI full-stack track (steps 18–19)
The two remaining steps put the same app on AWS and Azure. Every secret (API keys, cloud credentials) is read from the environment, never committed.

| # | Project | What it will show | Status |
|---|---|---|---|
| 18 | AWS on the free plan | S3 → Lambda → index pipeline, API Gateway, DynamoDB, all in Terraform; keys in SSM Parameter Store, CI via OIDC (no long-lived keys), budget alarm | ⏳ planned |
| 19 | Azure AI: same RAG on Azure | Step 15 behind one provider interface (`ollama`, `bedrock` or `azure_openai`, chosen in `.env`); Azure OpenAI + Azure AI Search instead of Qdrant, deployed with Terraform; a few test questions only, to stay at 0 €; local vs Azure on quality, latency and cost per answer | ⏳ planned |

## Roadmap
1. **Setup & math** – environment, derivatives, linear algebra
2. **ML fundamentals** – autograd from scratch, tabular ML (churn), image classifier
3. **Deep learning & transformers** – GPT from scratch in Slovak, LoRA/DPO fine-tuning, embeddings & retrieval
4. **AI engineering** – full-stack RAG (FastAPI + React), agents & MCP, observability and guardrails, GxP document migration
5. **Serving & MLOps** – containers, Kubernetes, CI/CD, Terraform, AWS, Azure, inference optimization
6. **Capstone** – end-to-end GenAI system on clinical-trial data (combines steps 15–20)

## Conventions
- Every project runs with `uv sync && uv run python <script>.py`.
- Every project has a baseline, a metric and a results table.
- Plots and screenshots live in each project's `assets/` folder.
- The main README is in English (`README.md`); a Slovak version lives in `README.sk.md`.
- New steps start from the template repo [`ml-project-template`](https://github.com/kavicka/ml-project-template).
