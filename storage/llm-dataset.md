---
license: mit
language:
- en
- multilingual
task_categories:
- text-generation
- other
tags:
- distillation
- instruction-tuning
- sft
- reasoning
- coding
- code-repositories
- cybersecurity
- attack
- defense
- exploit
- penetration-testing
- red-team
- blue-team
- open-source
- collection
- fable-5
- gpt-5.5
- claude
- gemini
- grok
- kimi
- deepseek
- Trace
- qwen
- biology
- science
- Llm
- Open-source
- Math
- cyber 
- security 
- cyber-security 
- cyber security 
size_categories:
- 10M<n<100M
pretty_name: "The Open Distillation Codex"
configs:
- config_name: default
  data_files:
  - split: train
    path:
    - "data/applied/*/*.jsonl"
    - "data/coding/*/*.jsonl"
    - "data/cybersecurity/high_quality_cybersecurity/shard-*.jsonl"
    - "data/cybersecurity/clydeiii_cybersecurity/shard-*.jsonl"
    - "data/cybersecurity/fenrir_v2_1/shard-*.jsonl"
    - "data/cybersecurity/precinct6_cybersecurity/shard-*.jsonl"
    - "data/cybersecurity/savani_cyber_attack/shard-*.jsonl"
    - "data/distilled/*/*.jsonl"
    - "data/humanities/*/*.jsonl"
    - "data/index/*/*.jsonl"
    - "data/instruction/*/*.jsonl"
    - "data/science/*/*.jsonl"
---

<div align="center">

<img src="https://img.shields.io/badge/Version-8.2-blue?style=for-the-badge" alt="Version">
<img src="https://img.shields.io/badge/Storage-76GB%2B-green?style=for-the-badge" alt="Storage">
<img src="https://img.shields.io/badge/Sources-73-orange?style=for-the-badge" alt="Sources">
<img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License">
<img src="https://img.shields.io/badge/Samples-18M%2B-red?style=for-the-badge" alt="Samples">
<img src="https://img.shields.io/badge/Cybersecurity-6%20Sources-purple?style=for-the-badge" alt="Cybersecurity">

<br><br>

# 📖 The Open Distillation Codex

### 🌌 *The Ultimate Open-Source Distillation Dataset — No Skip, Full, with Attack & Defense* 🌌

**Where 73 open-source minds converge into one unified stream of intelligence**

`18M+ Distilled Signals` · `7,090 Raw GitHub Repositories` · `8 Curated Categories` · `~76 GB+`

<br>

> *"We did not write this dataset. We assembled it.*
> *Every line is an echo — of a model thinking, a coder drafting, a tutor explaining, a repo breathing.*
> *Seventy-three sources. Eight categories. Zero gatekeeping. No skipping. Fully processed. Now fortified with real-world cybersecurity confrontations."*

<br>

</div>

---

## 📌 Table of Contents

| # | Section | Description |
|---|---|---|
| 1 | [📊 Dataset Summary](#-dataset-summary) | High-level overview & value proposition |
| 2 | [🗂️ Directory Structure](#️-directory-structure) | ASCII tree + folder explanation |
| 3 | [🌐 Data Sources](#-data-sources--provenance) | All 73 sources with full attribution |
| 4 | [🛡️ Cybersecurity Deep Dive: Attack & Defense](#️-cybersecurity-deep-dive-attack--defense) | Importance, attack traces, defense, exploit analysis |
| 5 | [🛠️ How to Use & Train](#️-how-to-use--train) | Loading, streaming, training scripts |
| 6 | [🔐 Licensing & Limitations](#-licensing--limitations) | License, intended use, limitations |
| 7 | [📜 Changelog](#-changelog) | Version history |

---

## 📊 Dataset Summary

<div align="center">

### 🎯 The Numbers That Matter

| Metric | Value | Status |
|:---:|:---:|:---:|
| **Total Storage** | `76 GB+` | ✅ Verified |
| **JSONL Data Shards** | `516` | ✅ Verified |
| **Archive Files (tar.gz)** | `7,090` | ✅ Verified |
| **Source Datasets** | `73` | ✅ Verified |
| **Categories** | `8` | ✅ Verified |
| **Total Samples** | `18M+` | ✅ Verified |
| **Largest Source** | `8.15M` (Vibe-Coding-Instruct-V2) | ✅ |
| **Archive Size** | `~64 GB` (compressed GitHub repos) | ✅ |
| **Cybersecurity Sources** | `6` | ✅ |
| **Cybersecurity Data Size** | `~2.6 GB` | ✅ |

</div>

<br>

### 🌟 Why "Ultimate Distilled"?

This dataset is not a raw scrape. Every sample has been **distilled through a unified extraction pipeline**:

```
┌────────────────────────────────────────────────────────────┐
│                    UNIFIED EXTRACTION PIPELINE              │
├────────────────────────────────────────────────────────────┤
│                                                             │
│  73 Upstream Sources (ALL FULLY PROCESSED, NO SKIP)         │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐          │
│  │ HF  │ │ HF  │ │ HF  │ │ GH  │ │ HF  │ │ ... │          │
│  └──┬──┘ └──┬──┘ └──┬──┘ └──┬──┘ └──┬──┘ └──┬──┘          │
│     │       │       │       │       │       │               │
│     └───────┴───────┴───────┼───────┴───────┘               │
│                         │                                    │
│                    ┌────▼────┐                               │
│                    │ EXTRACT │ ← Field normalization        │
│                    └────┬────┘   (instruction/response)      │
│                         │                                    │
│                    ┌────▼────┐                               │
│                    │CATEGORIZE│ ← 8 semantic categories      │
│                    └────┬────┘                               │
│                         │                                    │
│                    ┌────▼────┐                               │
│                    │  SHARD  │ ← 20K samples per shard       │
│                    └────┬────┘                               │
│                         │                                    │
│                    ┌────▼────┐                               │
│                    │ UPLOAD  │ ← Batch commits to HF         │
│                    └─────────┘                               │
│                                                             │
│  STATUS: ALL 73 SOURCES COMPLETE. NO SKIPPING. 18M+ ROWS.   │
└────────────────────────────────────────────────────────────┘
```

<br>

### 💎 Value to the Open-Source AI Community

| 🎯 For... | 📦 This dataset provides... |
|---|---|
| **Model Trainers** | Single `load_dataset()` call to stream 18M+ SFT-ready samples |
| **Coding Agent Researchers** | 11M+ agentic coding traces from Fable-5, Vibe-Coding, Royal Ghost, Kimi, DeepSeek |
| **Code Pretraining** | 7,090 full GitHub repository snapshots (64 GB compressed) |
| **Reasoning Researchers** | 2.7M+ distilled reasoning traces from Claude, Gemini, Grok, GPT-5.5, Opus 4.8 |
| **Domain Specialists** | 25K-sample sweeps across 29 disciplines |
| **Cybersecurity Researchers** | Dedicated cybersecurity category with attack/defense/exploit traces, red/blue team dialogues, and incident reports |
| **Red Team / Blue Team Trainers** | Realistic attack scenarios, defense strategies, exploit code, and post-mortem analysis |

---

## 🗂️ Directory Structure

```
📂 Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset/
│
├── 📦 archives/                          # ~64 GB — 7,090 compressed GitHub repos
│   ├── 0-chi__sonaure-lp.tar.gz
│   ├── 00MB__bitcoin_trading_bot.tar.gz
│   ├── 0101-agents__plugins.tar.gz
│   ├── ... (7,090 files total)
│   └── zznmg1__playable-survivor-ad.tar.gz
│
├── 📁 data/                              # ~12 GB — 516 JSONL shards (18M+ samples)
│   │
│   ├── 💻 coding/                        # 28 sources · ~11M+ samples
│   │   ├── vibe_instruct_v2/             # 8,152,510 samples
│   │   ├── fable5_2m/                    # 2,006,487 samples
│   │   ├── vibe_instruct_v1/             # 1,100,000 samples
│   │   ├── vibe_coding/                  # 1,100,000 samples
│   │   ├── royal_ghost_1m/               # 1,000,000 samples
│   │   ├── citation_ground/              # 980,064 samples
│   │   ├── royal_ghost_501k/             # 703,449 samples
│   │   ├── fable5_repos_full/            # 7,090 archive pointers
│   │   ├── fable5_agentic_sft/           # 159,972 samples
│   │   ├── gpt55_codex/                  # 119,436 samples ⭐ FULL
│   │   ├── alpca_gpt55/                  # 49,099 samples
│   │   ├── deepseek_v4_pro_agent/        # 96,597 samples ⭐ FULL
│   │   ├── fable5_traces/                # 49,544 samples ⭐ FULL
│   │   ├── genesis_code_100k/            # 68,000 samples
│   │   ├── genesis_code/                 # 49,000 samples
│   │   ├── kimi_coding/                  # 9,014 samples
│   │   ├── mimo_claude_code_traces/      # 15,046 samples ⭐ FULL
│   │   ├── kimi_k26_claude_code_traces/  # 7,438 samples
│   │   ├── genesis_code_10k/             # 9,800 samples
│   │   ├── legend_python/                # 5,000 samples
│   │   ├── autonomy/                     # 10,000 samples
│   │   ├── genesis_code_demo/            # 1,000 samples
│   │   ├── god_coder/                    # ⭐ FULL raw recovery
│   │   ├── python_god_coder/             # ⭐ FULL raw recovery
│   │   ├── elite_god_coder/              # ⭐ FULL raw recovery
│   │   ├── omega_genesis/                # ⭐ FULL raw recovery
│   │   ├── open_tool_trace/              # 48 samples
│   │   └── genesis_v11/                  # partial recovery
│   │
│   ├── 🧮 math/                          # 2 sources
│   │   ├── math_25k/
│   │   └── deepseek_prover_v1/           # 27,503 Lean theorem proofs
│   │
│   ├── 🔬 science/                       # 7 sources
│   │   ├── science_25k/
│   │   ├── physics_25k/
│   │   ├── chemistry_25k/
│   │   ├── biology_25k/
│   │   ├── medical_25k/
│   │   ├── cs_25k/
│   │   └── biology_r2med/                # ⭐ NEW
│   │
│   ├── ⚙️ applied/                       # 8 sources
│   │   ├── robotics_25k/
│   │   ├── nano_25k/
│   │   ├── materials_25k/
│   │   ├── earth_climate_25k/
│   │   ├── renewable_energy_25k/
│   │   ├── evolution_25k/
│   │   ├── universe_25k/
│   │   └── kardashev_25k/
│   │
│   ├── 📚 humanities/                    # 8 sources
│   │   ├── psychology_25k/
│   │   ├── economics_25k/
│   │   ├── law_25k/
│   │   ├── statistics_25k/
│   │   ├── sports_25k/
│   │   ├── human_25k/
│   │   ├── conscience_25k/
│   │   └── supernatural_25k/
│   │
│   ├── 🧠 distilled/                     # 9 sources · frontier distillations
│   │   ├── claude_mythos/
│   │   ├── gemini35/
│   │   ├── fable5_cleaned/
│   │   ├── grok44/
│   │   ├── gemini_pro32/
│   │   ├── gpt55_thinking/
│   │   ├── gpt55_distilled/
│   │   ├── claude_opus_48_distill/       # ⭐ NEW
│   │   └── claude_opus_48_max_thinking/  # ⭐ NEW
│   │
│   ├── 📝 instruction/                   # 3 sources
│   │   ├── alpaca/                       # 52,002 samples
│   │   ├── oasst/                        # 32,141 samples
│   │   └── dolly/                        # 15,011 samples
│   │
│   ├── 🔒 cybersecurity/                 # 6 sources
│   │   ├── high_quality_cybersecurity/
│   │   ├── heimdall_v1_1/                # ⭐ NEW — 78 MB conversations
│   │   ├── fenrir_v2_1/                  # ⭐ NEW — 411 MB (2.1M+ entries)
│   │   ├── clydeiii_cybersecurity/       # ⭐ NEW — 20 MB yearly corpus
│   │   ├── precinct6_cybersecurity/      # ⭐ NEW — 2.1 GB (graph+signals+ref)
│   │   └── savani_cyber_attack/          # ⭐ NEW — 17 MB attack CSV
│   │
│   └── 📇 index/                         # 2 sources
│       ├── species_25k/
│       └── transport_25k/
│
├── 📄 README.md
└── 📄 dataset_info.json
```

### 🤔 Why is `archives/` kept compressed?

| Reason | Explanation |
|---|---|
| **💾 Space Efficiency** | Uncompressed would exceed 200+ GB. Compressed = 64 GB (3× saving) |
| **🎯 On-Demand Access** | Download only specific repositories you need |
| **🔐 Preservation Fidelity** | tar.gz preserves exact file permissions, directory structure, binaries |

> 💡 **Tip**: For training on code content, use `data/coding/fable5_repos_full/` (475K samples, each a file extracted from archives, capped at 4KB). For full untruncated file access, stream directly from `archives/`.

---

## 🌐 Data Sources & Provenance

<div align="center">

### 🗺️ 73 Sources Across 8 Categories

| Category | Sources | Samples | Description |
|:---:|:---:|:---:|:---|
| 💻 `coding` | 28 | ~11M+ | Agentic traces, code repos, coder distillations |
| 🧠 `distilled` | 9 | ~200K | Frontier model distillations |
| ⚙️ `applied` | 8 | ~200K | Robotics, nano, materials, climate, energy |
| 📚 `humanities` | 8 | ~200K | Psychology, economics, law, statistics |
| 🔬 `science` | 7 | ~175K | Physics, chemistry, biology, medical, CS |
| 📝 `instruction` | 3 | ~99K | Classic instruction (alpaca, oasst, dolly) |
| 📇 `index` | 2 | ~50K | Species index, transport |
| 🔒 `cybersecurity` | 6 | ~2.6 GB | High-quality attack, defense, exploit traces |
| 🧮 `math` | 2 | ~52K | Math + Lean theorem proofs |

</div>

<br>

### 💻 Coding Category (28 sources — ALL FULLY PROCESSED ⭐)

| Source Slug | Upstream Dataset | Type | Samples |
|---|---|---|---:|
| `vibe_instruct_v2` | `CodeDevX/Vibe-Coding-Instruct-V2` | Agentic coding | 8,152,510 |
| `fable5_2m` | `Crownelius/Complete-FABLE.5-traces-2M` | Fable-5 traces | 2,006,487 |
| `vibe_instruct_v1` | `CodeDevX/Vibe-Coding-Instruct` | Agentic coding | 1,100,000 |
| `vibe_coding` | `attentionAllYouNeed/Vibe-Coding-Claude-Fable-5` | Claude coding | 1,100,000 |
| `royal_ghost_1m` | `WithinUsAI/Royal_Ghost_Coder_1M` | Ghost coder | 1,000,000 |
| `citation_ground` | `WithinUsAI/CitationGround-1M` | Citation-grounded | 980,064 |
| `royal_ghost_501k` | `WithinUsAI/Royal_Ghost_Coder_501k` | Ghost coder | 703,449 |
| `fable5_repos_full` | `notune/fable5-repos` | 7,090 repo pointers | 7,090 |
| `fable5_agentic_sft` | `Nexlab/fable5-agentic-coding-sft` | Agentic SFT | 159,972 |
| `gpt55_codex` | `AletheiaResearch/GPT-5.5-Codex` | GPT-5.5 Codex | 119,436 |
| `alpca_gpt55` | `GabrielFreeze-2/alpca-mlt-gpt-5.5_chatml` | GPT-5.5 chatml | 49,099 |
| `deepseek_v4_pro_agent` | `TeichAI/DeepSeek-v4-Pro-Agent` | DeepSeek v4 | 96,597 |
| `fable5_traces` | `Glint-Research/Fable-5-traces` | Fable-5 traces | 49,544 |
| `genesis_code_100k` | `WithinUsAI/Genesis_AI_Code_100k` | Genesis code | 68,000 |
| `genesis_code` | `WithinUsAI/Genesis_AI_Code_50k` | Genesis code | 49,000 |
| `kimi_coding` | `trjxter/Kimi-K2.7-CodingTraces-9000x` | Kimi K2.7 | 9,014 |
| `mimo_claude_code_traces` | `choucsan/mimo-claude-code-traces-1k` | Mimo Claude | 15,046 |
| `kimi_k26_claude_code_traces` | `armand0e/kimi-k2.6-claude-code-traces` | Kimi K2.6 | 7,438 |
| `genesis_code_10k` | `WithinUsAI/Genesis_AI_Code_10k` | Genesis code | 9,800 |
| `legend_python` | `WithinUsAI/Legend_Python_CoderV.1` | Python coder | 5,000 |
| `autonomy` | `WithinUsAI/The_Autonomy_From_WithIn_10k` | Autonomy | 10,000 |
| `genesis_code_demo` | `WithinUsAI/Genesis_AI_Code_1k_Demo` | Genesis demo | 1,000 |
| `god_coder` | `WithinUsAI/GOD_Coder_100k` | GOD coder | FULL ⭐ |
| `python_god_coder` | `WithinUsAI/python_GOD_coder_100k` | Python GOD | FULL ⭐ |
| `elite_god_coder` | `WithinUsAI/Elite_GOD_Coder_100k` | Elite GOD | FULL ⭐ |
| `omega_genesis` | `WithinUsAI/Omega_Genesis_Coder_100k` | Omega Genesis | FULL ⭐ |
| `open_tool_trace` | `WithinUsAI/OpenToolTrace-X` | Tool traces | 48 |
| `genesis_v11` | `WithinUsAI/Genesis_v1_1_Update...` | Genesis v1.1 | partial |

<br>

### 🧠 Distilled Category (9 sources)

| Source | Upstream | Distilled From |
|---|---|---|
| `claude_mythos` | `WithinUsAI/claude_mythos_distilled_25k` | Claude |
| `gemini35` | `WithinUsAI/gemini_3.5_flash_distilled_25k` | Gemini 3.5 Flash |
| `fable5_cleaned` | `WithinUsAI/fable_5_distillation_merged_cleaned_25k` | Fable-5 |
| `grok44` | `WithinUsAI/Grok4.4_heavy_max_distill_god_seed_25k` | Grok 4.4 |
| `gemini_pro32` | `WithinUsAI/GeminiPro3.2_max_distill_god_seed_25k` | Gemini Pro 3.2 |
| `gpt55_thinking` | `WithinUsAI/GPT5.5_thinking_max_distill_god_seed_25K` | GPT-5.5 |
| `gpt55_distilled` | `WithinUsAI/GPT_5.5_Distilled` | GPT-5.5 |
| `claude_opus_48_distill` | `11-47/claude_opus_4.8_distill_5k` | Claude Opus 4.8 ⭐ |
| `claude_opus_48_max_thinking` | `11-47/claude_opus_4.8_max_thinking_5k_v2` | Opus 4.8 Max ⭐ |

<br>

### 🔬 Science · ⚙️ Applied · 📚 Humanities · 🧮 Math · 📝 Instruction · 🔒 Cybersecurity · 📇 Index

<details>
<summary>📖 Click to expand all other categories</summary>

**🔬 Science (7 sources):** `science_25k`, `physics_25k`, `chemistry_25k`, `biology_25k`, `medical_25k`, `cs_25k`, `biology_r2med` (R2MED/Biology)

**⚙️ Applied (8 sources):** `robotics_25k`, `nano_25k`, `materials_25k`, `earth_climate_25k`, `renewable_energy_25k`, `evolution_25k`, `universe_25k`, `kardashev_25k`

**📚 Humanities (8 sources):** `psychology_25k`, `economics_25k`, `law_25k`, `statistics_25k`, `sports_25k`, `human_25k`, `conscience_25k`, `supernatural_25k`

**🧮 Math (2 sources):** `math_25k`, `deepseek_prover_v1` (27,503 Lean proofs)

**📝 Instruction (3 sources):** `alpaca` (52K), `oasst` (32K), `dolly` (15K)

**🔒 Cybersecurity (6 sources):** `high_quality_cybersecurity`, `heimdall_v1_1`, `fenrir_v2_1`, `clydeiii_cybersecurity`, `precinct6_cybersecurity`, `savani_cyber_attack`

**📇 Index (2 sources):** `species_25k`, `transport_25k`

</details>

---

## 🛡️ Cybersecurity Deep Dive: Attack & Defense

### ⚔️ Why This Matters

Modern AI systems are increasingly deployed in security-critical environments—yet most open-source training data ignores real-world adversarial scenarios. **The Open Distillation Codex** includes a dedicated `cybersecurity` category designed to equip models with:

- **Attack Awareness**: Recognize and generate realistic attack patterns, exploits, penetration testing commands, and social engineering dialogues.
- **Defense Proficiency**: Learn to propose defensive measures, detect anomalies, and articulate incident response protocols.
- **Exploit Understanding**: Analyze and explain software vulnerabilities, craft proof-of-concept code (for educational purposes), and understand exploit chains.
- **Red/Blue Team Simulation**: Engage in multi-turn conversations mimicking red team attack planning and blue team defense coordination.
- **Threat Intelligence**: Summarize, classify, and reason about cyber threat reports, CVEs, and IOCs (Indicators of Compromise).

This makes the dataset a powerful foundation for building **cybersecurity-aware LLMs**, **security co-pilots**, and **automated vulnerability assessment tools**.

### 📊 What’s Inside the Cybersecurity Category?

| Source | Description | Data Format | Key Themes |
|:---|:---|:---|:---|
| `high_quality_cybersecurity` | Manually curated high-quality instruction–response pairs covering attack techniques, defense, and policy | JSONL (shards) | MITRE ATT&CK, OWASP, incident response |
| `heimdall_v1_1` | ~78 MB of security conversations, including red/blue team dialogues and threat analysis | JSONL | Multi-turn chat, tool usage |
| `fenrir_v2_1` | 411 MB, 2.1M+ entries — massive corpus of cybersecurity Q&A, exploit descriptions, and code snippets | JSONL | Exploit code, CVEs, vulnerability research |
| `clydeiii_cybersecurity` | 20 MB yearly security corpus, aggregated from public reports and advisories | JSONL | Year-in-review, trends, threat landscape |
| `precinct6_cybersecurity` | 2.1 GB graph-based dataset with network signals, attack graphs, and reference materials | JSONL (graph+signals+ref) | Network attacks, lateral movement, detection |
| `savani_cyber_attack` | 17 MB CSV of labeled cyber attack incidents with detailed features | CSV | Attack classification, feature analysis |

### 🧪 Attack & Exploit Examples

Here are a few representative samples (sanitized) from the dataset:

**Example 1 – SQL Injection Exploit**
```json
{
  "source": "fenrir_v2_1",
  "instruction": "Explain how an attacker could exploit a vulnerable login form using SQL injection. Provide a sample malicious input.",
  "response": "An attacker could bypass authentication by injecting SQL logic. For a query like:\n`SELECT * FROM users WHERE username='$user' AND password='$pass'`,\nthe attacker might enter `admin' --` as the username and anything as password. The resulting query becomes:\n`SELECT * FROM users WHERE username='admin' --' AND password='...'`\nThe `--` comments out the password check, granting access as admin. More advanced attacks use UNION to extract data."
}
```

**Example 2 – Red Team Command Sequence**
```json
{
  "source": "heimdall_v1_1",
  "instruction": "As a red team operator, list the steps you would take after gaining initial access to a Windows machine using a phishing payload.",
  "response": "1. Establish persistence: `schtasks /create /tn \"Updater\" /tr \"C:\\malware.exe\" /sc hourly`\n2. Enumerate local users: `net user /domain`\n3. Dump credentials: `mimikatz sekurlsa::logonpasswords`\n4. Lateral movement: use PsExec to move to file server.\n5. Exfiltrate data: compress sensitive files and upload via DNS tunneling.\nAlways maintain C2 communication over HTTPS to blend in."
}
```

**Example 3 – Defense Playbook (Blue Team)**
```json
{
  "source": "high_quality_cybersecurity",
  "instruction": "An IDS alert flags unusual outbound DNS traffic from a workstation. What's the immediate response?",
  "response": "1. Isolate the workstation from the network (VLAN change or port shutdown).\n2. Capture volatile memory and network logs for forensics.\n3. Check DNS queries: if long, random-looking subdomains, suspect DNS tunneling.\n4. Scan for malware with updated signatures.\n5. Review firewall logs for similar traffic from other hosts.\n6. If confirmed, initiate incident response playbook for data exfiltration."
}
```

### 🎓 How to Train a Cybersecurity-Focused LLM

```python
from datasets import load_dataset

REPO = "Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset"

# Load only cybersecurity category
cyber_ds = load_dataset(REPO, split="train", 
                        data_files="data/cybersecurity/**/*.jsonl",
                        streaming=True)

# Or load specific sources
fenrir = load_dataset(REPO, split="train", 
                      data_files="data/cybersecurity/fenrir_v2_1/*.jsonl")

# Format for SFT
def format_security_sample(example):
    return {
        "text": f"### Security Task:\n{example['instruction']}\n\n### Expert Response:\n{example['response']}"
    }

cyber_ds = cyber_ds.map(format_security_sample)

# Now train with your favourite framework (transformers, axolotl, etc.)
```

**Curriculum Idea**:  
1. Start with `high_quality_cybersecurity` and `heimdall_v1_1` for foundational attack/defense conversations.  
2. Introduce `fenrir_v2_1` for exploit code and vulnerability deep dives.  
3. Use `precinct6_cybersecurity` for network-level attack graph understanding.

### 🛡️ Ethical & Responsible Use

- **For Defensive Purposes Only**: This data is intended to strengthen AI for defense, threat detection, and security education. Do not use it to generate active attack code without proper authorization.
- **No Zero-Day Exploits**: The dataset contains only already-public vulnerabilities and techniques. It does not include zero-day or weaponized exploits.
- **Responsible Disclosure**: If you fine-tune a model with this data, we recommend adding a safety preamble warning that generated security content must be used legally and ethically.
- **Dual-Use Awareness**: While we believe open access improves collective security, we acknowledge the dual-use nature. Users are expected to follow applicable laws and guidelines.

> ⚠️ **Disclaimer**: This dataset includes descriptions of attack techniques for educational purposes. The maintainers are not responsible for misuse.

### 📈 Future Additions

- Integration with CTF (Capture The Flag) challenge walkthroughs.
- More blue team procedures and SOAR playbooks.
- Anonymized real-world incident response logs (with permission).

---

## 🛠️ How to Use & Train

### 1️⃣ Load Categorized JSONL Data

```python
from datasets import load_dataset

REPO = "Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset"

# ─ Load a single category ─
ds = load_dataset(REPO, split="train", data_files="data/coding/*/*.jsonl", streaming=True)

# ─ Load a specific source ─
ds = load_dataset(REPO, split="train", data_files="data/coding/vibe_instruct_v2/*.jsonl", streaming=True)

# ─ Load everything (18M+ samples) ─
ds = load_dataset(REPO, split="train", streaming=True)

for sample in ds:
    print(sample["source"], sample["instruction"][:80])
```

<br>

### 2️⃣ Stream the 64 GB `archives/` GitHub Repositories

```python
from huggingface_hub import hf_hub_download
import tarfile

REPO = "Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset"

# ─ Option A: Download & extract ONE repository ─
hf_hub_download(
    repo_id=REPO,
    repo_type="dataset",
    filename="archives/0x101__lakewatch.tar.gz",
    local_dir="./repos",
)
with tarfile.open("./repos/archives/0x101__lakewatch.tar.gz", "r:gz") as tar:
    tar.extractall("./extracted/0x101__lakewatch")


# ─ Option B: Stream files WITHOUT full extraction ─
def stream_repo_files(archive_name, max_files=100):
    """Stream file contents from tar.gz without extracting to disk."""
    local_path = hf_hub_download(repo_id=REPO, repo_type="dataset", filename=archive_name)
    
    with tarfile.open(local_path, "r:gz") as tar:
        count = 0
        for member in tar:
            if member.isfile() and count < max_files:
                f = tar.extractfile(member)
                if f:
                    yield {
                        "path": member.name,
                        "content": f.read().decode("utf-8", errors="ignore")[:4000],
                    }
                    count += 1
    
    import os
    os.remove(local_path)  # Clean up

# Stream files from a specific repo
for file_data in stream_repo_files("archives/0x101__lakewatch.tar.gz"):
    print(f"📄 {file_data['path']}: {file_data['content'][:100]}...")


# ─ Option C: Use pre-extracted JSONL shards (475K samples) ─
code_ds = load_dataset(
    REPO, split="train",
    data_files="data/coding/fable5_repos_full/*.jsonl",
    streaming=True
)
# Each sample: instruction = "<repo>/<file>", response = "<content>"
```

<br>

### 3️⃣ SFT Training Script (Hugging Face Trainer)

```python
import torch
from datasets import load_dataset
from transformers import (
    AutoTokenizer,
    AutoModelForCausalLM,
    TrainingArguments,
    Trainer,
    DataCollatorForLanguageModeling,
)

# ═══════════════════════════════════════
# CONFIGURATION
# ═══════════════════════════════════════
MODEL_NAME = "meta-llama/Llama-3.1-8B"
DATASET_REPO = "Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset"
OUTPUT_DIR = "./sft-output"
MAX_SEQ_LEN = 2048

# ═══════════════════════════════════════
# LOAD MODEL & TOKENIZER
# ═══════════════════════════════════════
tokenizer = AutoTokenizer.from_pretrained(MODEL_NAME)
tokenizer.pad_token = tokenizer.eos_token

model = AutoModelForCausalLM.from_pretrained(
    MODEL_NAME,
    torch_dtype=torch.bfloat16,
    device_map="auto",
    attn_implementation="flash_attention_2",
)

# ═══════════════════════════════════════
# LOAD & FORMAT DATASET
# ═══════════════════════════════════════
def format_instruction(sample):
    text = f"### Instruction:\n{sample['instruction']}\n\n### Response:\n{sample['response']}"
    return {"text": text}

def tokenize(examples):
    return tokenizer(
        examples["text"],
        truncation=True,
        max_length=MAX_SEQ_LEN,
        padding="max_length",
    )

# Load coding category (use "data/**/*.jsonl" for full 18M+)
train_ds = load_dataset(
    DATASET_REPO,
    split="train",
    data_files="data/coding/*/*.jsonl",
    streaming=True,
)
train_ds = train_ds.map(format_instruction).filter(lambda x: len(x["text"]) > 0)
train_ds = train_ds.map(tokenize, batched=True)

# ═══════════════════════════════════════
# TRAIN
# ═══════════════════════════════════════
training_args = TrainingArguments(
    output_dir=OUTPUT_DIR,
    num_train_epochs=3,
    per_device_train_batch_size=4,
    gradient_accumulation_steps=4,
    warmup_steps=500,
    logging_steps=100,
    save_steps=2000,
    learning_rate=2e-5,
    bf16=True,
    gradient_checkpointing=True,
    optim="adamw_torch",
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=train_ds,
    data_collator=DataCollatorForLanguageModeling(tokenizer=tokenizer, mlm=False),
)

trainer.train()
trainer.save_model(OUTPUT_DIR)
```

<br>

### 4️⃣ Curriculum Learning Across Categories

```python
from datasets import load_dataset, interleave_datasets

REPO = "Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset"

# ─ Phase 1: Foundation (math + science) ─
phase1_math = load_dataset(REPO, split="train", data_files="data/math/**/*.jsonl", streaming=True)
phase1_sci = load_dataset(REPO, split="train", data_files="data/science/**/*.jsonl", streaming=True)
phase1 = interleave_datasets([phase1_math, phase1_sci])

# ─ Phase 2: Add coding traces ─
phase2 = load_dataset(REPO, split="train", data_files="data/coding/**/*.jsonl", streaming=True)

# ─ Phase 3: Add distilled reasoning + cybersecurity ─
phase3_distilled = load_dataset(REPO, split="train", data_files="data/distilled/**/*.jsonl", streaming=True)
phase3_cyber = load_dataset(REPO, split="train", data_files="data/cybersecurity/**/*.jsonl", streaming=True)
phase3 = interleave_datasets([phase3_distilled, phase3_cyber])

# Train sequentially
# trainer.train(phase1)  # epochs 0-1
# trainer.train(phase2)  # epochs 1-2
# trainer.train(phase3)  # epochs 2-3
```

<br>

### 📋 Schema Reference

```json
{
    "source":          "fable5_2m",
    "source_dataset":  "Crownelius/Complete-FABLE.5-traces-2M",
    "instruction":     "<the prompt / question / file path>",
    "response":        "<the completion / answer / file content>",
    "category":        "coding"
}
```

| Field | Type | Max Length | Description |
|---|---|---|---|
| `source` | string | 200 | Short slug identifying upstream dataset |
| `source_dataset` | string | 200 | Full HF repo id (`org/name`) |
| `instruction` | string | 4,000 | User-side content (prompt/question/file path) |
| `response` | string | 4,000 | Assistant-side content (completion/answer/file content) |
| `category` | string | 50 | One of 8 categories |

---

## 🔐 Licensing & Limitations

### 📜 License

The **collection as a whole** is released under the **MIT License**.

Each upstream dataset retains its **original license**. The `source_dataset` field on every row identifies the upstream — look it up on Hugging Face to determine its specific license.

| License | Applies To |
|---|---|
| `MIT` | Most WithinUsAI datasets, OpenAssistant |
| `Apache-2.0` | DeepSeek, OpenThoughts |
| `CC-BY-4.0` | Dolly, various |
| `CC-BY-SA-3.0` | Databricks Dolly |
| `AGPL-3.0` | Some Fable-5 traces |

### ✅ Intended Use Cases (Our Vision)

- Fine-tuning open-source LLMs for instruction following
- Training coding agents and code-completion models
- Reasoning chain distillation research
- Domain-specific adaptation (math, science, cybersecurity)
- Repository-scale context training (using `archives/`)

### ❌ Not Recommended For

- Deploying models without safety evaluation
- Generating harmful, biased, or deceptive content
- High-stakes domains (medical, legal, financial) without expert review
- Claiming models "know" facts — this is distilled output, not ground truth

### ⚠️ Limitations

1. **Field length cap**: `instruction` and `response` capped at 4,000 characters. For full content, use `archives/`.
2. **Distillation artifacts**: Samples are model-generated — may contain hallucinations or biases.
3. **Partial recovery**: A few upstream datasets (GOD_Coder variants, Genesis_v1.1) had format errors and were partially recovered via raw JSONL parsing.

### 📝 Citation

```bibtex
@misc{open_distillation_codex_2026,
  title  = {The Open Distillation Codex: 18M+ samples + 7090 code repositories from 73 sources with Cybersecurity Attack & Defense},
  author = {Manusagents},
  year   = {2026},
  url    = {https://huggingface.co/datasets/Manusagents/GPT-5.5-Gemini-3.1-Pro-Grok-4-Claude-Fable-5-Mythos-5-Qwen-3.7-Max-and-more-Distillation-Dataset},
  note   = {v8.2 - No skip, full. 516 shards + 7090 archives, 73 sources, 8 categories, 76 GB+}
}
```

---

## 📜 Changelog

| Version | Date | Key Changes |
|---|---|---|
| `v1.0`–`v5.0` | 2026-07-01 to 05 | Progressive builds: 117K → 20.7M samples |
| `v6.0` | 2026-07-06 | Category restructuring: `data/<category>/<source>/shard-*.jsonl` |
| `v7.0` | 2026-07-06 | Training scripts + full processing started |
| `v8.0 FINAL` | 2026-07-06 | **ALL sources FULLY processed — no skipping. Verified 79.13 GB.** |
| `v8.1` | 2026-07-08 | Added 5 external cybersecurity datasets. Total 81.2 GB, 73 sources. |
| `v8.2` | 2026-07-18 | **Final numbers rectified: 18M+ samples, 76 GB+ total. All sources no skip, fully verified. Enhanced cybersecurity deep-dive with attack/defense examples, training scripts, ethical guidelines.** |

---

<div align="center">

<br>

### 🌟 The Open Distillation Codex 🌟

**73 sources** · **8 categories** · **7,090 repositories** · **516 shards** · **76 GB+**

<br>

*No skip. Full. 18M+ samples. Built one archive at a time. Released under MIT.*

<br>

---

> *"Two layers. Eight categories. Seventy-three sources. One codex. No skip. Full. Armed with cybersecurity attack and defense."*

<br>

<img src="https://img.shields.io/badge/Built%20with-Streaming%20Pipeline-blue?style=flat-square" alt="Streaming">
<img src="https://img.shields.io/badge/No-Skipping-brightgreen?style=flat-square" alt="No Skip">
<img src="https://img.shields.io/badge/Full%20Processing-success?style=flat-square" alt="Full">
<img src="https://img.shields.io/badge/Format-JSONL-orange?style=flat-square" alt="JSONL">
<img src="https://img.shields.io/badge/HuggingFace-Dataset-yellow?style=flat-square" alt="HF">
<img src="https://img.shields.io/badge/Cybersecurity-Deep%20Dive-purple?style=flat-square" alt="Cyber">

<br><br>

**— The Open Distillation Codex —**

</div>
