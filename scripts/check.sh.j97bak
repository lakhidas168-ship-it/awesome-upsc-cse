#!/usr/bin/env bash
# Gates for awesome-upsc-cse (mirrors awesome-electrical-exams):
# 1. every https:// URL in README.md + resources/ answers 2xx/3xx
# 2. no personal home-directory paths outside .git/
# 3. no email addresses in tracked files (author lives in git config, not files)
set -u
REPO="$(cd "$(dirname "$0")/.." && pwd)"
fail=0

echo "== link check =="
urls=$(grep -rhoE 'https://[^)>"'"'"' ]+' "$REPO/README.md" "$REPO/resources" | sort -u)
n=0; ok=0
for u in $urls; do
  n=$((n+1))
  code=$(curl -s -o /dev/null -w '%{http_code}' -m 25 -L "$u" || true)
  echo "$code $u"
  case "$code" in
    2*|3*) ok=$((ok+1)) ;;
    *) echo "FAIL: $u -> $code"; fail=1 ;;
  esac
done
echo "Result: $ok/$n return 2xx/3xx."

echo "== personal paths =="
HOME_RE='/(Users|home)/'
if grep -rInE "$HOME_RE" "$REPO/README.md" "$REPO/resources" "$REPO/docs" "$REPO/data" "$REPO/scripts" 2>/dev/null; then
  echo "FAIL: personal paths found"; fail=1
else
  echo "OK: no personal paths."
fi

echo "== emails in files =="
if grep -rInE '[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}' "$REPO/README.md" "$REPO/resources" "$REPO/docs" "$REPO/data" "$REPO/scripts" 2>/dev/null; then
  echo "FAIL: email addresses found in files"; fail=1
else
  echo "OK: no emails in files."
fi

exit $fail
