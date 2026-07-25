---
language:
- en
license: apache-2.0
size_categories:
- 10B<n<100B
task_categories:
- text-generation
pretty_name: UltraX
tags:
- llm
- pretraining
- web-corpus
- data-refinement
- programmatic-editing
- function-calling
configs:
- config_name: UltraX-FineWeb
  data_files:
  - split: train
    path: data/UltraX-FineWeb/*
- config_name: UltraX-RedPajama-V2
  data_files:
  - split: train
    path: data/UltraX-RedPajama-V2/*
- config_name: UltraX-AICC
  data_files:
  - split: train
    path: data/UltraX-AICC/*
- config_name: UltraX-Ultra-FineWeb
  data_files:
  - split: train
    path: data/UltraX-Ultra-FineWeb/*
- config_name: UltraX-FineWeb-ProX-Doc
  data_files:
  - split: train
    path: data/UltraX-FineWeb-ProX-Doc/*
features:
- name: uid
  dtype: string
- name: raw_content
  dtype: string
- name: cleaned_content
  dtype: string
- name: processed_functions
  dtype: string
- name: source
  dtype: string
---

# UltraX: Refining Pre-Training Data at Scale with Adaptive Programmatic Editing

<p align="center">
  <a href="https://huggingface.co/collections/openbmb/ultradata">
    <img src="https://raw.githubusercontent.com/OpenBMB/UltraX/main/assets/ultradata-logo.png" alt="OpenBMB UltraData" width="350"/>
  </a>
  <br/>
  <a href="https://huggingface.co/collections/openbmb/ultradata">
    <img src="https://raw.githubusercontent.com/OpenBMB/UltraX/main/assets/ultrax-logo.png" alt="UltraX Logo" width="350"/>
  </a>
</p>

<p align="center">
<a href="https://arxiv.org/abs/2607.08646">📜 Paper</a> |
<a href="https://github.com/openbmb/UltraX">💻 Code</a> |
<a href="https://huggingface.co/openbmb/UltraX-0.6B-Preview">🤖 Models</a> |
<a href="https://huggingface.co/collections/openbmb/ultradata">📦 UltraData Collection</a>
</p>

<p align="center">
English |
<a href="https://huggingface.co/datasets/openbmb/UltraX-Preview/blob/main/README_ZH.md">中文</a>
</p>

## 📚 Introduction

**UltraX** is a function-calling refinement framework for large-scale pre-training data that adaptively generates and executes editing functions for efficient instance-wise refinement. Unlike rule-based or end-to-end LLM rewriting methods, UltraX trains a lightweight refinement model to predict structured editing operations — including insertion, deletion, and modification — which are then deterministically executed on the original text.

This dataset collection contains **five English pre-training corpora refined by UltraX**, each with ~20B tokens:

| Dataset | Source Corpus | Description |
|---------|--------------|-------------|
| [UltraX-FineWeb](https://huggingface.co/datasets/openbmb/UltraX-Preview/tree/main/data/UltraX-FineWeb/) | [FineWeb](https://huggingface.co/datasets/HuggingFaceFW/fineweb) | Large-scale Common Crawl web corpus |
| [UltraX-RedPajama-V2](https://huggingface.co/datasets/openbmb/UltraX-Preview/tree/main/data/UltraX-RedPajama-V2/) | [RedPajama-v2](https://huggingface.co/datasets/togethercomputer/RedPajama-Data-V2) | Multi-source web corpus |
| [UltraX-AICC](https://huggingface.co/datasets/openbmb/UltraX-Preview/tree/main/data/UltraX-AICC/) | [AICC](https://huggingface.co/datasets/opendatalab/AICC) | HTML-parsed high-fidelity web corpus |
| [UltraX-Ultra-FineWeb](https://huggingface.co/datasets/openbmb/UltraX-Preview/tree/main/data/UltraX-Ultra-FineWeb/) | [Ultra-FineWeb](https://huggingface.co/datasets/openbmb/Ultra-FineWeb) | Quality-filtered FineWeb corpus |
| [UltraX-FineWeb-ProX-Doc](https://huggingface.co/datasets/openbmb/UltraX-Preview/tree/main/data/UltraX-FineWeb-ProX-Doc/) | [FineWeb-ProX-Doc](https://huggingface.co/gair-prox) | ProX document-level refined corpus |

## 📢 News

- **[2026.07.17]** **UltraX** tops the Hugging Face Datasets Trending list, reaching the #1 spot! ⭐️⭐️⭐️
- **[2026.07.13]** **UltraX** codebase, refinement model, and refined datasets are now available on GitHub and Hugging Face. 🚀🚀🚀
- **[2026.07.10]** **UltraX** technical report is available on [arXiv](https://arxiv.org/abs/2607.08646). 🔥🔥🔥

## 💡 Highlights

- **Function-Calling Refinement:** Instead of end-to-end text rewriting, UltraX predicts structured editing operations (`keep_all`, `remove_all`, `remove_lines`, `replace_str`, `add_line`), enabling fine-grained instance-level editing with deterministic execution.
- **LAM + DCR Pipeline:** Line Alignment and Mapping (LAM) aligns original and refined text at line level, while Dynamic Context Replacement (DCR) converts character-level edits into reliable `replace_str` operations with unique context anchoring.
- **Robust Large-Scale Execution:** Sliding-window inference with overlap-aware aggregation, ambiguity filtering, same-line operation merging, and duplicate pattern detection ensure reliable execution at scale.
- **State-of-the-Art Performance:** UltraX achieves the best average performance across all five corpora in 1B-model pre-training experiments, with improvements exceeding 2% on multiple datasets and superior data efficiency.

## 🔬 Pipeline Overview

<div align="center">
  <img src="https://raw.githubusercontent.com/OpenBMB/UltraX/main/assets/ultrax_pipeline.png" width="800"/>
</div>

## 📈 Evaluation Results

We pretrain 1B-parameter MiniCPM models from scratch on 20B tokens for each corpus and evaluate on 10 benchmarks (ARC-C, ARC-E, CSQA, HellaSwag, MMLU, OBQA, PIQA, SIQA, WinoGrande, SciQ) using LightEval with zero-shot setting.

<div align="center">
  <img src="https://raw.githubusercontent.com/OpenBMB/UltraX/main/assets/results.png" width="900"/>
</div>

**Key findings:**
- UltraX achieves the **highest average performance on all five corpora**, winning 34 out of 50 task-corpus pairs.
- Compared to Raw and ProX-C, UltraX achieves average relative improvements of ~2.00% and ~1.53%, respectively.
- On FineWeb, UltraX at 16B tokens (45.49) already surpasses Raw and ProX-C at 20B tokens (45.08 / 45.05), demonstrating superior data efficiency.

<div align="center">
  <img src="https://raw.githubusercontent.com/OpenBMB/UltraX/main/assets/fineweb_token_curve.png" alt="FineWeb Token Curve" width="450"/>
  <p><i>Average downstream performance on FineWeb under different training token budgets.</i></p>
</div>

## 📊 Data Format

Each parquet file contains 5 columns:

| Column | Type | Description |
|--------|------|-------------|
| `uid` | string | Unique identifier (MD5 hash of raw_content) |
| `raw_content` | string | Original text before refinement |
| `cleaned_content` | string | Text after UltraX refinement |
| `processed_functions` | string | The editing operations applied |
| `source` | string | Source corpus name |

## 🚀 Quick Start

You can load the dataset directly from Hugging Face:

```python
from datasets import load_dataset

# Load UltraX-FineWeb
ds = load_dataset("openbmb/UltraX", "UltraX-FineWeb", split="train")

# Load UltraX-RedPajama-V2
ds = load_dataset("openbmb/UltraX", "UltraX-RedPajama-V2", split="train")

# Load UltraX-AICC
ds = load_dataset("openbmb/UltraX", "UltraX-AICC", split="train")

# Load UltraX-Ultra-FineWeb
ds = load_dataset("openbmb/UltraX", "UltraX-Ultra-FineWeb", split="train")

# Load UltraX-FineWeb-ProX-Doc
ds = load_dataset("openbmb/UltraX", "UltraX-FineWeb-ProX-Doc", split="train")
```

## 🔧 Function Space

The UltraX refinement model predicts operations from the following function space:

| Function | Description |
|----------|-------------|
| `keep_all()` | Document needs no modification |
| `remove_all()` | Entire document is valueless (e.g., error pages, login walls) |
| `remove_lines(start, end)` | Remove consecutive lines from start to end (inclusive) |
| `replace_str(line, old, new)` | Replace a substring within a specific line |
| `add_line(base, sub_idx, content)` | Insert a new line near the base position |

## ❤️ Acknowledgements

- The UltraX datasets are built upon [FineWeb](https://huggingface.co/datasets/HuggingFaceFW/fineweb), [RedPajama-v2](https://huggingface.co/datasets/togethercomputer/RedPajama-Data-V2), [AICC](https://huggingface.co/datasets/opendatalab/AICC), [Ultra-FineWeb](https://huggingface.co/datasets/openbmb/Ultra-FineWeb), and [FineWeb-ProX-Doc](https://huggingface.co/gair-prox).
- The refinement model is trained using [ms-swift](https://github.com/modelscope/ms-swift).
- UltraX builds upon insights from [ProX](https://github.com/GAIR-NLP/ProX) and RefineX.

Thanks for their awesome work! Open-source contributions make UltraX possible! 🙌

## 📖 Citation

If you find our work useful, please consider citing:

```bibtex
@misc{ultrax2026,
  title={UltraX: Refining Pre-Training Data at Scale with Adaptive Programmatic Editing},
  author={Xinlong Zhao and Dongsheng Liu and Hengyu Zhao and Zixuan Fu and Zheng Wang and Jie Cai and Jie Zhou and Qiang Ma and Xuanhe Zhou and Xu Han and Yudong Wang and Zhiyuan Liu},
  year={2026},
  eprint={2607.08646},
  archivePrefix={arXiv},
  primaryClass={cs.CL},
}
```

## 📜 License

This project is licensed under the [Apache 2.0](https://huggingface.co/datasets/openbmb/UltraX-Preview/blob/main/LICENSE) license. Please note that since UltraX datasets are built upon multiple source corpora, users should check the **LICENSE of each source dataset** individually to ensure proper usage and compliance.

**No unauthorized unchanged redistribution:** Without prior written permission from the original authors (or this organization), any institution, organization, or third-party platform is strictly prohibited from directly reposting, mirroring, re-hosting, or commercially repackaging and republishing any artifacts of this project in any form.
