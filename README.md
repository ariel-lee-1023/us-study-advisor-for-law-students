# US Study Advisor for Law Students

An agent skill for law students and law graduates going to the United States — LL.M./J.D.
programme selection, application essays, internships, funding, visas, bar eligibility, and
whatever else comes up before formal employment — written so that the agent reasons like an
intelligence analyst rather than like an admissions consultant.

The difference is not tone. It is that the advisor starts from *what would have to be
true* for an answer to hold, generates the live alternatives before it favours one,
reports the alternatives it rejected and why, keeps **data**, **inference**, and
**hunch** visibly separate in everything it hands back, and refuses to state a
volatile fact — a deadline, a tuition figure, a bar rule — as settled from memory.

---

## Why this exists

Most application advice fails in one of three ways. It arrives at an answer first and
then assembles support for it. It blurs a published fact, a chain of reasoning, and a
gut read into one confident-sounding sentence. Or it states last decade's rule as this
year's rule.

This skill is built to make those three failures structurally awkward. The core voice
carries the habits; seven trigger-loaded modules carry the procedures and the domain
structure; and a provenance file records where every behaviour came from and how fast
each piece of domain knowledge decays.

---

## Repository layout

```
us-study-advisor-for-law-students/
├── README.md
├── SKILL.md                      # the core advising voice — loaded always
├── references/                   # trigger-loaded modules — host-agent-facing
│   ├── calibration.md            # probability, base rates, updating
│   ├── toolbox.md                # structured analytic techniques
│   ├── llm-pathway.md            # LL.M./J.D., bar eligibility, visas
│   ├── legal-writing.md          # U.S. legal-writing convention
│   ├── personal-statements.md    # topic selection, structure, addenda, recommendation letters
│   └── institutions.md           # how U.S. universities are funded and governed
├── fidelity-ledger/              # human-maintainer-facing — never trigger-loaded
│   └── provenance.md             # sources, fidelity notes, staleness ledger, extension protocol
├── CHANGELOG.md
├── LICENSE
├── NOTICE.md                     # originality and source-attribution statement
└── .gitignore
```

`references/` and `fidelity-ledger/` sit side by side, on purpose, and are not
interchangeable. `references/` is written for a host agent to load automatically
when a trigger fires — every file in it is a module that can end up quoted or
paraphrased in the advising voice. `fidelity-ledger/` is written for the human
maintaining this repository — sourcing, fidelity notes, the staleness ledger, and
the extension protocol. No host ever loads it as part of normal operation, and
nothing in it is meant to reach the advising voice. If a file would answer "where
did this come from, and how do I extend it" rather than "what should the advisor
know or do," it belongs in `fidelity-ledger/`, not `references/`.

---

## Architecture: core voice, trigger-loaded modules

`SKILL.md` is the reasoning temperament and stands alone. The modules are **not**
preloaded — each one loads when its trigger fires, and each carries procedure and
structure only. A module that starts speaking in the first person has broken the
architecture, and `fidelity-ledger/provenance.md` says so explicitly.

| Trigger | Module |
|---|---|
| Stating or revising a probability or confidence | `references/calibration.md` |
| A decision consequential enough to earn extra structure — irreversible, high-cost, contested, or where the leading answer arrived suspiciously early | `references/toolbox.md` |
| LL.M./J.D. pathway mechanics, bar eligibility, visa logic, programme selection | `references/llm-pathway.md` |
| U.S. legal-writing convention, or the rhetorical transition for writers trained in another legal culture | `references/legal-writing.md` |
| Drafting or structuring a personal statement, optional essay, addendum, or wait-list letter; selecting or briefing recommenders | `references/personal-statements.md` |
| How U.S. universities and law schools are structured, funded, or governed | `references/institutions.md` |

For any domain not covered, the advisor reasons from the core and says plainly that
the question is outside its material. Auditing, editing, or extending the skill is not
a trigger a host ever fires — that work is done by a human maintainer reading
`fidelity-ledger/provenance.md` directly.

---

## Installation

**As a Claude skill.** Copy the whole directory into your skills folder, preserving
the `references/` subdirectory. You can omit `fidelity-ledger/` from the copy — it is
maintainer documentation, not skill content, and no host loads it:

```bash
git clone https://github.com/ariel-lee-1023/us-study-advisor-for-law-students.git
cp -r us-study-advisor-for-law-students ~/.claude/skills/us-study-advisor-for-law-students
```

Remove the repository-level files (`README.md`, `LICENSE`, `CHANGELOG.md`,
`.gitignore`) from the copied folder if you want the skill directory to contain only
skill content. They are harmless if left in place.

**As a system prompt or project instruction.** Paste the body of `SKILL.md` (below the
YAML front matter) as the system prompt, and attach the reference modules as project
knowledge. Behaviour degrades gracefully — the core is written to work without any
module loaded.

**With any other agent framework.** `SKILL.md` carries YAML front matter with `name`
and `description`; the rest is plain Markdown. Nothing here depends on a particular
runtime.

---

## What it does and does not do

**It does:**

- Lay out the alternatives it considered and name the ones it rejected, with reasons.
- Tag every substantive claim as data, inference, or hunch — and split claims that mix
  them.
- Triage how much analytic machinery a question deserves, and say which category it
  thinks you are in.
- Attach a trip-wire to every recommendation: the observable that would mean the
  recommendation needs revisiting, and in which direction.
- Read your draft as the tired, self-interested reader on the fortieth file would.
- Refuse a fabricated percentage, and give a mechanism and a condition instead.

**It does not:**

- Give legal, immigration, financial, or other advice that calls for a licensed
  professional. It explains how things generally work and marks where you need real
  counsel.
- State a current rule. Bar eligibility, visa procedure, work-authorization caps,
  deadlines, tuition, and test requirements all change; the skill flags them and names
  the office that owns the real answer.
- Insert experiences you did not provide, or let a draft imply something untrue.
- Decide what you disclose about yourself. That is left entirely to you.

---

## The vintage caution

The modules are distilled from books with fixed publication dates. What they carry
reliably is **structure** — the sequence of decisions, the shape of a system, the
mechanism behind an institution's behaviour. What they do not carry reliably is
**current fact**.

The full decay-ordered ledger is in `fidelity-ledger/provenance.md` §4. The headline:

| Content | Decay | Handling |
|---|---|---|
| Bar eligibility rules for foreign-educated lawyers | Fastest | Never state from the module; route to the specific state bar every time |
| Visa procedures, work-authorization durations and caps | Very fast | Route to the campus international office and current government guidance |
| Deadlines, tuition, fees, aid programmes, test requirements | Yearly | Flag as volatile; verify against the school |
| Named schools' statement-weighting, named admissions officers | Yearly to several years | Verify against current published guidance |
| Institutional mechanism, rhetorical framework, personal-statement genre conventions, cognitive biases | Very slow to stable | Usable directly |

**Combining these modules never produces a current rule.**

---

## Source corpus

Three sources supply the reasoning temperament; the remainder supply domain structure. The
division is deliberate — the voice is not a subject-matter expert wearing an analyst's
manner, it is an analyst reasoning over domain structure it treats as provisional.

**Reasoning temperament**

- Richards J. Heuer Jr., *Psychology of Intelligence Analysis* (1999)
- Richards J. Heuer Jr. & Randolph H. Pherson, *Structured Analytic Techniques for
  Intelligence Analysis* (2nd ed., 2011)
- Philip E. Tetlock & Dan Gardner, *Superforecasting: The Art and Science of
  Prediction* (2015)

**Domain structure**

- George E. Edwards, *LL.M. Roadmap: An International Student's Guide to U.S. Law
  School Programs* (Aspen, 2011)
- Jill J. Ramsfield, *Culture to Culture: A Guide to U.S. Legal Writing* (Carolina
  Academic Press, 2005)
- John R. Thelin, *American Higher Education: Issues and Institutions* (Routledge,
  Core Concepts in Higher Education)
- Paul Bodine, *Great Personal Statements for Law School* (McGraw-Hill, 2006)
- The Princeton Review, *Law School Essays That Made a Difference* (6th ed., 2014)
- Mark Alan Stewart, *Perfect Personal Statements: Law, Business, Medicine, Graduate
  School* (Peterson's, 2nd ed., 2002)
- Warren Zhang & Hemant Mohapatra (eds.), *Successful Personal Statements to Get You
  into a Top University* — UK/international undergraduate-admissions compilation, used
  for structural patterns only; see `references/personal-statements.md` §6 for what
  transfers and what does not
- [Top Law Schools, "Guide to Personal
  Statements"](https://www.top-law-schools.com/personal-statement-examples.html) — web
  source, treated as current-as-fetched rather than a fixed-date book

Nothing is quoted at length from any source; the modules are synthesised. Author
terminology is preserved exactly where the term *is* the framework — ACH, Key
Assumptions Check, ELP, RCM, revenue theory, disease theory, cost/price/net price,
perpetual beta, Fermi-izing, TELL model, uniqueness filter — because paraphrasing a
named framework destroys the ability to find it in the original. A behaviour-by-behaviour
source map is in `fidelity-ledger/provenance.md` §2.

---

## Extending it

The extension protocol is in `fidelity-ledger/provenance.md` §6. In short: distil structure
and decision rules rather than summary, preserve the author's exact framework names,
keep the file trigger-loaded and headed with **Sources / Trigger / What this file is**,
add a vintage warning and a staleness row, end with decision rules, and register the
source and the new behaviours in `fidelity-ledger/provenance.md` §§1–2.

The one hard constraint: **the voice lives in the core and must not be duplicated into
modules.**

Issues and pull requests are welcome. A pull request that adds a module should include
its `fidelity-ledger/provenance.md` entries; one that changes core behaviour should say which grounding
in §2 it is revising, or make the case that the behaviour belongs in the list of
commitments held for independent ethical reasons rather than analytic ones.

---

MIT © 2026 Ariel Lee. [See LICENSE](LICENSE).

This license covers the original text in this repository. It does not extend to any
referenced source books, which remain the property of their respective copyright
holders.
