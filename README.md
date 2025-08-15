# Custom LLM from Scratch

**Building language models one token at a time**

A hands-on project to implement a **decoder-only transformer** from scratch. This repository guides you through data preparation, tokenization, model initialization, training, and evaluation — end to end.

---

## 📂 Repository Structure

```text
.
├── code/                              # Core implementation (modules, helpers)
├── data/
│   └── TinySolar-308m-4k-init/        # Tokenizer & generation artifacts
│       ├── generation_config.json
│       ├── special_tokens_map.json
│       ├── tokenizer.model
│       └── tokenizer_config.json
├── .gitignore
├── Lesson_4.ipynb
├── Why Pretraining.ipynb
├── data packaging.html
├── data packaging.ipynb
├── data preparation.html
├── data preparation.ipynb
├── data_packing.png
├── model evaluation.ipynb
├── model initialization.html
├── model initialization.ipynb
├── model training test.html
├── model training.ipynb
├── requirements.txt
└── README.md
```

> **Note:** Several filenames include spaces (e.g., `data packaging.ipynb`). When using these in a terminal, wrap the path in quotes or escape spaces.

---

## 🚀 Quickstart

1. **Clone the repo**

```bash
git clone https://github.com/omarnahdi/pretraining-llm.git
cd pretraining-llm
```

2. **Create & activate a virtualenv**

```bash
python -m venv venv
# macOS / Linux
source venv/bin/activate
# Windows
venv\Scripts\activate
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Run Jupyter**

```bash
jupyter notebook
```

Open and run notebooks in this recommended order:

1. `data preparation.ipynb`
2. `data packaging.ipynb`
3. `model initialization.ipynb`
4. `model training.ipynb`
5. `model evaluation.ipynb`

---

## 🧩 Tokenizer & Generation Artifacts

Files inside `data/TinySolar-308m-4k-init/` are required for tokenization and generation:

* `tokenizer.model` — the trained SentencePiece/BPE tokenizer model (binary).
* `tokenizer_config.json` — tokenizer configuration (normalization, vocab size, special tokens).
* `special_tokens_map.json` — mapping for BOS/EOS/PAD/UNK, etc.
* `generation_config.json` — default generation settings (temperature, top\_p, max\_new\_tokens).

Keep these artifacts with the repository or update paths in the notebooks if you store them elsewhere.

---

## 🔬 Notebooks & Purpose

* **`data preparation.ipynb`** — dataset cleaning, normalization, and initial tokenization exploration.
* **`data packaging.ipynb`** — packing training sequences, creating TF/PyTorch-ready datasets.
* **`model initialization.ipynb`** — building model components: embeddings, positional encodings, attention, MLP.
* **`model training.ipynb`** — training loop, optimizer (AdamW), LR scheduling, checkpointing.
* **`model evaluation.ipynb`** — inference, generation examples, evaluation metrics and visualizations.

HTML exports (`*.html`) are included for quick reading without running the notebooks.

---

## 🛠 Key Implementation Notes

* The implementation uses a **decoder-only transformer** for causal language modeling (next-token prediction).
* Training loops are written to be readable and educational rather than hyper-optimized for large-scale training.
* Checkpoints and tokenizer artifacts are small/portable — verify `.gitignore` to avoid accidentally committing large parquet or dataset files.

---

## ✅ Best Practices

* When running long experiments, persist checkpoints and use small toy datasets for debugging.
* If you modify tokenizer artifacts, update `tokenizer_config.json` and `special_tokens_map.json` accordingly.
* Use the provided `generation_config.json` for reproducible sampling.

---

## 📈 Data Packing Visualization

![Data Packing Visualization](data_packing.png)

---

## 📚 Learning Outcomes

* Deep understanding of transformer internals and causal LM training.
* Practical knowledge of tokenizer creation, sequence packing, and training workflow.
* Ability to extend this codebase to fine-tune on new datasets or experiment with architecture changes.

---

## 📜 License

MIT License
