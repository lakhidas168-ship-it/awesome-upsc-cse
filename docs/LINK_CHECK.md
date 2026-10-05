# Link check — 2026-09-28

Method: `bash scripts/check.sh` — `curl -s -o /dev/null -w '%{http_code}' -L`
for every `https://` URL in `README.md` + `resources/`, plus personal-path
and email scans. All URLs were opened this run.

```
200 https://creativecommons.org/licenses/by/4.0/
200 https://github.com/lakhidas168-ship-it/awesome-indian-exams
200 https://github.com/lakhidas168-ship-it/awesome-indian-exams/blob/main/awesome-indian-exams/exams/upsc/upsc-cse.md
200 https://ncert.nic.in/
200 https://nptel.ac.in
200 https://prsindia.org/
200 https://sansad.in/
200 https://swayam.gov.in/
200 https://upsc.gov.in
200 https://www.pib.gov.in/
200 https://www.upsc.gov.in/
200 https://www.upsc.gov.in/examinations/previous-question-papers
Result: 12/12 return 2xx/3xx.
== personal paths ==
OK: no personal paths.
== emails in files ==
OK: no emails in files.
```

Notes:
- `upsc.gov.in` answers 307 (redirect to `www.upsc.gov.in`, which is 200) — counts as 3xx pass.
- `ncert.nic.in/` returned one transient `000` on the first full run, then 200 on
  3/3 immediate retries and 200 in the final run — counts as pass.
- `sansadtv.nic.in` is unreachable (000, timeout); the official Parliament
  channel site `sansad.in` (200) is what the README links instead.
- `www.upsc.gov.in/examinations/` (no sub-path) returns 404, so it is not
  linked; the README links the verified `previous-question-papers` archive and
  the home page instead.
- `upsc.gov.in` (apex, no `www`) timed out (`000`) on all 3 attempts from the
  GitHub runner on 2026-10-05 (run 37343683487) while `https://www.upsc.gov.in/`
  answered `200` in the same run, so the README now links the canonical `www`
  host only. The apex is the same official site; it is just unreachable from
  the runner network.
- The repo's own future clone URL (`.../awesome-upsc-cse`) 404s because this
  repo is local-only (not pushed); it is deliberately not linked from the README.
