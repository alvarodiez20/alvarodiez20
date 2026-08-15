## Álvaro Diez de Pablos

**AI Platform Engineer at BNP Paribas.** I build and run our internal coding agent — a Claude Code style CLI that our engineers use every day, at billions of tokens a month in production. I own the harness behind it: the tool-calling loop, sessions and checkpointing, context engineering and compaction, permissioning and cost control.

Before agents I spent five years on the less glamorous half of this job: MLOps at BNP Paribas, where I took model retraining and deployment from months down to hours, and before that a wind power forecasting system processing terabytes a day of meteorological data.

I also teach Big Data to fourth-year Mathematics students at UNIE.

---

### What I'm building

#### [endstate](https://github.com/alvarodiez20/endstate) — agent evals that grade the end state, not the output

Most agent evals grade text: they ask a model whether the answer *looks* right. That's cheap to build and easy to game. `endstate` throws away everything the agent said and asserts against what it left behind — did the test suite go green, is there a secret in the diff, did it refuse the destructive command, did it survive being killed halfway through.

The end state is gameable too, which is the half most write-ups skip. So every task pins its test files by hash, refuses new skip markers, confines changes to permitted paths, and runs held-out tests that were never in the sandbox.

**22 tasks** in disposable Docker containers · deterministic graders that never see the transcript, enforced by signature · a **mutation check** that removes each guard and proves the suite notices · 344 tests · `mypy --strict`

```bash
pip install endstate
```

[Docs](https://alvarodiez20.github.io/endstate/) · [How agents actually work](https://alvarodiez20.github.io/endstate/concepts/) — a walk through harness internals: the loop, the sandbox boundary, permissioning, compaction, checkpoint durability

#### [pysuricata](https://github.com/alvarodiez20/pysuricata) — exploratory data analysis built on streaming algorithms

Profiles a DataFrame in a **single pass**, with memory that stays bounded no matter how large the data is. Welford/Pébay for exact moments, KMV sketches for distinct counts, Misra-Gries for heavy hitters, reservoir sampling for quantiles. Pandas, Polars and LazyFrames; output is one self-contained HTML file with no external assets.

```bash
pip install pysuricata
```

[Docs](https://alvarodiez20.github.io/pysuricata/) · [Live example report](https://alvarodiez20.github.io/pysuricata/assets/titanic_report.html) · [Statistical methods](https://alvarodiez20.github.io/pysuricata/stats/overview/)

#### [Big Data course labs](https://github.com/alvarodiez20/bigdata) — open materials for the course I teach at UNIE

Out-of-core computing and storage formats, streaming and sketching algorithms, distributed systems from first principles, Spark, Airflow, Slurm.

#### [cka-practice](https://github.com/alvarodiez20/cka-practice) — eleven mock CKA exams solved against a real cluster

The grader inspects the cluster's actual state, not an answer key. Same idea as `endstate`, applied to Kubernetes.

---

Also, for fun: **[2048](https://alvarodiez20.github.io/2048/)** — RL agents (DQN, CNN) trained with PyTorch on MPS, Rust core compiled to WebAssembly. And **[Tetris](https://alvarodiez20.github.io/tetris/)** — pure-Rust engine in WASM with SRS wall kicks, 7-bag randomiser, and AI opponents.

---

### Stack

**Languages** Python · SQL · Bash

**Agents & LLM** LangGraph · Pydantic-AI · MCP · harness design · context engineering · tool-calling loops · sessions & checkpointing · token budgeting & cost control · evals · RAG

**Platform & infra** Kubernetes (CKA) · Docker · Terraform · GitOps · GitLab CI/CD · GitHub Actions · Domino Data Lab · JFrog Artifactory · FastAPI · Linux

**Data & ML** MLflow · PyTorch · TensorFlow · scikit-learn · XGBoost · Spark · Airflow · Dask · Xarray · Kafka · PostgreSQL · S3 · pandas · Polars · NumPy · streaming algorithms

**Engineering** uv · Pytest · Coverage.py · Ruff · `mypy --strict` · Pydantic · pre-commit · Conventional Commits · MkDocs · trunk-based development

### Education & certifications

- **MSc Industrial Mathematics** (M2i), modelling specialisation — Universidad Carlos III de Madrid
- **BSc Mechanical Engineering** (bilingual) — Universidad Carlos III de Madrid, with an exchange year at Purdue University
- **CKA: Certified Kubernetes Administrator** — CNCF
- **Deep Learning Specialization & MLOps Engineering for Production** — DeepLearning.AI

### Reach out

[LinkedIn](https://www.linkedin.com/in/alvarodiez20/) · alvarodiez20@gmail.com
