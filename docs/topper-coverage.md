# Topper-copy coverage & resume state

This repo indexes **publicly posted** UPSC CSE Mains topper answer copies as *citation rows only*
(topper, rank, medium, source link). No copy, scan or transcript is ever committed - see the
safe-content gate in the exam-repo protocol.

## What `data/topper-coverage.json` is

A deterministic scan of the public topper answer-booklet archive manifest. For every Mains year it
records: rows found, distinct toppers, subjects, citation files in the index, whether a gap record
exists, and a status (`AVAILABLE` when the source manifest has real rows, `UNAVAILABLE` when it has
none).

The file exists so a **gap is tracked instead of silently absent**: the index used to stop at the last
cycle that had published copies, which made a missing year indistinguishable from an unscanned one.

## Rules the scan follows

1. A year with **0** rows in the source manifest is `UNAVAILABLE` and gets only a gap record -
   never a fabricated citation row. Every citation row carries a real published source URL or it
   does not exist.
2. The source manifest's sha256 is the rebuild cursor: same sha -> same bytes, no churn, no commit.
3. Gap years carry a **resume state**, so the next run knows exactly which years to re-check.
4. The scan owns the coverage record and the rollup marker only. When a year gains real rows the
   marker self-heals away and the leftover gap file is reported as `stale_gap_files`, so the
   citation table for that year replaces it instead of contradicting it.
5. Bulk extraction of the raw copies stays off this machine (Spark lanes per the protocol); this repo
   only ever receives metadata.

## Re-scan

```sh
# read-only: what does the source archive hold per year right now?
jq -r '[.result[].year] | group_by(.) | map({year: .[0], rows: length}) | .[]' <source manifest>

# read-only: does every sha in the repo manifest still match the file on disk?
jq -r '.files | to_entries[] | "\(.value.sha256)  \(.key)"' manifest.json | shasum -a 256 -c - | grep -v ': OK'
```

When the source manifest sha changes, rebuild the affected year files, then let the repo protocol
regenerate `manifest.json` and push through the guard (never a bare `git push`).

_Last checked 2026-10-02._
