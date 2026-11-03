# Search scope and evidence notes

Snapshot date: 2026-11-03 (Asia/Shanghai). The catalog contains 33 selected records and is a curated research snapshot. The search does not establish exhaustive coverage, a PRISMA flow, or a common leaderboard.

## Search scope

The question was how reasoning participates in numerical time-series forecasting: direct deliberation, reasoning-conditioned numerical models, and agentic tools, memory, retrieval, verification, and reflection. Related QA, representation alignment, contextual benchmarks, and ordinary forecasting baselines are retained with separate scope tags.

Searches combined exact paper names, mechanism queries, recent-work queries, and venue-specific checks. Discovery sources included web search and a broader [reasoning/agentic time-series survey](https://arxiv.org/abs/2509.11575). Inclusion facts were checked at arXiv, official proceedings or publisher records, and author-associated project/repository pages.

Representative queries actually used:

| Purpose | Queries |
| --- | --- |
| Direct forecasting reasoning | `"time series forecasting" "reasoning" 2026`; `"reasoning-aware" "forecasting"`; `"time series forecasting" "chain-of-thought" arxiv reinforcement`; `"time series forecasting" reasoning distillation` |
| Recent additions | `"forecasting" "reasoning" "2610" site:arxiv.org/abs`; `"forecasting" "reasoning" "2609" site:arxiv.org/abs`; `"time series" "reasoning" "November" "2026" site:arxiv.org/abs` |
| Agentic forecasting | `"time series forecasting" "agents" "news" reasoning 2024 2025`; `"time series forecasting" "agent" "reflection" arxiv`; `"time series forecasting" "multi-agent" reasoning arxiv`; `"LEAF" "forecasting" LLM events` |
| Identity and resources | Exact-name searches for Time-R1, STRIDE, ReasonCast, TS-Reasoner, MemCast, CastFSR, KairosAgent, SEER, TimeRFT, and Time-MQA; title/arXiv-ID plus GitHub searches |
| Venue checks | Exact-title searches restricted to PMLR, ACL Anthology, NeurIPS, ICLR proceedings, and OpenReview; DOI metadata from Crossref for TimeReasoner and Time-R1; CIKM 2026 program for AlphaCast |

Recent-work queries were discovery probes, not a claim that every paper from those months was retrieved. No citation-count ranking or CCF filter was applied. References and author repositories were followed to fill gaps around benchmark tasks and implementation availability.

## Inclusion and exclusion

- Core forecasting methods evaluate a numerical future sequence and describe reasoning, latent deliberation, verification, decomposition, or agent decisions that affect the forecast. Mixed-task methods identify a numerical forecasting component.
- Benchmarks either evaluate forecasting reasoning directly or provide a relevant contextual/numerical subset. Their aggregate QA scores are not substituted for forecast error.
- Adjacent resources concern time-series understanding, alignment, or automated analysis, with their forecasting evidence identified explicitly.
- Foundations and boundary studies supply direct-forecast, modality-alignment, RL, or theoretical comparisons. Their presence does not label them reasoning methods.
- Generic news-event prediction, temporal commonsense reasoning, video grounding, and acronym matches without a numerical TSF connection are excluded. For example, arXiv:2505.13508 is a different Time-R1 from the forecasting paper arXiv:2506.10630.

Selection favors a clear mechanism and traceable primary evidence rather than a fixed paper count or reported performance. Primary sections overlap conceptually and are curator assignments, not an author-endorsed taxonomy.

## Identity and version checks

All 33 arXiv abstract pages were fetched to check exact current titles, complete authors, submission dates, PDF links, and version histories. The checked versions precede the snapshot cutoff. Records were deduplicated by arXiv identifiers, with manual checks of acronym/title collisions.

| Potential confusion | Resolution |
| --- | --- |
| Time-R1 titles | One record for [2506.10630](https://arxiv.org/abs/2506.10630); current v4 uses “via Reasoning” and “Reinforcement Fine-Tuned LLMs.” |
| STRIDE title | [2605.08625](https://arxiv.org/abs/2605.08625) now includes the STRIDE prefix. |
| CastMind / AlphaCast | One record for [2511.08947](https://arxiv.org/abs/2511.08947); current v6 is AlphaCast. |
| Cast-R1 titles | One record for [2602.13802](https://arxiv.org/abs/2602.13802); current v2 emphasizes trajectory distillation and memory-based RL. |
| Nexus versions | [2605.14389](https://arxiv.org/abs/2605.14389) v2 includes a numerical anchor and Bayesian synthesis. The earlier no-anchor description was not carried forward. |
| Two ReasonCast papers | [2608.01875](https://arxiv.org/abs/2608.01875) is joint forecast/explanation generation; [2608.15291](https://arxiv.org/abs/2608.15291) is selective semantic intervention for demand forecasting. |
| Two TS-Reasoner papers | [2510.03519](https://arxiv.org/abs/2510.03519) is representation alignment; [2410.04047](https://arxiv.org/abs/2410.04047) is operator-based analysis. Their OpenReview identities also differ. |
| Dates inferred from identifiers | The source-reported submission dates for Time-MQA and TimeRFT differ from their identifier month. Dates come from page metadata, not the arXiv ID prefix. |
| TimeReasoner venue typo | The code README's WSDM year differs from the paper and [publisher registration](https://api.crossref.org/works/10.1145/3773966.3777931); WSDM 2026 is used. |

Time-R1's registered publisher date is 2026-11-06, after this snapshot. It is labeled CIKM 2026 accepted, with registered metadata, rather than described as a completed conference publication. AlphaCast's CIKM association was checked against the official program; its program-linked DOI did not resolve during inspection and is omitted from the catalog. Survey TMLR acceptance remains explicitly author-reported.

## Evidence that changes interpretation

| Resource | Scope or limitation |
| --- | --- |
| [STRIDE](https://arxiv.org/html/2605.08625v2) | Teacher annotations use training pseudo-futures; the inference student uses historical context. These are different information-access regimes. |
| [TFRBench](https://arxiv.org/html/2604.05364v1#S4) | Reference construction uses oracle future-event knowledge and post-hoc outcome filtering, while evaluated models receive history. Reference agreement does not alone measure ex-ante faithfulness. |
| [TimeOmni-1](https://github.com/AntonGuan/TimeOmni-1) | Forecasting MAE and task accuracy have different meanings; valid-response rates and valid-only metric denominators matter. |
| [MemCast](https://arxiv.org/html/2602.03164v2#S3.SS6) | Memory content is fixed during testing, but confidence updates use delayed observable outcomes. |
| [TimEvolve](https://arxiv.org/html/2609.24862v1) | Updates require the full prior forecast horizon to have elapsed; this is an online delayed-feedback protocol. |
| [LEAF](https://arxiv.org/html/2605.16358v2) | Temporal verification reduces but does not eliminate problematic context. Outcome-conditioned context filtering is a diagnostic construction. |
| [COMMON-TSQA](https://arxiv.org/html/2610.05686v1) | Altered inputs often retain original targets; the resulting tests diagnose evidence use rather than automatically establishing counterfactual correctness. |
| [TSRBench](https://proceedings.mlr.press/v306/yu26m.html) | Reasoning and prediction are separately evaluated. The paper and repository give different domain counts; no domain count is used here. |
| [TimeRFT](https://arxiv.org/html/2605.00015v2) | Forecasting RL without explicit CoT is treated as a baseline. Placeholder ACM front matter is not venue evidence. |
| [In-context forecasting theory](https://arxiv.org/abs/2510.09776) | Conclusions depend on linear self-attention and autoregressive-data assumptions; they are not universal limitations of all reasoning models. |

## Release and verification limits

Author-associated code links were inspected for identity and stated release scope. Their presence is not proof that the experiments reproduce. No model was installed or run, and no performance results were independently reproduced. PDF entry points were checked from metadata; PDF bytes were not downloaded or validated.

- SEER exposed project materials without an observed executable forecasting pipeline. KairosAgent exposed a project page without a verified implementation download.
- The operator-based TS-Reasoner release was a small annotation/module package. TimeOmni-1 exposed inference/evaluation resources; the joint-generation ReasonCast release excluded extended analyses.
- Time-MQA's TSQA dataset was gated, and its card still described full code/evaluation data as forthcoming. No gate was accepted on the user's behalf.
- No executable author-linked implementation was verified for STRIDE, COUNTS, latent CoT, Nexus, TimEvolve, LEAF, or COMMON-TSQA in the inspected sources. This is a bounded search result, not a permanent availability claim.
- Citation counts were not collected. Missing values remain null rather than zero. Relative performance claims were not pooled across incomparable domains, horizons, modalities, or metrics.

## Catalog and bibliography conventions

[papers.json](../data/papers.json) is an array. Each record retains `title`, complete `authors`, `year`, `publication_date`, identifiers, `scope`, primary `section`, mechanism `summary`, `evidence_boundary`, resource links, version information, and field-level sources. `year` and `publication_date` refer to the first arXiv submission. `publication_type=preprint` describes the cataloged arXiv manifestation; `venue` and `venue_status` separately record an associated conference/journal.

`venue_status` is `published`, `accepted`, `author_reported`, or `unverified`. `code_status` distinguishes `linked_not_executed`, `partial_release_not_executed`, `materials_only`, and `not_located`. Field-level source timestamps record inspection; `fetched_at` is the snapshot date. Curator summaries and taxonomy assignments are interpretations of the cited papers.

`full_text_status=open_pdf` records an observed PDF entry point. `download_status=not_requested`, `pdf_verification_status=unverified`, and `paper_identity_status=unverified` describe the unperformed PDF-file checks; they do not mean the paper metadata was left unchecked.

[references.bib](../references.bib) cites the exact checked arXiv versions using source-backed authors and titles. It deliberately exports the arXiv manifestations; use the linked publisher records when a venue-specific citation is required. Optional DOI fields in the catalog are included only where publisher identities were verified. Update all three public representations together when adding or correcting a record.
