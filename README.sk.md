# ai-ml-learning

🇬🇧 [English version](README.md)

Moja cesta od základov ML po AI engineering. **Tento repozitár je len rozcestník.** Každý krok roadmapy je samostatný privátny repozitár s vlastným prostredím, kódom, výsledkami a popisom; tabuľka na ne odkazuje.

Každé projektové README teraz začína jednoduchým vysvetlením pred technickými detailmi. Po kliknutí na projekt nájdeš konkrétne príklady, namerané výsledky, grafy aj anglickú verziu.

| # | Projekt | Čo ukazuje | Stav |
|---|---|---|---|
| 01 | [Setup a benchmark násobenia matíc](https://github.com/kavicka/01-setup-benchmark/blob/main/README.sk.md) | Reprodukovateľné prostredie `uv` + PyTorch, benchmark CPU/MPS/CUDA, škálovanie O(n³) | ✅ |
| 02 | [Derivácie a chain rule](https://github.com/kavicka/02-calculus-chain-rule/blob/main/README.sk.md) | Ručný backprop vs numericky vs PyTorch autograd na malom grafe, chyba konečných diferencií vs h | ✅ |
| 03 | [Vektory, matice a tvary](https://github.com/kavicka/03-linear-algebra-shapes/blob/main/README.sk.md) | Násobenie matíc od nuly vs NumPy, pravidlá tvarov až po (B,T,C)@(C,H), tvary v attention, matice ako transformácie | ✅ |
| 04 | [P1: Autograd od nuly a makemore](https://github.com/kavicka/04-autograd-makemore/blob/main/README.sk.md) | Vlastný autograd engine testovaný proti PyTorch, MLP nad ním, znakový model pre názvy obcí SR (val NLL 2,46 bigram → 1,95 MLP) | ✅ |
| 05 | [Racing Lab: autíčka, ktoré sa učia jazdiť](https://github.com/kavicka/05-racing-lab/blob/main/README.sk.md) | Pretekárske laboratórium v pygame, ktoré rastie s roadmapou: každý vhodný krok má kapitolu na autíčkach (kap. 01–04, 06, 11 a 12 · PPO hotové); ostatné kroky majú vlastný vizuálny príklad | ✅ kap. 01–04, 06, 11, 12 |
| 06 | [Pravdepodobnosť, Bayes a ROC vs PR](https://github.com/kavicka/06-probability-bayes-roc/blob/main/README.sk.md) | Rozptyl priemeru ~1/n, Bayes pri 1 % chorých (pozitívny test → 16,7 %), ten istý model má ROC-AUC 0,92 pri 50 % aj 0,1 % pozitívnych, pritom precision padne z 87 % na 0,6 % | ✅ |
| 07 | [Tabulárne ML: odchod zákazníkov (P2)](https://github.com/kavicka/07-churn-tabular-ml/blob/main/README.sk.md) | Telco churn: vyladený LightGBM PR-AUC 0,664 vs 0,265 naivný, leakage z oversamplingu (CV 0,89 vs reálne 0,64), prah z nákladov zachytí 68 % odchádzajúcich za 118 € vs 133 € na zákazníka, FastAPI endpoint | ✅ |
| 08 | [MLE, softmax, cross-entropy a KL](https://github.com/kavicka/08-mle-cross-entropy-kl/blob/main/README.sk.md) | Matematika pred P4: minimalizácia cross-entropy skončí presne na MLE (NLL = CE na 8,9e-16, dno lossu = entropia dát 1,652), gradient = softmax − one-hot, forward vs reverse KL | ✅ |
| 09 | [Low-rank, SVD a LoRA](https://github.com/kavicka/09-low-rank-svd-lora/blob/main/README.sk.md) | Matematika pred P5: 8 najväčších singulárnych hodnôt drží 91,7 % fotky, zmena z plného fine-tuningu má 86 % energie v 8 smeroch, LoRA r=8 dosiahne 95,9 % vs 96,9 % pri plnom FT s tretinou parametrov | ✅ |
| 10 | [Normy a cosine similarity](https://github.com/kavicka/10-norms-cosine-similarity/blob/main/README.sk.md) | Matematika pred P6: na jednotkových vektoroch dá súčin = cosine = L2 rovnaké poradie (100 % rovnakých top-10), surový súčin uprednostňuje dlhé dokumenty, vektory bge-m3 majú normu 1,0000 | ✅ |
| 11 | [P3: Klasifikátor obrázkov v PyTorchi](https://github.com/kavicka/11-image-classifier-pytorch/blob/main/README.sk.md) | Vlastný trénovací cyklus na MPS: ResNet-20 od nuly na CIFAR-10 (91,35 % vs 40,04 % lineárny), transfer learning na 10 triedach Food-101 (94,76 % vs 75,08 % od nuly), 37 behov v MLflow, Grad-CAM, ONNX | ✅ |
| 12 | [P4: GPT od nuly na slovenčine](https://github.com/kavicka/12-gpt-from-scratch-sk/blob/main/README.sk.md) | Vlastný BPE tokenizer (2,36 tokenu na slovenské slovo vs 3,39 pri GPT-2) a GPT s 13,8M parametrov natrénovaný na slovenskej Wikipédii na MPS: perplexita 20,0 vs 136,4 bigram, KV cache 4,7× na CPU, heatmapy attention | ✅ |
| 13 | [P5: Doladenie malého modelu: LoRA vs DPO](https://github.com/kavicka/13-finetuning-lora-dpo-sk/blob/main/README.sk.md) | Qwen3-1.7B vyťahuje JSON zo syntetických slovenských hlásení poistných udalostí: micro F1 0,968 s LoRA vs 0,812 zero-shot a 0,885 few-shot, platný JSON 24 % → 100 % v Ollame za 0,83 s na hlásenie, DPO nepridá nič merateľné (0,964), už 25 príkladov porazí prompt | ✅ |
| 14 | [P6: Embeddingy a vyhľadávanie](https://github.com/kavicka/14-embeddings-retrieval-sk/blob/main/README.sk.md) | Vyhľadávanie v slovenských poistných podmienkach, 141 ručne skontrolovaných otázok od nevidených poisťovní: recall@5 BM25 0,191, bge-m3 0,574, doladený (in-batch) 0,674, no validácia vybrala model s hard negatives (0,617, bez preukázateľného zlepšenia). Vlastný brute-force vs HNSW na 200k vektoroch: 5,45 ms vs 0,19 ms pri recall 0,955 | ✅ |

### Plánované: GenAI full-stack séria (kroky 15–20)
Ďalšie kroky pokrývajú to, čo chce GenAI full-stack pozícia: RAG, agentov, MCP, React, kontajnery, AWS, Azure a nasadzovanie v regulovanom (GxP) prostredí. Používajú verejné dáta o klinických štúdiách (ClinicalTrials.gov, openFDA) a všetky tajomstvá (API kľúče, AWS prístupy) sa čítajú z prostredia, nikdy nie sú v gite.

| # | Projekt | Čo bude ukazovať | Stav |
|---|---|---|---|
| 15 | P7: RAG aplikácia: FastAPI + React | Chunking, hybridné vyhľadávanie (BM25 + vektory), reranking, odpovede s citáciami, streamované React/TypeScript UI; LLM bez vyhľadávania vs RAG na ručne skontrolovanom eval sete | ⏳ plánované |
| 16 | P8: AI agent a vlastný MCP server | Agent loop od nuly s volaním nástrojov, potom tie isté nástroje ako MCP server; úspešnosť úloh vs jeden prompt | ⏳ plánované |
| 17 | Kontajnery, mikroslužby a CI/CD | Krok 15 rozdelený na služby, docker compose, lokálny Kubernetes (kind), GitHub Actions s eval quality gate, Terraform | ⏳ plánované |
| 18 | AWS na free pláne | Pipeline S3 → Lambda → index, API Gateway, DynamoDB, všetko v Terraforme; kľúče v SSM Parameter Store, CI cez OIDC (žiadne dlhodobé kľúče), rozpočtový alarm | ⏳ plánované |
| 19 | Azure AI: ten istý RAG na Azure | Krok 15 za jedným rozhraním poskytovateľa (`ollama`, `bedrock` alebo `azure_openai`, volí sa v `.env`); Azure OpenAI + Azure AI Search namiesto Qdrantu, nasadené cez Terraform; iba pár testovacích otázok, aby to ostalo na 0 €; lokálne vs Azure v kvalite, latencii a cene za odpoveď | ⏳ plánované |
| 20 | GxP migrácia dokumentov a archivácia aplikácií | Migrácia z legacy systému do cieľového DMS s mapovaním metadát, validáciou, checksumami, audit trailom, dry runom a reconciliation reportom; archivácia vyradenej aplikácie; URS, testovacie skripty, traceability matica | ⏳ plánované |

## Roadmapa
1. **Setup a matematika** – prostredie, derivácie, lineárna algebra
2. **Základy ML** – autograd od nuly, tabulárne ML (churn), klasifikátor obrázkov
3. **Deep learning a transformery** – GPT od nuly v slovenčine, LoRA/DPO fine-tuning, embeddings a retrieval
4. **AI engineering** – full-stack RAG (FastAPI + React), agenti a MCP, observability a guardrails, GxP migrácia dokumentov
5. **Serving a MLOps** – kontajnery, Kubernetes, CI/CD, Terraform, AWS, Azure, optimalizácia inferencie
6. **Capstone** – end-to-end GenAI systém nad dátami klinických štúdií (spája kroky 15–20)

## Konvencie
- Každý projekt sa spúšťa cez `uv sync && uv run python <skript>.py`.
- Každý projekt má baseline, metriku a tabuľku výsledkov.
- Grafy a screenshoty sú v priečinku `assets/` každého projektu.
- Hlavné README je v angličtine (`README.md`), slovenská verzia je v `README.sk.md`.
- Nové kroky začínajú zo šablóny [`ml-project-template`](https://github.com/kavicka/ml-project-template).
