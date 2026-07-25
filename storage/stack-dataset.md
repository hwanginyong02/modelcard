---
thumbnail: "https://huggingface.co/datasets/HuggingFaceCode/stack-v3-train/resolve/main/assets/banner.png"
annotations_creators: []
language_creators:
- crowdsourced
- expert-generated
language:
- code
license:
- odc-by
multilinguality:
- multilingual
size_categories:
- 100M<n<1B
source_datasets: []
task_categories:
- text-generation
task_ids: []
pretty_name: The Stack v3
tags:
- code
dataset_info:
  features:
  - name: repo_path
    dtype: string
  - name: repo_id
    dtype: int64
  - name: commit_id
    dtype: string
  - name: github_metadata
    struct:
    - name: branch
      dtype: string
    - name: commit_count
      dtype: int32
    - name: repo_created_at
      dtype: string
    - name: is_fork
      dtype: bool
    - name: is_org_owned
      dtype: bool
    - name: forked_from
      dtype: string
    - name: stars
      dtype: int32
    - name: forks
      dtype: int32
    - name: issues
      dtype: int32
    - name: pull_requests
      dtype: int32
  - name: num_files
    dtype: int64
  - name: files
    list:
    - name: content_id
      dtype: string
    - name: content
      dtype: string
    - name: size_bytes
      dtype: int32
    - name: file_path
      dtype: string
    - name: file_timestamp
      dtype: int64
    - name: language
      dtype: string
    - name: is_vendor
      dtype: bool
    - name: license_type
      dtype: string
    - name: detected_licenses
      sequence: string
  splits:
  - name: train
configs:
- config_name: default
  data_files:
  - split: train
    path: data/*.parquet
---

<img src="./assets/banner.png" width="100%" alt="The Stack v3 banner">

# 🥞 The Stack v3

- [What is it?](#what-is-it)
- [What is being released](#what-is-being-released)
- [How to download and use it](#how-to-download-and-use-it)
- [Dataset statistics](#dataset-statistics)
- [Dataset structure](#dataset-structure)
- [Dataset creation](#dataset-creation)
- [Considerations for using the data](#considerations-for-using-the-data)
- [Additional information](#additional-information)

## What is it?

The Stack v3 is the **largest, most up-to-date open dataset of source code**, crawled directly from GitHub and built to pre-train code LLMs with full-repository context. It is the successor to [The Stack v2](https://huggingface.co/datasets/bigcode/the-stack-v2) and, like its predecessor, is released to make the training of code models more **open, reproducible, and transparent**.

If your code is included in this version and you would like it removed for any reason, please use the ["Am I in The Stack?"](https://huggingface.co/spaces/HuggingFaceCode/in-the-stack) Space to submit a removal request. Repositories that opted out are removed from the dataset before each patch release.

Two things set v3 apart from earlier releases of The Stack:

1. **The file contents are included inline.** The decoded UTF-8 source text is embedded directly in the dataset, so it is fully self-contained — you can start training the moment the download finishes.
2. **It reflects the state of GitHub in August 2025.** The corpus is a direct crawl of GitHub repositories at their default-branch HEAD, capturing roughly two additional years of open-source code compared to The Stack v2.

> The Stack v3 training subset contains **15.9 TB** of source code across **713** programming languages from **173M** repositories (~**4.9 trillion** tokens).
> The Full Stack v3 corpus contains **113.7 TB** of source code across **770** languages from **224M** repositories.

### The Stack across versions

| | The Stack v1 | The Stack v2 | The Stack v3 |
|-|-|-|--------------|
| cutoff | 2022 | 2023 | 2025         |
| full | 6.4 TB | 67.5 TB | 113.7 TB     |
| dedup | 2.9 TB | 32.1 TB | 99.3 TB      |
| train | ~200B tokens | 2.0 TB / ~550B tokens | 15.9 TB / ~4.9T tokens |
| languages | 358 | 618 | 713          |

## What is being released

The Stack v3 is published in two complementary datasets:

| Dataset                                                                                      | What it is | Best for |
|----------------------------------------------------------------------------------------------|---|---|
| [`HuggingFaceCode/stack-v3-train`](https://huggingface.co/datasets/HuggingFaceCode/stack-v3-train) | Near-deduplicated, heuristically filtered code, **grouped by repository**, with file contents inline. Ready for training. | Pre-training code LLMs with repository context. |
| [`HuggingFaceCode/stack-v3-full`](https://huggingface.co/buckets/HuggingFaceCode/stack-v3-full)          | The complete corpus before quality filtering and near-dedup selection. Hosted as an HF Storage Bucket. Split into a **`metadata`** part (repo/file metadata) and a **`contents`** part (one row per unique file blob). | Research on the raw corpus, custom filtering, or building your own training mix. |

`stack-v3-train` is derived from `stack-v3-full`: it is the near-deduplicated corpus with an additional round of quality heuristics applied, restricted to one representative per duplicate cluster, and grouped so that each row is a full repository.

`stack-v3-full` is documented in its own [dataset card](https://huggingface.co/buckets/HuggingFaceCode/stack-v3-full). Reach for it when `stack-v3-train` is not enough: it retains all near-duplicates with their **`dedup_cluster`** IDs and pre-filtering signals (so you can roll your own deduplication and filtering), and its metadata lists **every** file of every repository — including stubs for binary, oversized, and undetected-language files — so you can locate and re-crawl anything we excluded (PDFs, binary assets, niche languages).

### Changelog

| Release | Description |
|---|---|
| v3.0 | Initial release of The Stack v3. |

## How to download and use it

### `stack-v3-train`

Each row is a **repository**; the code lives inline under `files[].content`.

```python
from datasets import load_dataset

# Full dataset (downloads locally)
ds = load_dataset("HuggingFaceCode/stack-v3-train", split="train", cache_dir="/path/to/local/cache", num_proc=16)

# Streaming (downloads shards on demand — recommended for quick tests)
ds = load_dataset("HuggingFaceCode/stack-v3-train", split="train", streaming=True)

for repo in ds:
    print(repo["repo_path"], "-", repo["num_files"], "files")
    for f in repo["files"]:
        print(f["file_path"], f["language"], f["license_type"])
        print(f["content"][:100], "...") 
    break
```

> [!TIP]
> There are no per-language configs: each row is a whole repository, and its files (usually a mix of languages) live in the `files[]` array. To filter by language, iterate the dataset (streaming works well) and keep the files you want, e.g. `[f for f in repo["files"] if f["language"] == "Python"]`. If you need language-partitioned files, use [`stack-v3-full`](https://huggingface.co/buckets/HuggingFaceCode/stack-v3-full), where contents are partitioned by language.

For analytical access without loading through the `datasets` library, you can query the Parquet files directly with DuckDB or Polars:

```python
import duckdb
from huggingface_hub import HfFileSystem

duckdb.register_filesystem(HfFileSystem())

duckdb.sql("""
    SELECT repo_path, num_files
    FROM 'hf://datasets/HuggingFaceCode/stack-v3-train/data/*.parquet'
    LIMIT 10
""").show()
```

### `stack-v3-full`

`stack-v3-full` is hosted as a [Hugging Face Storage Bucket](https://huggingface.co/docs/hub/storage-buckets) (not a regular dataset repo), split into a `metadata/` part (one row per repository) and a `contents/` part (one row per unique file blob, partitioned by language) that join on `content_id`. See [its dataset card](https://huggingface.co/buckets/HuggingFaceCode/stack-v3-full) for access instructions, join examples (DuckDB, pandas, PySpark), the full schema, and how stubs and `dedup_cluster` work.

## Dataset statistics

<img src="./assets/stack_v3_multiplier_light.png" alt="The Stack v3 compared to previous versions" style="max-width: min(100%, 720px);">

### Languages

The dataset contains **713** programming and markup languages.

Per-language breakdowns are available as JSON:

* **Train split:** [`stats/train/stats_by_language.json`](./stats/train/stats_by_language.json) — 713 languages
* **Full (unfiltered):** [`stats/full/stats_by_language.json`](./stats/full/stats_by_language.json) — 770 languages

## Dataset structure

### `stack-v3-train` — data fields

Each row is a **repository**.

* `repo_path` (`string`): `owner/name` slug of the repository on GitHub.
* `repo_id` (`int64`): Numeric GitHub repository ID.
* `commit_id` (`string`): Commit (HEAD of the default branch) the snapshot was taken from.
* `github_metadata` (`struct`): Repository-level metadata from the GitHub repository page:
  * `branch` (`string`): Default branch name.
  * `commit_count` (`int32`): Number of commits on the default branch.
  * `repo_created_at` (`string`): Repository creation timestamp.
  * `is_fork` (`bool`): Whether the repository is a fork.
  * `is_org_owned` (`bool`): Whether the repository is owned by an organization.
  * `forked_from` (`string`): Source repository if this is a fork, else `None`.
  * `stars` (`int32`): Star count at crawl time.
  * `forks` (`int32`): Fork count at crawl time.
  * `issues` (`int32`): Open issue count at crawl time.
  * `pull_requests` (`int32`): Open pull-request count at crawl time.
* `num_files` (`int64`): Number of files in this repository row.
* `files` (`list[struct]`): The files of the repository:
  * `content_id` (`string`): SHA-1 of the file content.
  * `content` (`string`): The UTF-8 file content (PII-redacted).
  * `size_bytes` (`int32`): Length of the content in UTF-8 bytes.
  * `file_path` (`string`): Path of the file within the repository.
  * `file_timestamp` (`int64`): File modification time (Unix seconds). Only as accurate as the GitHub metadata.
  * `language` (`string`): Programming language, detected by [`go-enry`](https://github.com/go-enry/go-enry) (a port of GitHub's Linguist).
  * `is_vendor` (`bool`): Whether the file is a vendored/third-party file (per `go-enry`).
  * `license_type` (`string`): `permissive` or `no_license`.
  * `detected_licenses` (`list[string]`): SPDX license identifiers detected by [ScanCode](https://github.com/nexB/scancode-toolkit).

### `stack-v3-full` — data fields

`stack-v3-full` shares the same repository-level fields, but its `files[]` structs reference content by `content_id` instead of embedding it, and include **stub** entries for excluded files (binary, oversized, undetected language). The full schema and stub semantics are documented in the [`stack-v3-full` dataset card](https://huggingface.co/buckets/HuggingFaceCode/stack-v3-full#data-fields).

## Dataset creation

The Stack v3 was built in a similar fashion as The Stack v2 — language detection with [`go-enry`](https://github.com/go-enry/go-enry), file-level license detection with [ScanCode](https://github.com/nexB/scancode-toolkit), MinHash-LSH near-deduplication, PII redaction, quality filtering, and repository-level grouping — with updated tool versions and a few meaningful changes:

### What changed from v2

| | The Stack v2 | The Stack v3 |
|---|---|---|
| **Source** | Software Heritage graph (2023) | Direct GitHub crawl (cutoff: 2025-08-07) |
| **Content** | File IDs only | File contents inline — self-contained |
| **Near-dedup** | Per-language | Language-agnostic, with Jaccard verification after connected-component clustering (no false positives) |

The rest of the pipeline (license detection, quality heuristics, PII redaction, grouping) follows the same methodology as v2 with updated tool versions.

> **Scope note:** This release focuses on **source code and Jupyter notebooks**. It does not include the additional non-code sources that accompanied StarCoder2 training (GitHub issues, pull requests, Kaggle notebooks, documentation, ArXiv, Wikipedia, OpenWebMath, etc.).

### Curation rationale

Most code LLMs are trained on data that is never released, making the systems hard to reproduce and study. By publishing a large, contemporary, contents-included code dataset together with its construction code, we aim to make code-LLM pre-training reproducible and to give researchers a transparent, up-to-date corpus to build on.

### Source data

#### Data collection

The list of repositories to crawl was assembled by taking the union of:

- Every GitHub repository that appears in [GH Archive](https://www.gharchive.org/) public event data, and
- Every GitHub origin recorded in the Software Heritage graph (origin table, `2025-05-18` snapshot).

For each repository, the crawler fetched the GitHub repository page (for metadata such as stars, forks, and the HEAD commit) and downloaded a **single snapshot tarball** of the default branch at its HEAD commit — no git history is collected. Forks were only downloaded when they had at least **5 stars**.

During download, the following were dropped or emptied:

* Files larger than **5 MB**.
* Binary files (files containing a null byte).
* Symlinks and non-regular files.
* Repositories were capped at **1,000,000 files**.


The crawl completed on **August 7, 2025**. The dataset reflects the state of public GitHub repositories as of that date.

The crawl collected snapshots from **224M** repositories containing **43.9 billion** files (including stubs for binary, oversized, and undetected-language files).

The exact snapshot for every repository is traceable via its `commit_id`.

#### Cleaning and filtering

The corpus then passes through the following stages (implemented in Spark):

1. **Decoding & language detection.** File bytes are decoded to UTF-8 (falling back to `cchardet` encoding detection). Language, vendor, and generated-file flags are assigned with [`go-enry`](https://github.com/go-enry/go-enry). Each unique content blob is content-addressed by its SHA-1 (`content_id`) and stored once.
2. **License detection.** We detect licenses at the file level using the [ScanCode Toolkit](https://github.com/nexB/scancode-toolkit) and propagate them through the repository file tree:
   1. *Identify license files.* Any file whose name matches a license-bearing pattern (e.g. `LICENSE`, `COPYING`, `MIT.txt`, `Apache2.0`, `NOTICE`, `README`, `GUIDELINES`, …) is selected for scanning.
   2. *Detect licenses.* ScanCode's license detection runs on the content of each matching file and returns the SPDX identifiers of any licenses found.
   3. *Propagate to siblings.* The detected licenses are propagated to every file that shares the same directory prefix as the license file — e.g. a `LICENSE` at the repo root covers all files, while one in `src/lib/` covers only files under that subtree. When a file is covered by multiple license files from different directories, their licenses are merged.
   4. *Classify.* Each file is labelled `permissive` (at least one permissive license detected, no conflicting non-permissive license), `no_license` (no licenses detected, or only non-license legal texts such as CLAs), or `non_permissive`. The permissive allowlist follows the [Blue Oak Council](https://blueoakcouncil.org/list) list plus licenses categorized as *Permissive* or *Public Domain* by [ScanCode](https://scancode-licensedb.aboutcode.org/). **Files classified as `non_permissive` are excluded from both released datasets.**
3. **Near-deduplication.** MinHash signatures (256 permutations, 5-grams, min. 5 tokens) are indexed with LSH; candidate pairs with estimated Jaccard similarity ≥ **0.7** are grouped into duplicate clusters via connected components. Unlike v2, deduplication runs across all languages at once (language-agnostic) and candidate pairs are verified against their Jaccard estimate to eliminate false positives. For `stack-v3-train`, a single **representative** file per cluster is retained, chosen by (in order) highest stars, highest forks, permissive license, earliest repository creation.
4. **Quality heuristics** (applied to `stack-v3-train`). Same filters as the StarCoder2 pipeline, with minor adjustments to language lists to accommodate new or updated languages detected by the newer `go-enry` release:
   * Drop files with `<25%` alphabetic characters (alphanumeric for Assembly).
   * Drop files with average line length `>100` or maximum line length `>1000` (exempting data/markup formats such as Text, JSON, XML, HTML, Markdown, Roff, TeX).
   * Drop files with `>100,000` lines and cap several data/config formats (such as JSON, Yaml,...) at `512` lines.
   * Drop files with giant base64/hex/unicode-escape data blobs, LFS pointers, and files with auto-generation markers in the first 5 lines.
   * For HTML, keep only files whose visible text is ≥ 100 characters and ≥ 20% of the content.
   * Drop a curated blocklist of non-code languages/extensions.
   * Cap the largest markup/config languages (XML, HTML, JSON, JavaScript) at a fixed byte budget each, and probabilistically downsample any repository whose total size exceeds **1.5 GB** to fit Arrow/Parquet limits.
5. **PII redaction** (applied to `stack-v3-train`). Same model and filtering as v2. File contents are scanned with [`StarPII`](https://huggingface.co/bigcode/starpii). Detected emails, keys, names, passwords, and IP addresses are replaced with placeholder tokens (`<EMAIL>`, `<KEY>`, `<NAME>`, `<PASSWORD>`, and synthetic private IPs).
6. **Jupyter notebooks** (applied to `stack-v3-train`). `.ipynb` files are processed separately: cell **outputs, inline images, and volatile metadata are stripped**, and the notebook is kept as structured JSON. They pass through the same license, dedup, and PII steps. `stack-v3-full` keeps the raw `.ipynb` contents as crawled — use it if you want to apply your own notebook processing.
7. **Grouping.** Files are grouped by repository so each row is a full repository, enabling repository-context pre-training.

Opt-out requests (see below) are applied before release.

#### Who are the source language producers?

The source code was written by GitHub users whose repositories were public at crawl time (up to August 7, 2025).

### Personal and sensitive information

`stack-v3-train` was scanned for PII (emails, keys, names, passwords, IP addresses) with the same model and heuristics as The Stack v2, and detected entities were replaced with placeholder tokens. Detection is imperfect: the released data may still contain sensitive information (emails, IP addresses, keys) that was previously published to public GitHub repositories.

Researchers should use only public, non-personal information for open-access research, and must not use any personal information for spamming or other harmful purposes.

### Opting out

Developers can request that their code be removed from The Stack v3. You can check whether your code is included via the ["Am I in The Stack?"](https://huggingface.co/spaces/HuggingFaceCode/in-the-stack) Space, and submit removal requests following the [opt-out instructions](https://github.com/bigcode-project/opt-out-v2). Repositories that opted out are removed from the dataset before each patch release.

## Considerations for using the data

### Social impact

The Stack v3 is released in the spirit of open science, to increase the accessibility, reproducibility, and transparency of code-LLM research. Code LLMs can help people of diverse backgrounds write better software, but they also carry risks such as over-reliance on generated code, generation of insecure or malicious code, and effects on the software-development labor market.

### Discussion of biases

Widely used languages (e.g. C, JavaScript, Python) are heavily overrepresented relative to niche languages, and some languages are far less likely to be permissively licensed than others, biasing their representation. Comments in code may contain harmful or offensive language. The majority of natural language in the code is English.

### Other known limitations

* License attribution is only as accurate as ScanCode and the GitHub metadata; report any mistakes for review.
* The dataset may contain malicious code, and models trained on it could be used to generate malware.
* Because content is a single default-branch snapshot (as of August 7, 2025), it does not capture development history or non-default branches.

## Additional information

### Licensing information

The dataset is released under the **Open Data Commons Attribution License (ODC-By) v1.0** [license](https://opendatacommons.org/licenses/by/1-0/).

The Stack v3 is a collection of source code from repositories with various licenses. Any use of all or part of the code gathered in The Stack v3 must abide by the terms of the original licenses, including attribution clauses where relevant; we provide provenance information (`repo_path`, `commit_id`, `detected_licenses`) for each file to facilitate this. 

The list of [SPDX license identifiers](https://spdx.org/licenses/) included in the dataset can be found [here](stats/full/stats_by_license.json).

### Citation information

```bibtex
@misc{lozhkov2026stack-v3,
    author       = {Lozhkov, Anton and Larcher, Hugo and Morlon, Mathieu and Ben Allal, Loubna and von Werra, Leandro},
    title        = {The Stack v3: The Largest Open Code Dataset},
    year         = 2026,
    url          = {https://huggingface.co/datasets/HuggingFaceCode/stack-v3-train},
    publisher    = {Hugging Face}
}
```

The Stack v3 builds on the methodology of The Stack v2 / StarCoder2:

```bibtex
@misc{lozhkov2024starcoder,
      title={StarCoder 2 and The Stack v2: The Next Generation},
      author={Anton Lozhkov and Raymond Li and Loubna Ben Allal and Federico Cassano and Joel Lamy-Poirier and Nouamane Tazi and Ao Tang and Dmytro Pykhtar and Jiawei Liu and Yuxiang Wei and Tianyang Liu and Max Tian and Denis Kocetkov and Arthur Zucker and Younes Belkada and Zijian Wang and Qian Liu and Dmitry Abulkhanov and Indraneil Paul and Zhuang Li and Wen-Ding Li and Megan Risdal and Jia Li and Jian Zhu and Terry Yue Zhuo and Evgenii Zheltonozhskii and Nii Osae Osae Dade and Wenhao Yu and Lucas Krauß and Naman Jain and Yixuan Su and Xuanli He and Manan Dey and Edoardo Abati and Yekun Chai and Niklas Muennighoff and Xiangru Tang and Muhtasham Oblokulov and Christopher Akiki and Marc Marone and Chenghao Mou and Mayank Mishra and Alex Gu and Binyuan Hui and Tri Dao and Armel Zebaze and Olivier Dehaene and Nicolas Patry and Canwen Xu and Julian McAuley and Han Hu and Torsten Scholak and Sebastien Paquet and Jennifer Robinson and Carolyn Jane Anderson and Nicolas Chapados and Mostofa Patwary and Nima Tajbakhsh and Yacine Jernite and Carlos Muñoz Ferrandis and Lingming Zhang and Sean Hughes and Thomas Wolf and Arjun Guha and Leandro von Werra and Harm de Vries},
      year={2024},
      eprint={2402.19173},
      archivePrefix={arXiv},
      primaryClass={cs.SE}
}
```

### Acknowledgements

This dataset is derived from source code hosted on GitHub. We thank the developers who make their work publicly available, and the [BigCode](https://www.bigcode-project.org/) community, whose work on dataset filters, PII detection, and open code dataset governance informed much of this pipeline.
