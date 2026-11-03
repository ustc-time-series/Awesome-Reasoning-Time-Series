# Contributing

Contributions should make the connection to numerical time-series forecasting clear and traceable.

## Add or correct a paper

1. Check the arXiv ID or DOI for an existing record. Acronyms and renamed titles are not reliable identifiers.
2. Provide a primary paper link and exact title, complete authors, first arXiv submission date, and the version inspected. Use official venue evidence where available; distinguish accepted work from published work and author-reported status.
3. Describe what reasoning changes: numerical output, a decoder or ensemble, tool/workflow decisions, or evaluation. Mark mixed-task, QA-only, latent-computation, and baseline scope explicitly.
4. Link author-associated code, projects, and data. State partial releases, gating, and missing implementation evidence accurately. A project page is not automatically an executable release.
5. Add a short evidence boundary, such as forecast-origin context access, delayed-outcome adaptation, synthetic-only evaluation, task-specific metrics, or release limits.
6. Update [README.md](README.md), [data/papers.json](data/papers.json), and [references.bib](references.bib) together. Update [search/evidence notes](docs/search-and-evidence.md) when changing inclusion rules or important interpretations.

Use the existing JSON record structure and null values with explanations for unknown fields. Preserve the relationship between first-submission year, inspected version, and associated venue year. For the current bibliography, cite the inspected arXiv manifestation rather than inventing publisher fields.

## Evidence standards

Prefer papers, official proceedings, and author-maintained resources. Use third-party indexes to discover candidates, then verify their identities at an owning source. Retain source links and inspection dates for material claims.

Keep forecast errors separate from QA accuracy, trend classification, and event-probability metrics. If reporting a number, retain the dataset, horizon, denominator, metric, and comparison setting. Include output validity and the handling of failed predictions where relevant.

Do not infer faithful reasoning from fluent explanations or a judge score alone. Describe information and compute access, retrieval timestamps, training-time oracle labels, forecast-origin context, and feedback timing when they affect interpretation.

Before submitting, validate JSON syntax, check duplicate identifiers and bibliography keys, verify relative links/anchors, inspect external links and release scope, and review the rendered Markdown tables. Do not claim experimental reproduction unless it was actually performed.
