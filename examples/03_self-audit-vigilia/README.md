# Example 03 — a self-audit of Vigilia

Not a fixture. **Vigilia is the product this auditor's methodology came out of** —
a live service at [aivigilia.com](https://aivigilia.com) that sells EU AI Act
audits for €499, run by the same person who wrote this repository.

So it gets audited by its own auditor, in public, and it did not come out clean.

**Run three times.** The first run, 2026-09-03, returned one MAJOR and one MINOR.
The operator shipped a fix and the audit was re-run on 2026-09-06: the MAJOR became
a PASS. The operator shipped a second fix and the audit was re-run on 2026-09-09:
the MINOR became a PASS — and the fix activated an obligation that had been
NOT_APPLICABLE while there was nothing to grade, which now scores a smaller MINOR
of its own. Every state is kept — the superseded captures are preserved in the
evidence pack, and each finding carries its own history — because a remediation
you cannot check against what it replaced is a claim, not a record.

| | First run, 2026-09-03 | Re-run, 2026-09-06 | Re-run, 2026-09-09 |
|---|---|---|---|
| **F-08** · disclosure at the point of interaction on the free checker | PARTIAL · **MAJOR** | **PASS** — disclosure now sits above the submit control and repeats on the snapshot, in five languages | PASS |
| **F-02** · machine-readable marking of synthetic content | FAIL · **MINOR** | FAIL · MINOR, still open — inside the Article 111(4) window until 2 December 2026 | **PASS** — IPTC `digitalSourceType` on the dispatches and the feed, a provenance header and block on the checker |
| **F-03** · quality of the marking technique | NOT_APPLICABLE — nothing to grade | NOT_APPLICABLE | **PARTIAL · MINOR** — interoperable and consistent, and metadata beside plain text does not survive the text being copied; the limit of what is feasible for text |
| PASS | three | four | five |

There is an obvious reason not to publish this: it is a list of ways a commercial
product falls short, written by its own operator, on the internet, permanently.

It is here anyway, because an auditor whose only worked examples are invented
companies that behave exactly as the auditor expects has demonstrated nothing.
The interesting question about any audit tool is what it says when the answer is
inconvenient — and then whether anything changes because it said it.

Evidence was captured from the live site on 2026-09-03, 2026-09-06 and 2026-09-09,
each capture preserved beside the next, and is reproduced in `evidence-pack/` so the
findings can be checked without trusting this summary.
The audit covers **public surfaces only** — the authenticated €499 workspace was
not examined, and the report says so.

```bash
python3 _verify/verify_citations.py examples/03_self-audit-vigilia/audit-report.md
```
