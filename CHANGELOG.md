# Changelog

All notable changes to this project are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Because this is a skill rather than a library, the version numbers are read as:

- **MAJOR** — the core voice changes, or the module architecture changes in a way
  that would alter the advice a host agent gives.
- **MINOR** — a new reference module is added, or an existing module gains new
  structure or decision rules.
- **PATCH** — wording, formatting, typo, or vintage-note corrections that do not
  change behaviour.

---

## [Unreleased]

### Fixed

- The `git clone` command in the README's installation section used a `USERNAME`
  placeholder, so copying it verbatim failed. Now points at the actual repository, as do
  the changelog comparison links.
- Added the `.gitignore` that the layout block and the 1.0.0 scaffolding note both
  already listed.
- The layout block omitted `README.md` and `NOTICE.md`.

## [1.0.0] — 2026-07-24

First public release.

### Added

- `SKILL.md` — the core advising voice: alternative generation before plausibility
  filtering, disconfirmation over confirmation, triage of how much analytic
  machinery a question earns, the data / inference / hunch separation, volatile-fact
  flagging, source-independence and deception-aware review, ranking by fewest
  disqualifiers, weight-before-score discipline, gatekeeper reading of drafts,
  and trip-wires attached to every recommendation.
- `references/calibration.md` — verbal-probability bands, granularity limits,
  Fermi decomposition, outside-view-first ordering, update discipline, the
  wrong-side-of-maybe rule, and Heuer's probability biases.
- `references/toolbox.md` — technique selection guide, the full eight-step ACH
  procedure, Key Assumptions Check, Quality of Information Check (with the
  deception-aware extension), Indicators, Decision Matrix,
  Pros-Cons-Faults-and-Fixes, High Impact/Low Probability, What If?, and the
  challenge techniques.
- `references/llm-pathway.md` — LL.M./J.D. pathway sequence, program taxonomy,
  selection criteria, admission components, visa category logic, work
  authorization structure, funding, and bar eligibility.
- `references/legal-writing.md` — the four rhetorical considerations, the four
  families of analytical pattern, the six design elements, English for Legal
  Purposes, and the cross-cultural transition points.
- `references/institutions.md` — cost / price / net price, the revenue and disease
  theories of rising cost, RCM budgeting, governance and organized anarchy,
  stratification, and internationalisation as a revenue strategy.
- `references/provenance.md` — the corpus, the behaviour-to-source map, fidelity
  notes and deliberate departures, the staleness ledger, known gaps, and the
  extension protocol.
- `README.md`, `LICENSE`, `.gitignore`, and this changelog.

[Unreleased]: https://github.com/ariel-lee-1023/study-abroad-advisor/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/ariel-lee-1023/study-abroad-advisor/releases/tag/v1.0.0
