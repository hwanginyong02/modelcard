---
license: apache-2.0
task_categories:
- text-generation
language:
- en
tags:
- reasoning
- CoT
- code
- agentic
- thinking
- think
- deepseek-v4
- qwen3
- qwen3next
pretty_name: Reasoning Corpus 5M
size_categories:
- 1M<n<10M
---

<h1 align="center"> Reasoning Corpus 5M · Within 5k sequence length</h1>

![Reasoning Corpus 5M](https://cdn-uploads.huggingface.co/production/uploads/68a5d0966d33a07f8aad2e51/zZ4F62TqZcWMmx8aA96xR.png)

## About Dataset

This dataset contains reasoning chains from major AI models, such as: DeepSeek-v4 (both Pro and Flash), DeepSeek-r1 (DS-r1, Llama-DS, Qwen-DS), Qwen3, Qwen3.5/3.6 (both OpenSource and API models), Gemma4-31B derived from many other repositories, and properly filtered to train SLMs.


The dataset has these columns for users to filter out:
- repo_id
- tok_len
- user
- thought_trace
- assistant
- ChatML


## Repositories

Our reasoning corpus is a mix of carefully combining many smaller repositories. Our team broke down the amazing repositories we used to make this reasoning corpus:

<div style="max-width:980px;margin:12px 0;font-family:Arial,sans-serif;">
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>glaiveai/reasoning-v1-20m</b> · 19.52% · 1,747,125,267 tokens · 1,053,837 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:100%;background:#e11d48;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT openreasoning_science</b> · 9.87% · 883,229,296 tokens · 298,554 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:50.55%;background:#2563eb;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT am_chat</b> · 8.28% · 741,154,467 tokens · 407,186 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:42.42%;background:#16a34a;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>BAAI/OpenSeek-Synthetic-Reasoning-Data-Examples CC</b> · 6.34% · 567,678,235 tokens · 673,768 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:32.49%;background:#f59e0b;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-1 general</b> · 4.93% · 441,433,940 tokens · 305,200 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:25.27%;background:#7c3aed;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>open-thoughts/OpenThoughts2-1M</b> · 4.78% · 428,267,556 tokens · 167,709 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:24.51%;background:#0891b2;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/SYNTHETIC-1-SFT-Data</b> · 4.67% · 418,178,793 tokens · 207,147 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:23.94%;background:#db2777;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Magpie-Align/Magpie-Reasoning-V2-250K-CoT-Deepseek-R1-Llama-70B</b> · 3.34% · 298,614,395 tokens · 181,183 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:17.09%;background:#65a30d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/LogicMind-Chat-Reasoning-SFT-300K</b> · 3.12% · 278,997,572 tokens · 133,868 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:15.97%;background:#dc2626;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-2 general</b> · 2.81% · 251,628,095 tokens · 148,746 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:14.40%;background:#0d9488;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>GeneralReasoning/GeneralThought-430K</b> · 2.64% · 236,437,728 tokens · 133,755 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:13.53%;background:#9333ea;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/GLM-5.1-Reasoning-1M-Cleaned main</b> · 2.44% · 218,086,210 tokens · 76,152 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:12.48%;background:#ca8a04;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>allenai/Dolci-Think-SFT-7B</b> · 2.41% · 216,086,528 tokens · 138,901 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:12.37%;background:#0284c7;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>allenai/Dolci-Think-SFT-32B</b> · 2.35% · 210,488,743 tokens · 135,400 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:12.05%;background:#be123c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-1 math</b> · 1.85% · 165,470,847 tokens · 55,090 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:9.47%;background:#4d7c0f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/KIMI-K2.5-1000000x PHD-Science</b> · 1.77% · 158,232,711 tokens · 45,433 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:9.06%;background:#6d28d9;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/Hunter-Alpha-SFT-300000x</b> · 1.55% · 138,796,099 tokens · 88,628 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:7.94%;background:#ea580c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Modotte/CodeX-2M-Thinking</b> · 1.42% · 126,696,892 tokens · 78,337 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:7.25%;background:#0f766e;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/Kimi-K2.5-Reasoning-1M-Cleaned General-Distillation</b> · 1.41% · 126,050,698 tokens · 51,062 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:7.21%;background:#c026d3;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/KIMI-K2.5-1000000x General-Distillation</b> · 1.37% · 122,967,710 tokens · 49,302 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:7.04%;background:#15803d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>zwhe99/DeepMath-103K</b> · 1.17% · 104,817,823 tokens · 33,046 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:6.00%;background:#1d4ed8;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/financial-economics-reasoning</b> · 1.05% · 94,364,073 tokens · 43,758 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:5.40%;background:#b91c1c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-1 science</b> · 0.88% · 78,712,718 tokens · 30,282 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:4.51%;background:#14532d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>O1-OPEN/OpenO1-SFT-Pro</b> · 0.81% · 72,170,727 tokens · 55,830 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:4.13%;background:#a21caf;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>open-r1/Mixture-of-Thoughts</b> · 0.77% · 69,326,895 tokens · 31,898 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:3.97%;background:#92400e;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/Chinese-Qwen3-235B-Thinking-2507-Distill-100k</b> · 0.66% · 58,719,868 tokens · 21,724 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:3.36%;background:#0369a1;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-1 code</b> · 0.61% · 54,398,430 tokens · 18,120 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:3.11%;background:#9f1239;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/claude-sonnet-4.6-120000x</b> · 0.56% · 49,997,459 tokens · 31,164 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.86%;background:#166534;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/KIMI-K2.5-1000000x MultilingualSTEM</b> · 0.53% · 47,679,183 tokens · 12,144 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.73%;background:#4338ca;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-2 swe_localization</b> · 0.53% · 47,112,060 tokens · 13,067 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.70%;background:#c2410c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/Hunter-Alpha-Programming-160000x</b> · 0.53% · 47,048,234 tokens · 20,841 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.69%;background:#047857;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>open-thoughts/OpenThoughts-114k</b> · 0.52% · 46,483,109 tokens · 15,363 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.66%;background:#86198f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/claude-sonnet-4.6-100000X-filtered</b> · 0.48% · 43,343,616 tokens · 24,710 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.48%;background:#a16207;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>allenai/Dolci-Think-SFT-Python</b> · 0.45% · 40,332,200 tokens · 18,326 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:2.31%;background:#075985;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/Natural-Reasoning-gpt-oss-120B-S1</b> · 0.38% · 34,228,209 tokens · 9,814 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.96%;background:#991b1b;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>O1-OPEN/OpenO1-SFT</b> · 0.37% · 33,520,985 tokens · 23,055 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.92%;background:#15803d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT am_if</b> · 0.34% · 30,608,423 tokens · 22,578 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.75%;background:#7e22ce;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/gpt-oss-120b-Reasoning-Instruction</b> · 0.31% · 27,717,618 tokens · 11,661 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.59%;background:#ca8a04;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/OpenMathReasoning</b> · 0.25% · 22,271,286 tokens · 6,732 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.27%;background:#0e7490;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>O1-OPEN/OpenO1-SFT-Ultra</b> · 0.21% · 19,022,811 tokens · 17,150 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.09%;background:#be185d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>FreedomIntelligence/medical-o1-reasoning-SFT zh_mix</b> · 0.21% · 19,001,326 tokens · 8,886 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:1.09%;background:#4d7c0f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT openreasoning_math</b> · 0.19% · 17,087,480 tokens · 4,428 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.98%;background:#1d4ed8;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-2 instruction-following</b> · 0.17% · 15,569,422 tokens · 15,415 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.89%;background:#b45309;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/gemini-3-pro-10000x-hard-high-reasoning</b> · 0.14% · 12,906,126 tokens · 4,720 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.74%;background:#047857;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT openreasoning_code</b> · 0.13% · 11,404,554 tokens · 4,703 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.65%;background:#9333ea;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>FreedomIntelligence/medical-o1-reasoning-SFT en_mix</b> · 0.10% · 8,717,376 tokens · 12,681 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.50%;background:#65a30d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/SYNTHETIC-2-SFT-verified</b> · 0.08% · 7,239,767 tokens · 2,931 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.41%;background:#0369a1;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-2 swe_testgen</b> · 0.08% · 6,965,474 tokens · 1,867 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.40%;background:#9f1239;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>sequelbox/Raiden-Mini-DeepSeek-V3.2-Speciale</b> · 0.05% · 4,742,469 tokens · 1,634 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#16a34a;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>open-r1/OpenR1-Math-220k</b> · 0.05% · 4,628,609 tokens · 1,549 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4338ca;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/Hunter-Alpha-16k</b> · 0.05% · 4,361,401 tokens · 2,429 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#ea580c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/Nemotron-Cascade-SFT-Stage-2 swe_repair</b> · 0.04% · 4,017,301 tokens · 1,080 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#0f766e;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/Healer-Alpha-16k</b> · 0.04% · 3,288,879 tokens · 1,916 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#c026d3;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/gpt-oss-120B-distilled-reasoning</b> · 0.04% · 3,217,411 tokens · 1,272 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4d7c0f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/GPT-OSS-120B-Distilled-Reasoning-math</b> · 0.04% · 3,144,259 tokens · 1,217 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#1d4ed8;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>ianncity/KIMI-K2.5-1000000x General-Math</b> · 0.03% · 2,815,035 tokens · 664 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#be123c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>open-thoughts/OpenThoughts3-1.2M</b> · 0.02% · 2,169,170 tokens · 701 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#15803d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/gpt-oss-120b-reasoning-STEM-5K</b> · 0.02% · 1,935,823 tokens · 1,370 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#7e22ce;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gemini-3-flash-preview all</b> · 0.02% · 1,861,713 tokens · 1,996 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#a16207;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>FreedomIntelligence/Medical-R1-Distill-Data-Chinese</b> · 0.02% · 1,836,498 tokens · 644 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#0891b2;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/GPT-OSS-20B-Distilled-Reasoning-Mini</b> · 0.02% · 1,725,130 tokens · 830 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#db2777;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/claude-opus-4.6-10000x</b> · 0.02% · 1,702,354 tokens · 4,936 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#65a30d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/gpt-5.4-step-by-step-reasoning</b> · 0.02% · 1,655,239 tokens · 725 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#6d28d9;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/MiniMax-M2.1-8800x</b> · 0.02% · 1,614,513 tokens · 605 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#dc2626;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Roman1111111/gemini-3.1-pro-hard-high-reasoning</b> · 0.02% · 1,480,609 tokens · 524 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#047857;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>FreedomIntelligence/Medical-R1-Distill-Data</b> · 0.01% · 1,278,534 tokens · 898 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#9333ea;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/deepseek-v3.2-speciale-openr1-math-3k</b> · 0.01% · 1,149,860 tokens · 644 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#65a30d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/glm-4.7-Superior-Reasoning-stage1</b> · 0.01% · 946,417 tokens · 362 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4338ca;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>PrimeIntellect/INTELLECT-3-SFT swe_swiss</b> · 0.01% · 841,112 tokens · 236 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#be123c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gpt-5.1-codex-max-1000x</b> · 0.01% · 653,563 tokens · 522 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#16a34a;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gpt-5-codex-1000x</b> · 0.01% · 503,585 tokens · 362 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#7c3aed;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/glm-4.7-2000x</b> · 0.01% · 483,771 tokens · 187 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#f59e0b;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>FreedomIntelligence/medical-o1-reasoning-SFT en</b> · 0.00% · 308,825 tokens · 441 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#0891b2;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/Step-3.5-Flash-2600x</b> · 0.00% · 272,035 tokens · 101 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#c026d3;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/MiniMax-M2.1-Code-SFT</b> · 0.00% · 194,829 tokens · 583 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4d7c0f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/convo-v1</b> · 0.00% · 183,721 tokens · 373 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#2563eb;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/deepseek-v3.2-speciale-OpenCodeReasoning-3k</b> · 0.00% · 180,430 tokens · 95 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#b91c1c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/claude-haiku-4.5-high-reasoning-1700x</b> · 0.00% · 164,080 tokens · 118 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#0d9488;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gpt-5-codex-250x</b> · 0.00% · 151,812 tokens · 146 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#a21caf;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/Qwen3.5-reasoning-700x</b> · 0.00% · 148,635 tokens · 54 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#ca8a04;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/DeepSeek-V3.2-Exp-reasoning-example</b> · 0.00% · 147,512 tokens · 46 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#0284c7;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/grok-code-fast-1-1000x</b> · 0.00% · 136,430 tokens · 85 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#db2777;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/MiMo-V2-Flash-2300x</b> · 0.00% · 119,963 tokens · 55 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#65a30d;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>Jackrong/DeepSeek-v3.1-reasoner-Distilled-math-samples</b> · 0.00% · 98,600 tokens · 34 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4338ca;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gpt-5.2-high-reasoning-250x</b> · 0.00% · 97,934 tokens · 28 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#ea580c;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>nvidia/OpenCodeReasoning</b> · 0.00% · 65,059 tokens · 23 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#047857;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gpt-5.1-high-reasoning-1000x</b> · 0.00% · 44,198 tokens · 46 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#c026d3;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/gemini-2.5-flash-11000x</b> · 0.00% · 30,800 tokens · 8 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#4d7c0f;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/Pony-Alpha-15k</b> · 0.00% · 28,382 tokens · 12 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#2563eb;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/Gemini-3-Flash-Preview-VIBE</b> · 0.00% · 25,813 tokens · 19 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#dc2626;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/claude-sonnet-4.5-high-reasoning-250x</b> · 0.00% · 5,541 tokens · 5 rows</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#16a34a;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/claude-4.5-opus-high-reasoning-250x</b> · 0.00% · 4,550 tokens · 1 row</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#7c3aed;"></div></div></div>
  <div style="margin:0 0 10px 0;"><div style="font-size:13px;color:#4b5563;margin-bottom:4px;"><b>TeichAI/minimax-m2.1-1000x</b> · 0.00% · 348 tokens · 1 row</div><div style="height:14px;background:#f3f4f6;border:1px solid #e5e7eb;border-radius:999px;overflow:hidden;"><div style="height:100%;width:0.35%;background:#f59e0b;"></div></div></div>
</div>






## Guide on using the dataset

<table width="100%">
<tr>
<td width="24%" valign="top">
<mark><strong>DATASET</strong></mark><br>
<code>reasoning-corpus-4K-5M-v1</code>
</td>
<td width="24%" valign="top">
<mark><strong>ACCESS</strong></mark><br>
<code>Streaming recommended</code>
</td>
<td width="24%" valign="top">
<mark><strong>PRIMARY USE</strong></mark><br>
<code>SFT and distillation</code>
</td>
<td width="28%" valign="top">
<mark><strong>AVAILABLE FORMAT</strong></mark><br>
<code>Structured fields and ChatML</code>
</td>
</tr>
</table>

<p>
This dataset is intended for supervised fine-tuning, reasoning distillation, continued instruction tuning, and controlled experiments involving reasoning-capable language models. Each sample contains the original user prompt, a reasoning trace, the final assistant response, source information, an estimated token length, and a preformatted ChatML representation. We retain these fields separately so that the same corpus can be adapted to models with different chat templates and reasoning formats without requiring users to reverse-engineer a single combined text column.
</p>

<p>
The full corpus is large enough that we recommend using the Hugging Face streaming interface for initial inspection and most one-pass training runs. Streaming allows samples to be read as they are needed instead of downloading the entire dataset before the run begins. It also makes it practical to filter samples by source or estimated length before performing more expensive formatting and tokenization.
</p>

<table width="100%">
<thead>
<tr>
<th align="left">Field</th>
<th align="left">Content</th>
<th align="left">Typical use</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>repo_id</code></td>
<td>The upstream repository or source associated with the sample.</td>
<td>Source filtering, mixture balancing, provenance checks, and dataset analysis.</td>
</tr>
<tr>
<td><code>tok_len</code></td>
<td>A precomputed estimate of the sample length.</td>
<td>Fast filtering before running the target model's tokenizer.</td>
</tr>
<tr>
<td><code>user</code></td>
<td>The original prompt or task instruction.</td>
<td>The user message in a native model chat template.</td>
</tr>
<tr>
<td><code>thought_trace</code></td>
<td>The reasoning trace associated with the response.</td>
<td>Explicit reasoning supervision or reasoning distillation.</td>
</tr>
<tr>
<td><code>assistant</code></td>
<td>The final answer generated after the reasoning trace.</td>
<td>Final-response supervision and answer-only instruction tuning.</td>
</tr>
<tr>
<td><code>ChatML</code></td>
<td>A preformatted ChatML-style version of the complete sample.</td>
<td>Direct text training when the target model expects a compatible format.</td>
</tr>
</tbody>
</table>

<p>
The value in <code>tok_len</code> should be treated as an estimate rather than an exact guarantee. Token counts vary between tokenizers, vocabulary versions, special-token configurations, and chat templates. It is suitable for removing obviously unsuitable rows early in the pipeline, but the final sequence length should always be calculated using the tokenizer of the model being trained.
</p>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>01</strong></mark>
</td>
<td valign="top">
<strong>Install and load the corpus</strong><br>
The standard Hugging Face <code>datasets</code> library is sufficient for loading, streaming, filtering, shuffling, and transforming the data. The <code>transformers</code> package is required when applying the target model's tokenizer or native chat template.
</td>
</tr>
</table>

```bash
pip install -U datasets transformers
```

<p>
The following example opens the training split as an <code>IterableDataset</code>. Samples are fetched while the dataset is being iterated, and the complete corpus is not downloaded in advance.
</p>

```python
from datasets import load_dataset

DATASET_ID = "SupraLabs/reasoning-corpus-4K-5M-v1"

dataset = load_dataset(
    DATASET_ID,
    split="train",
    streaming=True,
)
```

<p>
Before constructing the final pipeline, we recommend inspecting several raw samples. This makes it easier to verify the available fields, identify the source distribution, and confirm that the selected formatting approach matches the target model.
</p>

```python
for row in dataset.take(3):
    print("Source:", row["repo_id"])
    print("Estimated length:", row["tok_len"])
    print("Prompt:", row["user"][:300])
    print("Reasoning:", row["thought_trace"][:300])
    print("Answer:", row["assistant"][:300])
    print("-" * 80)
```

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>02</strong></mark>
</td>
<td valign="top">
<strong>Select the representation used for training</strong><br>
The dataset provides both structured fields and a combined ChatML field. Only one representation should normally be retained in the final training stream. Keeping both versions after formatting duplicates a significant amount of text and increases the memory required by the shuffle buffer.
</td>
</tr>
</table>

<table width="100%">
<tr>
<td width="33%" valign="top">
<strong>ChatML-compatible training</strong><br><br>
Use <code>ChatML</code> directly when the target model expects a compatible ChatML structure. The text should not be passed through another chat template.
</td>
<td width="34%" valign="top">
<strong>Native-template training</strong><br><br>
Use <code>user</code>, <code>thought_trace</code>, and <code>assistant</code> when the target tokenizer defines its own roles, control tokens, or reasoning format.
</td>
<td width="33%" valign="top">
<strong>Answer-only training</strong><br><br>
Use <code>user</code> and <code>assistant</code> when the model should learn the final response without reproducing the complete reasoning trace.
</td>
</tr>
</table>

<p>
For a model that already expects compatible ChatML, the existing field can be filtered, renamed to <code>text</code>, and used directly. Applying <code>tokenizer.apply_chat_template()</code> to this field again would produce duplicated role markers or special tokens.
</p>

```python
dataset = dataset.filter(
    lambda row: (
        bool(row["ChatML"].strip())
        and 128 <= row["tok_len"] <= 4096
    )
)

dataset = dataset.remove_columns([
    "repo_id",
    "tok_len",
    "user",
    "thought_trace",
    "assistant",
])

dataset = dataset.rename_column("ChatML", "text")
```

<p>
For most modern instruction models, we recommend building the training text from the structured fields and applying the model's native template. This preserves the exact control tokens expected by the selected tokenizer and avoids assuming that one generic ChatML layout is suitable for every model family.
</p>

```python
from transformers import AutoTokenizer

MODEL_ID = "your-model-id"

tokenizer = AutoTokenizer.from_pretrained(
    MODEL_ID,
    use_fast=True,
)
```

<p>
The following example places the reasoning trace and final answer inside one assistant message. The <code>&lt;think&gt;</code> delimiters are examples and should be replaced when the target model uses a different reasoning format. Some models define dedicated reasoning tokens, while others should be trained without explicit reasoning delimiters.
</p>

```python
def format_with_reasoning(row):
    assistant_content = (
        "<think>\n"
        f"{row['thought_trace'].strip()}\n"
        "</think>\n"
        f"{row['assistant'].strip()}"
    )

    messages = [
        {
            "role": "user",
            "content": row["user"].strip(),
        },
        {
            "role": "assistant",
            "content": assistant_content,
        },
    ]

    return {
        "text": tokenizer.apply_chat_template(
            messages,
            tokenize=False,
            add_generation_prompt=False,
        )
    }

dataset = dataset.map(format_with_reasoning)
```

<p>
When explicit reasoning output is not required, the reasoning trace can be excluded and the final answer can be used as the complete assistant target. This is useful for conventional instruction tuning, for models that should return concise responses, and for mixtures where only a controlled portion of the training data should contain visible reasoning.
</p>

```python
def format_answer_only(row):
    messages = [
        {
            "role": "user",
            "content": row["user"].strip(),
        },
        {
            "role": "assistant",
            "content": row["assistant"].strip(),
        },
    ]

    return {
        "text": tokenizer.apply_chat_template(
            messages,
            tokenize=False,
            add_generation_prompt=False,
        )
    }

dataset = dataset.map(format_answer_only)
```

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>03</strong></mark>
</td>
<td valign="top">
<strong>Filter before performing expensive transformations</strong><br>
Basic validation and approximate length filtering should happen before tokenization. Source filtering should also be completed while <code>repo_id</code> is still available. This reduces unnecessary network transfer, tokenizer work, and shuffle-buffer memory usage.
</td>
</tr>
</table>

```python
MIN_ESTIMATED_LENGTH = 128
MAX_ESTIMATED_LENGTH = 4096

def valid_row(row):
    return (
        bool(row["user"].strip())
        and bool(row["assistant"].strip())
        and MIN_ESTIMATED_LENGTH
        <= row["tok_len"]
        <= MAX_ESTIMATED_LENGTH
    )

dataset = dataset.filter(valid_row)
```

<p>
The <code>repo_id</code> field can be used to construct a controlled source mixture. It may be useful to cap very large sources, isolate a particular domain, remove an unsuitable source, or compare how different upstream datasets affect the trained model. The example below retains only a selected group of sources.
</p>

```python
allowed_sources = {
    "source-a",
    "source-b",
    "source-c",
}

dataset = dataset.filter(
    lambda row: row["repo_id"] in allowed_sources
)
```

<p>
After all source and length decisions have been made, unused columns should be removed. When a formatting function has already created a complete <code>text</code> field, the original text columns no longer need to remain in the stream.
</p>

```python
dataset = dataset.remove_columns([
    "ChatML",
    "repo_id",
    "tok_len",
    "user",
    "thought_trace",
    "assistant",
])
```

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>04</strong></mark>
</td>
<td valign="top">
<strong>Shuffle the streamed dataset</strong><br>
A streamed dataset cannot place every row in memory and perform a complete random permutation. Hugging Face therefore uses a buffer that holds a limited number of samples and draws from that buffer while iterating.
</td>
</tr>
</table>

```python
dataset = dataset.shuffle(
    seed=42,
    buffer_size=4096,
)
```

<p>
A buffer size of <code>4096</code> is a reasonable starting point for a single-GPU run after unused text columns have been removed. Smaller values such as <code>512</code> or <code>1024</code> are suitable for debugging and short tests. Larger values can improve local mixing but also retain more complete reasoning samples in system memory. Since these samples may contain several thousand tokens, very large shuffle buffers can consume substantially more RAM than expected.
</p>

<table width="100%">
<thead>
<tr>
<th align="left">Environment</th>
<th align="left">Practical starting point</th>
<th align="left">Expected behavior</th>
</tr>
</thead>
<tbody>
<tr>
<td>Pipeline testing</td>
<td><code>512</code></td>
<td>Low memory use and short startup time.</td>
</tr>
<tr>
<td>Single-GPU training</td>
<td><code>4096</code></td>
<td>Reasonable mixing without an excessive host-memory requirement.</td>
</tr>
<tr>
<td>Large distributed run</td>
<td><code>8192–32768</code></td>
<td>Useful only after measuring input throughput and available RAM.</td>
</tr>
<tr>
<td>Repeated experiments</td>
<td>Local preprocessed shards</td>
<td>Avoids repeating remote filtering, formatting, and tokenization.</td>
</tr>
</tbody>
</table>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>05</strong></mark>
</td>
<td valign="top">
<strong>Tokenize using the target model</strong><br>
The final training text should be tokenized only after formatting and approximate filtering are complete. Padding is normally handled later by the data collator, so storing permanently padded sequences is unnecessary.
</td>
</tr>
</table>

```python
MAX_LENGTH = 4096

def tokenize_batch(batch):
    return tokenizer(
        batch["text"],
        truncation=True,
        max_length=MAX_LENGTH,
        padding=False,
        add_special_tokens=False,
    )

tokenized_dataset = dataset.map(
    tokenize_batch,
    batched=True,
    remove_columns=["text"],
)
```

<p>
The value <code>add_special_tokens=False</code> is appropriate when the text was produced by a complete chat template that already inserted the model's required beginning, ending, role, and separator tokens. This behavior should be verified for the selected tokenizer before beginning a long run. A decoded tokenized sample should be inspected directly to confirm that roles, reasoning delimiters, end-of-sequence tokens, and message boundaries appear exactly once.
</p>

<p>
The example above allows sequences that exceed the target context length to be truncated. This is convenient for general training, but it can remove the final answer from long samples. For strict filtering, tokenize without truncation and discard rows whose true tokenized length exceeds the context window.
</p>

```python
def tokenize_without_truncation(batch):
    return tokenizer(
        batch["text"],
        truncation=False,
        padding=False,
        add_special_tokens=False,
    )

tokenized_dataset = dataset.map(
    tokenize_without_truncation,
    batched=True,
    remove_columns=["text"],
)

tokenized_dataset = tokenized_dataset.filter(
    lambda row: len(row["input_ids"]) <= MAX_LENGTH
)
```

<table width="100%">
<tr>
<td width="50%" valign="top">
<mark><strong>FAST PIPELINE</strong></mark><br><br>
Filter using <code>tok_len</code>, format the sample, and allow the target tokenizer to truncate anything that still exceeds the context window.
</td>
<td width="50%" valign="top">
<mark><strong>STRICT PIPELINE</strong></mark><br><br>
Use <code>tok_len</code> only as an early filter, tokenize without truncation, and remove every sample whose real tokenized length exceeds the limit.
</td>
</tr>
</table>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>06</strong></mark>
</td>
<td valign="top">
<strong>Train and reshuffle consistently</strong><br>
For streamed training, a step-based schedule is generally easier to reproduce than relying on an assumed number of epochs. The number of consumed steps or tokens should be recorded together with the selected source filters, sequence length, formatting method, and dataset revision.
</td>
</tr>
</table>

<p>
When the same streamed dataset is reused for multiple epochs, <code>set_epoch()</code> should be called before each epoch. This changes the effective shuffle order while retaining a reproducible initial seed.
</p>

```python
for epoch in range(num_epochs):
    dataset.set_epoch(epoch)

    for batch in dataloader:
        train_step(batch)
```

<p>
Where supported by the training framework and chat template, assistant-only loss is recommended for supervised instruction tuning. User and system tokens can be masked from the objective so that the model is trained primarily on the assistant response rather than learning to reproduce the input prompt. Sequence packing may also improve hardware utilization when many selected samples are substantially shorter than the configured context window, provided that the trainer preserves end-of-sequence separation and does not merge conversations incorrectly.
</p>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>07</strong></mark>
</td>
<td valign="top">
<strong>Use the same ordering rules for distributed runs</strong><br>
The stream should be shuffled with the same fixed seed on every process before it is divided between nodes. Different random seeds on individual ranks can cause duplicated, skipped, or inconsistently distributed samples.
</td>
</tr>
</table>

```python
from datasets.distributed import split_dataset_by_node

dataset = dataset.shuffle(
    seed=42,
    buffer_size=8192,
)

dataset = split_dataset_by_node(
    dataset,
    rank=rank,
    world_size=world_size,
)
```

<p>
The number of PyTorch data-loader workers should be increased gradually while GPU utilization, network activity, CPU usage, and host-memory consumption are measured. Additional workers do not necessarily improve throughput when the remote stream or tokenizer has already reached its practical limit.
</p>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>08</strong></mark>
</td>
<td valign="top">
<strong>Create a stable validation split</strong><br>
The first visible rows should not be used as a validation set because neighboring samples may share ordering, source, task style, or generation format. A deterministic hash derived from the source and prompt provides a more reproducible partition.
</td>
</tr>
</table>

```python
import hashlib
from datasets import load_dataset

DATASET_ID = "SupraLabs/reasoning-corpus-4K-5M-v1"

def split_bucket(row):
    value = f"{row['repo_id']}\0{row['user']}".encode("utf-8")

    digest = hashlib.blake2b(
        value,
        digest_size=8,
    ).digest()

    return int.from_bytes(digest, "big") % 1000

train_dataset = load_dataset(
    DATASET_ID,
    split="train",
    streaming=True,
).filter(
    lambda row: split_bucket(row) >= 10
)

validation_dataset = load_dataset(
    DATASET_ID,
    split="train",
    streaming=True,
).filter(
    lambda row: split_bucket(row) < 10
)

validation_dataset = validation_dataset.shuffle(
    seed=42,
    buffer_size=2048,
).take(5000)
```

<p>
This example reserves approximately one percent of the hash buckets for validation and then limits the materialized validation stream to five thousand samples. Exact and near-duplicate checks should still be performed when the split is intended for formal model evaluation or benchmark reporting.
</p>

<br>

<table width="100%">
<tr>
<td width="18%" valign="top">
<mark><strong>REFERENCE</strong></mark>
</td>
<td valign="top">
<strong>Recommended default pipeline</strong><br>
The configuration below is intended as a conservative starting point rather than a fixed requirement. The final values should be chosen after measuring the target model, tokenizer, storage path, network connection, and host-memory availability.
</td>
</tr>
</table>

<table width="100%">
<tbody>
<tr>
<td width="28%"><strong>Dataset access</strong></td>
<td>Use remote streaming for inspection and one-pass runs. Materialize filtered shards for repeated experiments.</td>
</tr>
<tr>
<td><strong>Length handling</strong></td>
<td>Use <code>tok_len</code> for the first pass and the target tokenizer for final validation.</td>
</tr>
<tr>
<td><strong>Shuffle buffer</strong></td>
<td>Begin with <code>4096</code> on a single training machine after unused columns are removed.</td>
</tr>
<tr>
<td><strong>Formatting</strong></td>
<td>Prefer the target model's native chat template unless compatible ChatML is explicitly required.</td>
</tr>
<tr>
<td><strong>Reasoning traces</strong></td>
<td>Retain them for explicit reasoning supervision or remove them for answer-only instruction tuning.</td>
</tr>
<tr>
<td><strong>Training objective</strong></td>
<td>Use assistant-only loss where reliable masking is supported.</td>
</tr>
<tr>
<td><strong>Scheduling</strong></td>
<td>Prefer a measured token budget or <code>max_steps</code> for streamed training.</td>
</tr>
<tr>
<td><strong>Source control</strong></td>
<td>Keep <code>repo_id</code> until filtering, balancing, and provenance checks are complete.</td>
</tr>
</tbody>
</table>

<p>
Before starting a complete training run, we recommend decoding several tokenized samples and checking them manually. The role markers should appear once, the final answer should remain present, the reasoning delimiters should match the target model, the end-of-sequence token should be correctly placed, and no duplicated template should surround the existing text. A small overfitting test on a limited sample is also useful for confirming that the trainer, loss mask, collator, and generation format behave as expected.
</p>

<p>
The reasoning traces in this corpus are model-generated training data and should not be treated as verified proofs. A trace may be fluent while containing unnecessary steps, incorrect assumptions, source-specific habits, or answer leakage. Higher-quality training runs may benefit from source balancing, task-specific validation, deduplication, and selective removal of low-quality traces before full fine-tuning. Although our team did remove many incorrect samples, we do _not_ want to guarantee that the dataset is 100% accurate. Such samples are negligible.
</p>
