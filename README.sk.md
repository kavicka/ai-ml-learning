# ai-ml-learning

🇬🇧 [English version](README.md)

Moja cesta od základov ML po AI engineering: každý priečinok je jeden krok roadmapy s vlastným prostredím, kódom, výsledkami a popisom.

| # | Projekt | Čo ukazuje | Stav |
|---|---|---|---|
| 01 | [Setup a benchmark násobenia matíc](01-setup-benchmark/README.sk.md) | Reprodukovateľné prostredie `uv` + PyTorch, benchmark CPU/MPS/CUDA, škálovanie O(n³) | ✅ |
| 02 | [Derivácie a chain rule](02-calculus-chain-rule/README.sk.md) | Ručný backprop vs numericky vs PyTorch autograd na malom grafe, chyba konečných diferencií vs h | ✅ |
| 03 | [Vektory, matice a tvary](03-linear-algebra-shapes/README.sk.md) | Násobenie matíc od nuly vs NumPy, pravidlá tvarov až po (B,T,C)@(C,H), tvary v attention, matice ako transformácie | ✅ |
| 04 | [P1: Autograd od nuly a makemore](04-autograd-makemore/README.sk.md) | Vlastný autograd engine testovaný proti PyTorch, MLP nad ním, znakový model pre názvy obcí SR (val NLL 2,46 bigram → 1,95 MLP) | ✅ |
| 05 | [Racing Lab: autíčka, ktoré sa učia jazdiť](05-racing-lab/README.sk.md) | Pretekárske laboratórium v pygame, ktoré rastie s roadmapou: každý vhodný krok má kapitolu na autíčkach (kap. 01–04 hotové); ostatné kroky majú vlastný vizuálny príklad | ✅ kap. 01–04 |

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
