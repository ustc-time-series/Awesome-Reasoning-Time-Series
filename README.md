# Awesome Reasoning Time Series

A curated collection of reasoning-aware time-series forecasting (TSF) methods, agentic systems, benchmarks, and related resources.

The forecasting core covers methods where explicit deliberation, latent reasoning, tool decisions, or verification affects a numerical forecast. Related time-series understanding and QA resources are identified separately. “Reasoning-aware” is a working curation scope, not a standardized task definition.

Last checked: 2026-11-03. The first release contains 33 records: 19 forecasting methods, 5 benchmarks/reliability studies, 4 related analysis resources, 4 foundations/boundary studies, and 1 survey. This is a curated snapshot, not an exhaustive systematic review or a performance ranking.

[中文调研与研究机会](docs/research-survey.zh-CN.md) · [Machine-readable catalog](data/papers.json) · [BibTeX](references.bib) · [Search and evidence notes](docs/search-and-evidence.md) · [Contributing](CONTRIBUTING.md)

## Contents

- [Scope and taxonomy](#scope-and-taxonomy)
- [Forecasting through explicit or latent reasoning](#forecasting-through-explicit-or-latent-reasoning)
- [Reasoning conditions a numerical forecaster](#reasoning-conditions-a-numerical-forecaster)
- [Agentic tools, memory, and reflection](#agentic-tools-memory-and-reflection)
- [Forecasting and reasoning benchmarks](#forecasting-and-reasoning-benchmarks)
- [Related understanding and analysis](#related-understanding-and-analysis)
- [Forecasting foundations and boundary studies](#forecasting-foundations-and-boundary-studies)
- [Surveys and broader resources](#surveys-and-broader-resources)
- [Reading path](#reading-path)
- [Evaluation and reproducibility](#evaluation-and-reproducibility)

## Scope and taxonomy

| Interface | What reasoning changes | Representative methods |
| --- | --- | --- |
| Reasoning → forecast | Intermediate deliberation precedes numeric output | TimeReasoner, Time-R1, ReasonCast joint generation |
| Reasoning → numerical model | Semantic features, control signals, ensemble weights, or corrections | STRIDE, KairosAgent, REATS, TimeOmni-VL, ReasonCast demand intervention |
| Reasoning → workflow | Retrieval, tool routing, memory, verification, or adaptation | AlphaCast, Cast-R1, MemCast, CastFSR, Nexus, SEER, TimEvolve |
| Reasoning → evaluation | Forecast rationale quality, evidence use, or contextual dependence | TFRBench, TSRBench, CiK, LEAF, COMMON-TSQA |

Categories overlap. The catalog retains a primary section and a scope tag. Latent computation, linguistic explanations, and tool execution are different mechanisms and need different evidence.

Dates in the tables are first arXiv submissions. Titles follow the checked latest version; venue years may be later. “Accepted” is kept distinct from a completed conference. “Author-reported” means venue status was found in author-maintained metadata. BibTeX entries cite the exact checked arXiv versions; the catalog stores venue evidence separately.

Code links identify author-associated releases that were inspected but not executed. “Partial code” and “Materials” describe a narrower release. “Not located” means no executable author-linked code was verified in the inspected sources; it does not establish that none exists. Dataset access may have additional conditions.

## Forecasting through explicit or latent reasoning

Reasoning produces a forecast, or additional latent deliberation participates in prediction. Mixed-task papers have an identified numerical forecasting component.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [ReasonCast: Towards Explainable Time Series Forecasting with Reasoning](https://arxiv.org/abs/2608.01875) | 2026-08-03 | arXiv preprint | A single autoregressive response produces structured reasoning followed by a numeric forecast. | [Code](https://github.com/seunghan96/reasoncast) |
| [Latent Chain-of-Thought Improves Structured-Data Transformers](https://arxiv.org/abs/2605.11262) | 2026-05-11 | arXiv preprint | Recurrent latent tokens provide extra computation for structured-data prediction, including time-series forecasting. | Code not located |
| [Eliciting Chain-of-Thought Reasoning for Time Series Analysis using Reinforcement Learning](https://arxiv.org/abs/2510.01116) | 2025-10-01 | arXiv preprint | Discrete time-series tokens, SFT, and verifiable-reward RL support CoT across tasks, including contextual numeric forecasting. Mixed tasks including forecasting. | Code not located |
| [TimeOmni-1: Incentivizing Complex Reasoning with Time Series in Large Language Models](https://arxiv.org/abs/2509.24803) | 2025-09-29 | [ICLR 2026](https://openreview.net/forum?id=kOIclg7muL) | Hierarchical reasoning SFT and task-grounded RL cover four tasks, including event-aware numerical forecasting. Mixed tasks including forecasting. | [Code](https://github.com/AntonGuan/TimeOmni-1) |
| [Time Series Forecasting via Reasoning: A Slow-Thinking Approach with Reinforcement Fine-Tuned LLMs](https://arxiv.org/abs/2506.10630) | 2025-06-12 | [CIKM 2026 (accepted)](https://api.crossref.org/works/10.1145/3799682.3840737) | Reasoning-trace SFT and forecasting-specific RL train an LLM to reason before generating a numeric sequence. | [Code](https://github.com/ustc-time-series/Time-R1) |
| [Can Slow-thinking LLMs Reason Over Time? Empirical Studies in Time Series Forecasting](https://arxiv.org/abs/2505.24511) | 2025-05-30 | [WSDM 2026](https://api.crossref.org/works/10.1145/3773966.3777931) | Training-free prompting compares one-shot, decoupled, and rollout reasoning for numerical forecasts. | [Code](https://github.com/ustc-time-series/TimeReasoner) |

## Reasoning conditions a numerical forecaster

The reasoning output controls a numerical decoder, ensemble, or semantic correction. These works overlap with agentic orchestration; placement records the main interface.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [ReasonCast: Agentic Demand Forecasting with Selective Semantic Reasoning](https://arxiv.org/abs/2608.15291) | 2026-08-15 | arXiv preprint | An agent converts event context into structured semantic fields and selectively corrects a Chronos-2 forecast. | [Code](https://github.com/ziyuey/ReasonCast) |
| [REATS: LLM Reasoning-based Ensemble Learning for Adaptive Time Series Forecasting](https://arxiv.org/abs/2608.10149) | 2026-08-10 | arXiv preprint | CoT SFT and GRPO train sample-specific ensemble weights over numerical forecasters. | [Code](https://github.com/microsoft/TimeCraft/tree/main/REATS) |
| [KairosAgent: Agentic Time Series Forecasting with Fused Semantic Reasoning](https://arxiv.org/abs/2605.30002) | 2026-05-28 | [EMNLP 2026](https://aclanthology.org/2026.emnlp-main.1343/) | Tool-assisted semantic descriptions of future morphology condition a numerical foundation-model decoder. | [Project](https://mldi.group/KairosAgent/) · Code not located |
| [STRIDE: Reasoning-Aware Training for Time Series Forecasting](https://arxiv.org/abs/2605.08625) | 2026-05-09 | arXiv preprint | Distilled reasoning hidden states become a continuous prior for a numerical time-series foundation model. | Code not located |
| [TimeOmni-VL: Unified Models for Time Series Understanding and Generation](https://arxiv.org/abs/2602.17149) | 2026-02-19 | [ICML 2026](https://proceedings.mlr.press/v306/guan26e.html) | Calibrated CoT guides generation through a bidirectional mapping between time series and images. Mixed tasks including forecasting. | [Code](https://github.com/AntonGuan/TimeOmni-VL) |

## Agentic tools, memory, and reflection

Reasoning organizes evidence gathering, expert selection, forecast revision, or delayed-feedback adaptation.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [SEER: Self-Evolving Event Reasoning and Retrieval for Time Series Forecasting](https://arxiv.org/abs/2610.04109) | 2026-10-02 | arXiv preprint | Error-driven reflection updates retrieval memory and persistent forecasting knowledge for a frozen LLM. Mixed tasks including forecasting. | [Materials](https://github.com/BennyTMT/SEER) · Executable code not verified |
| [When Tomorrow Becomes Today: Self-Evolving Policies for Agentic Time-Series Forecasting](https://arxiv.org/abs/2609.24862) | 2026-09-21 | arXiv preprint | Delayed outcomes update policies for expert trust, reasoning-path selection, and intervention strength. | Code not located |
| [CastFSR: A Fast--Slow--Reflect Agentic Reasoning Framework for Context-Aware Time Series Forecasting](https://arxiv.org/abs/2608.03031) | 2026-08-04 | arXiv preprint | Fast numerical priors, adaptive slow contextual reasoning, and reflective checks revise forecasts. | [Code](https://github.com/Xiaoyu-Tao/CastFSR) |
| [Nexus : An Agentic Framework for Context-Aware Time Series Forecasting](https://arxiv.org/abs/2605.14389) | 2026-05-14 | arXiv preprint | A numerical anchor, macro/micro contextual reasoning, and calibrated Bayesian synthesis produce forecasts. | Code not located |
| [Learning Agentic Time Series Forecasting via Trajectory Distillation and Memory-Based Reinforcement Learning](https://arxiv.org/abs/2602.13802) | 2026-02-14 | arXiv preprint | Trajectory distillation and memory-based multi-turn RL train tool routing and forecast refinement. | [Code](https://github.com/ustc-time-series/Cast-R1) |
| [MemCast: Memory-Driven Time Series Forecasting with Experience-Conditioned Reasoning](https://arxiv.org/abs/2602.03164) | 2026-02-03 | [ICML 2026](https://proceedings.mlr.press/v306/tao26a.html) | Hierarchical experience memory supports analogical forecasting, trajectory selection, and reflective checks. | [Code](https://github.com/ustc-time-series/MemCast) |
| [AlphaCast: A Human Wisdom-LLM Intelligence Co-Reasoning Framework for Time Series Forecasting](https://arxiv.org/abs/2511.08947) | 2025-11-12 | [CIKM 2026 (accepted)](https://cikm2026.diag.uniroma1.it/program/) | Investigator, Generator, and Reflector agents combine structured human knowledge, contextual evidence, and forecast revision. | [Code](https://github.com/ustc-time-series/AlphaCast) |
| [From News to Forecast: Integrating Event Analysis in LLM-Based Time Series Forecasting with Reflection](https://arxiv.org/abs/2409.17515) | 2024-09-26 | [NeurIPS 2024](https://proceedings.neurips.cc/paper_files/paper/2024/hash/6aef8bffb372096ee73d98da30119f89-Abstract-Conference.html) | News selection and error-driven reflection construct contextual training data for an LLM forecaster. | [Code](https://github.com/daydreamer-amelia/From_News_to_Forecast) |

## Forecasting and reasoning benchmarks

These resources test different capabilities. Use the scope notes below to select comparable forecasting tasks.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [Do Time-Series QA Systems Read the Time Series? Evidence Use and Reasoning Reliability](https://arxiv.org/abs/2610.05686) | 2026-10-05 | arXiv preprint | Input interventions and rationale audits examine evidence use, factual grounding, and inference reliability. | Code not located |
| [LEAF: A Living Benchmark for Event-Augmented Forecasting](https://arxiv.org/abs/2605.16358) | 2026-05-09 | arXiv preprint | Event-augmented forecasting benchmark audits retrieved context for factual and temporal validity. | Code not located |
| [TFRBench: A Reasoning Benchmark for Evaluating Forecasting Systems](https://arxiv.org/abs/2604.05364) | 2026-04-07 | [ICML 2026](https://proceedings.mlr.press/v306/ahamed26a.html) | Pairs numerical forecasts with reference reasoning about trends, cross-channel relationships, and contextual events. | [Project](https://tfrbench.github.io/) · [Data](https://huggingface.co/datasets/AtikAhamed/TFRBench) · Code not located |
| [TSRBench: A Comprehensive Multi-task Multi-modal Time Series Reasoning Benchmark for Generalist Models](https://arxiv.org/abs/2601.18744) | 2026-01-26 | [ICML 2026](https://proceedings.mlr.press/v306/yu26m.html) | Evaluates perception, reasoning, prediction, and decision-making with multimodal time-series inputs. | [Code](https://github.com/tianyi-lab/TSRBench) · [Data](https://huggingface.co/datasets/umd-zhou-lab/TSRBench) |
| [Context is Key: A Benchmark for Forecasting with Essential Textual Information](https://arxiv.org/abs/2410.18959) | 2024-10-24 | [ICML 2025](https://proceedings.mlr.press/v267/williams25a.html) | Context-essential numerical forecasting tasks test whether models use textual scenarios, constraints, and background. | [Code](https://github.com/ServiceNow/context-is-key-forecasting) · [Data](https://huggingface.co/datasets/ServiceNow/context-is-key) |

## Related understanding and analysis

Useful representations, tools, and mixed-task resources. Their aggregate QA results should be interpreted separately from numeric forecast errors.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [TS-Reasoner: Aligning Time Series Foundation Models with LLM Reasoning](https://arxiv.org/abs/2510.03519) | 2025-10-03 | [TMLR 2026](https://openreview.net/forum?id=d6TD0f2xXq) | Aligns frozen TSFM representations with an LLM for time-series understanding and reasoning. | [Code](https://github.com/Yu-Fangxu/TS-Reasoner) |
| [Time-MQA: Time Series Multi-Task Question Answering with Context Enhancement](https://arxiv.org/abs/2503.01875) | 2025-02-26 | [ACL 2025](https://aclanthology.org/2025.acl-long.1437/) | Multi-task TSQA pairs context with forecasting, imputation, anomaly detection, classification, and reasoning questions. | [Project](https://huggingface.co/Time-MQA) · [Gated data](https://huggingface.co/datasets/Time-MQA/TSQA) · Code not located |
| [ChatTS: Aligning Time Series with LLMs via Synthetic Data for Enhanced Understanding and Reasoning](https://arxiv.org/abs/2412.03104) | 2024-12-04 | [PVLDB 2025](https://www.vldb.org/pvldb/vol18/p2385-xie.pdf) | Synthetic time-series alignment and instruction data support multivariate understanding and reasoning. | [Code](https://github.com/NetManAIOps/ChatTS) |
| [TS-Reasoner: Domain-Oriented Time Series Inference Agents for Reasoning and Automated Analysis](https://arxiv.org/abs/2410.04047) | 2024-10-05 | [TMLR 2026](https://openreview.net/forum?id=yhy7Vigjcf) | Decomposes analysis queries into executable operator workflows with feedback, including constrained forecasting tasks. | [Partial code](https://github.com/wen-ye-xwz/TS-Reasoner) · [Data](https://huggingface.co/datasets/Melady/TSAIA) |

## Forecasting foundations and boundary studies

Baselines and analysis for controlled comparisons. Inclusion here does not assert explicit or faithful reasoning.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [TimeRFT: Stimulating Generalizable Time Series Forecasting for TSFMs via Reinforcement Finetuning](https://arxiv.org/abs/2605.00015) | 2026-04-18 | arXiv preprint | Forecast-quality rewards and difficulty-aware sampling reinforcement-finetune a numerical TSFM. | [Code](https://github.com/LSY-Cython/TimeRFT) |
| [Why Do Transformers Fail to Forecast Time Series In-Context?](https://arxiv.org/abs/2510.09776) | 2025-10-10 | arXiv preprint | Analyzes linear self-attention on autoregressive data and the behavior of CoT-style iterative forecasting. | [Code](https://github.com/MasterZhou1/ICL-Time-Series) |
| [Large Language Models Are Zero-Shot Time Series Forecasters](https://arxiv.org/abs/2310.07820) | 2023-10-11 | [NeurIPS 2023](https://proceedings.neurips.cc/paper_files/paper/2023/hash/3eb7ca52e8207697361b2c0fb3926511-Abstract-Conference.html) | Serializes numerical histories for zero-shot next-token forecasting; useful direct-forecast baseline. | [Code](https://github.com/ngruver/llmtime) |
| [Time-LLM: Time Series Forecasting by Reprogramming Large Language Models](https://arxiv.org/abs/2310.01728) | 2023-10-03 | [ICLR 2024](https://proceedings.iclr.cc/paper_files/paper/2024/hash/680b2a8135b9c71278a09cafb605869e-Abstract-Conference.html) | Reprograms numerical patches into a frozen LLM and projects its representations into forecasts. | [Code](https://github.com/KimMeen/Time-LLM) |

## Surveys and broader resources

Background reading and discovery resources.

| Paper | First submitted | Venue/status | Reasoning role / scope | Resources |
| --- | --- | --- | --- | --- |
| [A Survey of Reasoning and Agentic Systems in Time Series with Large Language Models](https://arxiv.org/abs/2509.11575) | 2025-09-15 | [TMLR 2026 (author-reported)](https://arxiv.org/abs/2509.11575) | Organizes reasoning topologies, tools, verification, retrieval, and agentic time-series systems. | [Project](https://github.com/blacksnail789521/Time-Series-Reasoning-Survey) |

## Reading path

1. [TimeReasoner](https://arxiv.org/abs/2505.24511): inspect how prompting and deliberation change numerical forecasting.
2. [Time-R1](https://arxiv.org/abs/2506.10630): study reasoning supervision, forecasting rewards, and rationale interventions.
3. [STRIDE](https://arxiv.org/abs/2605.08625): compare reasoning-conditioned numerical decoding with direct numeric generation.
4. [MemCast](https://arxiv.org/abs/2602.03164) and [CastFSR](https://arxiv.org/abs/2608.03031): compare experience memory with contextual retrieval and reflection.
5. [CiK](https://proceedings.mlr.press/v267/williams25a.html), [TFRBench](https://proceedings.mlr.press/v306/ahamed26a.html), and [TSRBench](https://proceedings.mlr.press/v306/yu26m.html): distinguish context use, forecast reasoning, and broader reasoning ability.

## Evaluation and reproducibility

Forecast error, factual correctness, and reasoning faithfulness are separate axes. A convincing rationale or an LLM-judge score alone does not establish that the rationale caused the forecast. [Time-R1](https://arxiv.org/html/2506.10630v4#S4.SS8) includes rationale interventions; [COMMON-TSQA](https://arxiv.org/abs/2610.05686) studies evidence-use interventions with task-specific interpretation limits.

- Report numerical error, probabilistic calibration where applicable, output validity, and the evaluation denominator. Keep QA accuracy, trend classification, event probabilities, and numerical forecasts separate.
- Match input information and inference budget. Compare the same expert models, context, retrieval access, samples, tokens, and tool calls before attributing gains to reasoning.
- Enforce forecast-origin availability for context, memory, retrieval, calibration, and demonstrations. Distinguish future-known calendars from events only documented retrospectively.
- Separate training-time oracle annotations from inference-time access. [STRIDE](https://arxiv.org/abs/2605.08625) uses training pseudo-futures; [TFRBench](https://arxiv.org/html/2604.05364v1#S4) constructs references with oracle future events and outcome-conditioned validation, making reference-alignment scores an imperfect ex-ante faithfulness test.
- State the adaptation protocol. [MemCast](https://arxiv.org/abs/2602.03164), [SEER](https://arxiv.org/abs/2610.04109), and [TimEvolve](https://arxiv.org/abs/2609.24862) use observable outcomes for different updates; compare them under the same feedback timing.
- Record end-to-end latency, API/token cost, retrieval and tool overhead, training-data construction cost, and uncertainty across seeds/origins. Inspect release scope before claiming reproducibility.

Two different papers use the name ReasonCast: [joint forecast/explanation generation](https://arxiv.org/abs/2608.01875) and [selective demand intervention](https://arxiv.org/abs/2608.15291). Two different TS-Reasoner papers concern [representation alignment](https://arxiv.org/abs/2510.03519) and [operator-based analysis agents](https://arxiv.org/abs/2410.04047). AlphaCast was previously named CastMind; Cast-R1 and Time-R1 also have earlier titles. Deduplicate by identifiers, not acronyms.

See the [Chinese synthesis](docs/research-survey.zh-CN.md) for interpretation and research opportunities, and the [evidence notes](docs/search-and-evidence.md) for inclusion rules and verification limits.
