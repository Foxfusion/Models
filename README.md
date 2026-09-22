# Models

Reusable AI/ML model training, evaluation, inference, and registry workspace.

This repository is intentionally separate from the other FoxFusion AI repositories:

- **AI_Fox_Project** — agents, RAG, prompts, tools, workflows, and experiments
- **Models** — reusable model training/evaluation/inference code
- **Project-Nurv** — standalone local LLM chat application

## Structure

```text
Models/
├── training/      # training pipelines and reusable trainers
├── evaluation/    # metrics, benchmarks, and evaluation harnesses
├── inference/     # model loading and serving/inference helpers
├── registry/      # MLflow/model-registry integration
├── configs/       # non-secret configuration templates
├── notebooks/     # exploration and experiments
└── tests/         # automated tests
```

## Recommended workflow

1. Prototype model ideas in `notebooks/`.
2. Move reusable training logic into `training/`.
3. Put evaluation code in `evaluation/`.
4. Put reusable prediction/serving logic in `inference/`.
5. Track experiments and model versions with MLflow or another model registry.
6. Promote complete end-user applications into their own repository instead of turning this repo into a monolith.

## Storage rules

Do **not** commit:

- model weights
- checkpoints
- large datasets
- customer/private data
- API keys or passwords
- `.env` files

Use MLflow, Hugging Face, MinIO/S3, or another artifact store for model binaries and large artifacts.

## Python setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
