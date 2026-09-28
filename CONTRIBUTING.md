# Contributing

Students, teachers and toppers are all welcome. The one rule: **anything a student might act on must be
traceable to an official source.**

## Adding or fixing UPSC facts

1. Find the official document (notification, syllabus annexure, question paper)
   on an official domain (`upsc.gov.in`, `ncert.nic.in`, `pib.gov.in`,
   `prsindia.org`, `sansad.in`, `nptel.ac.in`, `swayam.gov.in`).
2. Add the link to the README or the matching file in `resources/`.
3. Open every link you add and confirm it loads; record the check in `docs/LINK_CHECK.md`.
4. Never copy coaching material, lecture transcripts, topper copies, or proprietary content — links only.
   Never invent numbers, dates, cut-offs, or paper URLs. Advice must be labelled
   **(suggestion)**, never stated as fact.

## Adding tool code

1. Work in a branch, add tests under `tools/<name>/tests/` when a tool lands.
2. Code must work with zero bundled data: all data paths come from
   environment variables, and tests must pass in a temp dir.
3. Gates before any commit: `gitleaks detect --no-git -s . --redact` clean,
   no personal paths or emails, `bash scripts/check.sh` green.

## What never lands here

- The paid evaluator bot's core, topper databases, topper copies.
- Coaching PDFs, lecture transcripts, NotebookLM session exports.
- Credentials, tokens, API keys, `.env` files.
