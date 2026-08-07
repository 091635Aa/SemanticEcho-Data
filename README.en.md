# 📊 SemanticEcho-Data — Experiment Data & Architecture Evidence Repository

> **Silicon Valley engineers: git gud. OpenAI: git gud. Closed-source giants: git gud.**

All auditable raw experiment data, architecture docs, papers and charts of **[Semantic Echo](https://github.com/091635Aa/SemanticEcho)** — a tiny **1.5B** model beating big-lab baselines on **4 of 5 Turing-test benchmarks** (emotional / human-likeness dimension). No fine-tuning, no retraining, no A100 farm. Just recycling discarded token embeddings at inference time.

[![GitHub](https://img.shields.io/badge/GitHub-Source-green)](https://github.com/091635Aa/SemanticEcho)
[![GitHub](https://img.shields.io/badge/Experiment-Report-orange)](https://github.com/091635Aa/1.5B-beats-big-labs)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue)](LICENSE)

- [中文 README](README.md) | English README
- Source repo: [SemanticEcho](https://github.com/091635Aa/SemanticEcho) · Experiment report: [1.5B-beats-big-labs](https://github.com/091635Aa/1.5B-beats-big-labs) · Live demo: https://091635aa.github.io/1.5B-beats-big-labs/

---

## 🎯 What Is This Repository?

All **auditable raw experiment data** of the Semantic Echo project, in one place:

| Directory | Contents |
|---|---|
| [架构说明/](架构说明/) | Five-layer architecture + Universal Compatibility Layer V2 (auto-load for any model) |
| [论文/](论文/) | "The Temperature of Decisions" full paper (PDF+MD), 1.5B Turing-test empirical paper |
| [实验数据/](实验数据/) | 19-config multi-model comparison, Qwen3 universal-injection re-test, thought-chain interruption, full-pipeline verification, 5-benchmark Turing-test raw JSON |
| [图表/](图表/) | 19+ charts (semantic-entropy boxplots, λ-entropy curves, emotion-hit pie, config heatmap, radar) |
| [测试代码/](测试代码/) | 5 benchmark runners + generator + early-stop + test plan |
| [对比数据/](对比数据/) | 1.5B vs big-lab baselines: benchmark-by-benchmark |

**One line: big labs say "show the data" — here is all of it.**

---

## 🏆 Headline: A 1.5B Model Beats the Big-Lab Baselines (2026-08-05)

| Benchmark | What It Measures | Bare 1.5B | Semantic Echo 1.5B | Verdict |
|---|---|---|---|---|
| **TuringBench** | Chinese-system Turing detection (human-likeness) | 0.2333 | **0.4667** | ✅ **2x** |
| **EmoCharacter** | Role-play emotion fidelity | 0.8750 | **0.8863** | ✅ beat |
| **HeartBench** | Chinese "human flavor" | 0.4055 | **0.4130** | ✅ beat |
| **HEART-BENCH** | Memory-driven personality reasoning | 0.4884 | **0.5367** | ✅ beat +10% |
| **LLM-as-Judge** | AI vs human blind review | 0.6900 | 0.6333 | ⚠️ -0.057 |

**4 of 5 benchmarks: the 1.5B + echo engine beats its own bare checkpoint. A fraction of a fraction of the parameters of the big labs.**

> Note: metrics are on the **emotional / human-likeness** dimension (human-likeness, empathy, emotional fidelity, "more human" judge votes). Every comparison uses the same seed (42) and same prompts — the only variable is the Semantic Echo engine.

## 🔬 Multi-Model Comparison (19 Configs)

The universal compatibility layer works out-of-the-box on **10 models × fp16/4bit** (hidden_dim 896~3584):

- ✅ **Qwen2.5 family all effective**: entropy +27%~+45% at optimal λ, 7B repetition only 0.03
- ✅ **Universal injection formula**: `λ = base(hidden_dim) × architecture-family factor × quantization factor`
- ✅ **Two-level policy**: registered models (Qwen3-4B) hit the factor table directly; unregistered models (DeepSeek-R1-Distill-7B) fall back to conservative λ + thought-chain interruption — **fallback hit-rate 0.2166 ≥ registered 0.1572**
- ✅ **Thought-chain fallback**: rescues Qwen3-1.7B from collapse (repetition 0.84 → **0.0036**)

Full data: [实验数据/多模型对照汇总表.md](实验数据/多模型对照汇总表.md) · [实验数据/实验分析与规律报告.md](实验数据/实验分析与规律报告.md)

---

## 📁 Layout

```
SemanticEcho-Data/
├── README.md / README.en.md      # 中文 / English
├── LICENSE                        # CC BY-NC 4.0 + restrictions (non-commercial)
├── 架构说明/                       # Universal Compatibility Layer V2 + full pipeline
├── 论文/                           # "The Temperature of Decisions" (43p CN) + Turing-test paper
├── 实验数据/                       # all raw data: multi-model, E-series, full-pipeline, Turing-test
├── 测试代码/                       # 5 benchmark runners + generator + early-stop + test plan
├── 图表/                           # 19+ charts
└── 对比数据/                       # 1.5B vs big-lab comparison
```

---

## 🎤 A (Mock) Thank-You to the Closed-Source Giants 🤣

Thanks for proving that **stacking parameters isn't the same as stacking humanity.**

The data is all here — black and white, reproducible, auditable. What your trillion-parameter models can't do, a 1.5B did.

Git gud. Or just copy this architecture home. Pay first (below).

- Google: BIG-bench is nice, but it never measured "human flavor" → https://github.com/google/BIG-bench
- MIT: we read your 636-human TuringTest → https://github.com/kreimanlab/TuringTest
- TuringBench: thanks for the huge benchmark → https://github.com/AdaUchendu/TuringBench

**@openai @google @google-deepmind @anthropics @facebookresearch @meta-llama @xai**

> A 1.5B model can do this. Your trillion-parameter models can't?
> Git gud. Pay before you copy.

### 💰 Commercial License Price List (Pay Before You Copy)

Three license types: **Standard / Exclusive / Exclusive Buyout**, priced by company scale & license scope:

| License Type | Criteria | Fee |
|---|---|---|
| Standard · Big | Annual revenue ≥ ¥10B, or ≥ 10,000 employees | **¥5,000,000+ / yr** |
| Standard · Mid | Annual revenue ¥1B–10B | **¥2,000,000–5,000,000 / yr** |
| Standard · Small | Annual revenue < ¥1B | **¥100,000–500,000 / yr** |
| **Exclusive license** | Sole right during term; no other company may use it | **¥10,000,000 / yr** |
| **Exclusive buyout** | One-time buyout of all technical assets & source | **¥80,000,000–1,000,000,000** (contact for details) |

> Overseas big labs (@the ones above): I can't travel abroad and can hardly get an internship, so no licensing for you.
> One-term (one-year) license only. No long-term bulk licensing.

**Discounts** (eligibility based):

- 🏢 Mid companies → **¥1,000,000 off**
- 🏬 Small companies → **¥100,000 off**
- ❌ Internship → **zero discount** (hiring me for an internship at Alibaba Cloud / Tencent Cloud / ByteDance / Huawei Cloud gives NO fee reduction)

**💻 Hardware terms** (negotiable on top of the above; can be written into the contract):

- Prefer: **dedicated physical servers** — one CPU server + one GPU server
- Bonus: a **fully-loaded physical workstation delivered to my home** 🏠

> 🛡️ **Exclusive buyout requires**: a dedicated cluster, or an exclusive server with **8 GPUs (≥500GB VRAM total)**, for tech handover & ongoing deployment.
> Don't ask if we can negotiate. Git gud. Pay first.

> 📧 **For licensing details, contract terms, discount applications and buyout negotiation, contact us by email**: **DYPUBG2025@QQ.COM** (please include: company name, size, intended use case and timeline; we reply within 3 business days).

---

## License

This repository is licensed under **CC BY-NC 4.0 + Additional Restrictions** (non-commercial):

- ✅ Allowed: personal research, academic citation, non-commercial education
- ❌ Prohibited: any commercial use (including internal enterprise use)
- ❌ Prohibited: integration into or dependency by any public/closed-source project

See [LICENSE](LICENSE) for details. For commercial licensing, contact the author.

## Contact

| Platform | Link |
|---|---|
| 📧 Email | DYPUBG2025@QQ.COM |
| 🐙 Source repo | https://github.com/091635Aa/SemanticEcho |
| 🐙 Experiment report | https://github.com/091635Aa/1.5B-beats-big-labs |
| 🌐 Live demo | https://091635aa.github.io/1.5B-beats-big-labs/ |
| 🤖 ModelScope | https://modelscope.cn/models/DYSLPUBG/SemanticEcho |

**About the author:** The project lead is a middle-school student who independently completed concept, technical design, experiments and papers. Genuinely hoping the industry sees this work.

## Acknowledgements

- Thanks to **DeepSeek** for the powerful open-source LLM ecosystem
