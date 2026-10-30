# ai-ml-learning

🇬🇧 [English version](README.md)

Moja cesta od základov ML po AI engineering. **Tento repozitár je len rozcestník.** Každý krok roadmapy je samostatný privátny repozitár s vlastným prostredím, kódom, výsledkami a popisom; tabuľka na ne odkazuje.

| # | Projekt | Čo ukazuje | Stav |
|---|---|---|---|
| 01 | [Setup a benchmark násobenia matíc](https://github.com/kavicka/01-setup-benchmark/blob/main/README.sk.md) | Reprodukovateľné prostredie `uv` + PyTorch, benchmark CPU/MPS/CUDA, škálovanie O(n³) | ✅ |
| 02 | [Derivácie a chain rule](https://github.com/kavicka/02-calculus-chain-rule/blob/main/README.sk.md) | Ručný backprop vs numericky vs PyTorch autograd na malom grafe, chyba konečných diferencií vs h | ✅ |
| 03 | [Vektory, matice a tvary](https://github.com/kavicka/03-linear-algebra-shapes/blob/main/README.sk.md) | Násobenie matíc od nuly vs NumPy, pravidlá tvarov až po (B,T,C)@(C,H), tvary v attention, matice ako transformácie | ✅ |
| 04 | [P1: Autograd od nuly a makemore](https://github.com/kavicka/04-autograd-makemore/blob/main/README.sk.md) | Vlastný autograd engine testovaný proti PyTorch, MLP nad ním, znakový model pre názvy obcí SR (val NLL 2,46 bigram → 1,95 MLP) | ✅ |
| 05 | [Racing Lab: autíčka, ktoré sa učia jazdiť](https://github.com/kavicka/05-racing-lab/blob/main/README.sk.md) | Pretekárske laboratórium v pygame, ktoré rastie s roadmapou: každý vhodný krok má kapitolu na autíčkach (kap. 01–04 a 06 hotové); ostatné kroky majú vlastný vizuálny príklad | ✅ kap. 01–04, 06 |
| 06 | [Pravdepodobnosť, Bayes a ROC vs PR](https://github.com/kavicka/06-probability-bayes-roc/blob/main/README.sk.md) | Rozptyl priemeru ~1/n, Bayes pri 1 % chorých (pozitívny test → 16,7 %), ten istý model má ROC-AUC 0,92 pri 50 % aj 0,1 % pozitívnych, pritom precision padne z 87 % na 0,6 % | ✅ |
| 07 | [Tabulárne ML: odchod zákazníkov (P2)](https://github.com/kavicka/07-churn-tabular-ml/blob/main/README.sk.md) | Telco churn: vyladený LightGBM PR-AUC 0,664 vs 0,265 naivný, leakage z oversamplingu (CV 0,89 vs reálne 0,64), prah z nákladov zachytí 68 % odchádzajúcich za 118 € vs 133 € na zákazníka, FastAPI endpoint | ✅ |
| 08 | [MLE, softmax, cross-entropy a KL](https://github.com/kavicka/08-mle-cross-entropy-kl/blob/main/README.sk.md) | Matematika pred P4: minimalizácia cross-entropy skončí presne na MLE (NLL = CE na 8,9e-16, dno lossu = entropia dát 1,652), gradient = softmax − one-hot, forward vs reverse KL | ✅ |
| 09 | [Low-rank, SVD a LoRA](https://github.com/kavicka/09-low-rank-svd-lora/blob/main/README.sk.md) | Matematika pred P5: 8 najväčších singulárnych hodnôt drží 91,7 % fotky, zmena z plného fine-tuningu má 86 % energie v 8 smeroch, LoRA r=8 dosiahne 95,9 % vs 96,9 % pri plnom FT s tretinou parametrov | ✅ |
| 10 | [Normy a cosine similarity](https://github.com/kavicka/10-norms-cosine-similarity/blob/main/README.sk.md) | Matematika pred P6: na jednotkových vektoroch dá súčin = cosine = L2 rovnaké poradie (100 % rovnakých top-10), surový súčin uprednostňuje dlhé dokumenty, vektory bge-m3 majú normu 1,0000 | ✅ |

## Roadmapa
1. **Setup a matematika** – prostredie, derivácie, lineárna algebra
2. **Základy ML** – autograd od nuly, tabulárne ML (churn), klasifikátor obrázkov
3. **Deep learning a transformery** – GPT od nuly v slovenčine, LoRA/DPO fine-tuning, embeddings a retrieval
4. **AI engineering** – RAG riadený evalmi, agenty a MCP, observability a guardrails
5. **Serving a MLOps** – optimalizácia inferencie, end-to-end ML systém
6. **Capstone** – ClaimPilot v2

## Konvencie
- Každý projekt sa spúšťa cez `uv sync && uv run python <skript>.py`.
- Každý projekt má baseline, metriku a tabuľku výsledkov.
- Grafy a screenshoty sú v priečinku `assets/` každého projektu.
- Hlavné README je v angličtine (`README.md`), slovenská verzia je v `README.sk.md`.
- Nové kroky začínajú zo šablóny [`ml-project-template`](https://github.com/kavicka/ml-project-template).
