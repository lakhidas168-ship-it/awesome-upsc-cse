# Awesome UPSC CSE 📜

> A curated list of **official sources and free resources** for the UPSC Civil
> Services Examination (Prelims, Mains, Interview).
>
> Every link below points to an official source and was opened and checked on
> 2026-09-28 (see [docs/LINK_CHECK.md](docs/LINK_CHECK.md)).
> Anything that is advice rather than fact is marked **(suggestion)**.

- [Official UPSC links](#-official-upsc-links)
- [Free official sources](#-free-official-sources)
- [GS1–GS4 + Essay syllabus map](#️-gs1gs4--essay-syllabus-map)
- [Answer-writing](#-answer-writing)
- [Open tools](#-open-tools)
- [Related](#-related)

Found a mistake? Open an issue with the official link.

---

## 📋 Official UPSC links

Start from the Commission's own site. The yearly notification carries the
syllabus as an annexure; exact PDF URLs change every year, so follow the
site's examination section from the home page.

| What | Official link |
|------|---------------|
| **UPSC home** (notifications, syllabus annexures) | [www.upsc.gov.in](https://www.upsc.gov.in/) |
| **Previous question papers** (CSE Prelims + Mains) | [Previous Question Papers](https://www.upsc.gov.in/examinations/previous-question-papers) → "Civil Services Examination" |
| **Per-exam page (hub)** | [upsc-cse.md](https://github.com/lakhidas168-ship-it/awesome-indian-exams/blob/main/awesome-indian-exams/exams/upsc/upsc-cse.md) |

Download papers only from `upsc.gov.in`. See also
[resources/upsc-papers.md](resources/upsc-papers.md).

---

## 🎓 Free official sources

| Source | What it gives | Link |
|--------|---------------|------|
| **NCERT** | School textbooks (base for Prelims + GS) — free PDFs | [ncert.nic.in](https://ncert.nic.in/) |
| **PIB** | Official government releases (current affairs, schemes) | [pib.gov.in](https://www.pib.gov.in/) |
| **PRS Legislative Research** | Bills, session analysis, policy briefs (GS-II) | [prsindia.org](https://prsindia.org/) |
| **Sansad (Parliament)** | Parliament debates and proceedings recordings | [sansad.in](https://sansad.in/) |
| **NPTEL** | Free-to-audit courses (S&T, environment, ethics-adjacent) | [nptel.ac.in](https://nptel.ac.in) |
| **SWAYAM** | Free government MOOCs across subjects | [swayam.gov.in](https://swayam.gov.in/) |

Details: [resources/free-sources.md](resources/free-sources.md).

---

## 🗺️ GS1–GS4 + Essay syllabus map

Paper names follow the official CSE notification. For the full text of each
paper's syllabus, read the notification annexure on
[upsc.gov.in](https://www.upsc.gov.in/) — the map below is only an index.

| Mains paper | Covers (index only) |
|-------------|---------------------|
| **Essay** | Two essays on topics of national/international relevance |
| **GS-I** | Indian heritage and culture, history, geography of the world and society |
| **GS-II** | Governance, constitution, polity, social justice, international relations |
| **GS-III** | Technology, economic development, biodiversity, environment, security, disaster management |
| **GS-IV** | Ethics, integrity, aptitude |
| **Optional I + II** | One optional subject, two papers |
| **Indian Language + English** | Qualifying papers |
| **Prelims** | General Studies-I (merit) + CSAT (qualifying) |

Details: [resources/syllabus-map.md](resources/syllabus-map.md).

---

## ✍️ Answer-writing

No answer-writing framework from Rajon's team is published here: the
consolidation inventory
(`~/.air10/awesome_consolidation/INVENTORY.md`, 2026-09-28) lists **no
standalone `rajon_original` answer-writing framework**, and the Telegram
answer-evaluator bot's core is a paid product built on a private topper-copy
database — so it is deliberately excluded (no evaluator code, no topper
copies, no coaching notes in this repo).

**(Suggestion — not a rule.)** Practice against the official previous papers
above; compare structure (intro, dimensions, examples, conclusion) across
years. If a team-written framework is cleared for publication later, it will
appear in this section with its origin noted.

---

## 🔧 Open tools

No tool code is vendored in this repo yet. Generic, publishable pieces from
Rajon's work live with the sibling repo / hub (per the inventory's target
mapping) and are linked, not copied:

- **Evidence-gated retrieval** (`sovereign-study-commons-india`: SQLite FTS5 +
  concept graph + evidence gate) — published as the reference implementation
  in `awesome-electrical-exams` (inventory: `publish code`, target =
  electrical). Relevant to CSE GS/S&T study as a pattern; see that repo when
  it is public.
- **Claim verification** (`truthgate`: deterministic claim auditor) —
  inventory target includes this repo as a CI gate; wired in when tool code
  lands here.

Explicitly **not** included: the paid evaluator bot's core (`bot.py`,
`evaluator.py`, topper database), topper copies, coaching notes, lecture
transcripts. Links only, never copies.

---

## 🔗 Related

- [awesome-indian-exams](https://github.com/lakhidas168-ship-it/awesome-indian-exams) —
  the hub repo with per-exam pages for all Indian competitive exams (the CSE
  page is linked in the table above).
- `awesome-electrical-exams` (sibling local repo, not yet pushed) — shares the
  ESE GS overlap and the open study tools referenced above.

---

## 📜 Licenses

| Content type | License |
|--------------|---------|
| Code (`scripts/`) | [MIT](LICENSE.md) |
| Text (README, docs, resources) | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). In short: only real, sourced content —
link to official sources, never copy coaching material, never invent numbers.

---

*Maintained by Rajon Das.*

---

<!-- topper-updater:upsc:begin -->
## 🧾 Topper-copy citations & strategy

- [toppers/](toppers/README.md) — citation index of public UPSC Mains topper answer copies (name · rank · medium · source link; never the copy).
- [strategy/](strategy/README.md) — our own distilled analysis: answer-writing (from grading rubrics), verified-question topic trends, optional coverage.
<!-- topper-updater:upsc:end -->
