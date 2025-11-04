# D E L T A - > https://tinyurl.com/bdf8yy7u

# labtrek

🧪 LabTrek

LabTrek is a lightweight, script-friendly experiment tracker and results visualizer for machine learning workflows—perfect for research labs, Kaggle teams, and MLOps pipelines.

✨ Features

🧠 Smart logging – autolog parameters, model structure, and performance

📊 Rich metrics – time-series plots, confusion matrices, AUC, BLEU, etc.

📁 Versioned runs – YAML configs, Git-linked snapshots, checkpoint diffing

🔄 Repeatable pipelines – CLI & API experiment runners with seed control

🗃 Artifacts – store models, logs, configs, notebooks, charts

📡 Remote sync – push to S3, HuggingFace Spaces, or private server

🔌 Integrations – PyTorch Lightning, HuggingFace Transformers, Sklearn, XGBoost

📦 Installation

pip install labtrek
# or for notebooks
pip install labtrek[jupyter]


📍 Quick Start

labtrek init experiment.yaml
labtrek run experiment.yaml --tag baseline
labtrek ui


📄 Minimal experiment.yaml

experiment: sentiment_baseline
seed: 42
dataset: imdb_reviews
model:
type: transformers/bert-base-uncased
lr: 2e-5
epochs: 4
track:
metrics: [accuracy, f1, loss]
log_interval: 50
save_best: true
artifacts:
save: [model, tokenizer, config]


🧠 Auto Tracking

from labtrek import Tracker

with Tracker("imdb_run") as run:
run.log_param("lr", 2e-5)
run.watch(model)
for epoch in range(4):
run.log_metric("accuracy", acc, step=epoch)
run.save_artifact("model.pt")


📊 Visualize Results

labtrek ui


Dashboard at localhost:8000

Compare multiple runs, export charts as PNG/SVG

View training curves, confusion matrix, tables

🔗 Integration Examples

# PyTorch Lightning
from labtrek.integrations.pl import LabTrekLogger
trainer = Trainer(logger=LabTrekLogger("pl_exp"))

# HuggingFace
trainer = Trainer(callbacks=[LabTrekCallback("bert_finetune")])


📡 Remote Sync

labtrek sync --to s3://mybucket/labtrek
labtrek sync --to https://my.labtrek.server


🔍 Compare Experiments

labtrek compare --metric accuracy --top 5


🧪 Reproduce

labtrek run 20231018-bert-lr2e5 --reproduce


⚙️ Presets

gpu-a100 – auto batch scaling, mixed precision

nlp-finetune – standard huggingface trainer + tokenizer

cv-transfer – torchvision with pretrained backbones

🛠 Interop

Log directly to Weights & Biases, TensorBoard, or MLflow

Export tracked data:

labtrek export csv --metric accuracy --out acc_logs.csv


🛣 Roadmap

Hyperparameter sweeps with Optuna integration

Jupyter cell-level tracking

CLI dashboard viewer (TUI)

Team run tagging & annotations

🤝 Contributing

Fork

git checkout -b feat/sweet-new-feature

Add tests + docs

Submit a PR with a screenshot of your run 🧪📈

📜 License

Apache-2.0 © 2025 LabTrek Contributors
