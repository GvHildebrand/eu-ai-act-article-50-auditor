# Stranger tests

The README is measured on people and agents who have never seen this repository, not
argued. Every run is recorded here, including the ones that go badly.

## Run 1 · 2026-09-16 · fresh AI session, link only

**Who.** A fresh Claude session with no context, given only the repository link. It was
told to stay inside its own clone.
**Task.** Audit an invented product: a support chatbot called "Parla" on a Berlin shop's
site. It opens with "Hi! I'm Lena, how can I help you today?", generates text, launched
2026-03-01 and has no metadata dump. The operator described itself as a deployer.
**Result.** A passing report in about 10 tool calls: 11 findings, all 11 obligations
covered. It passed on the second verifier run.

Where it got stuck, and what is still open:

| # | Confusion | Status |
|---|---|---|
| 1 | The operator said "deployer", but QUICKSTART's own definition makes a shop that built its own bot a provider too. Nothing says what to do when a stated fact contradicts a definition, and taking the stated fact would have turned 50(1), 50(2) and 50(5) into not applicable with a still-passing report. | open: the most serious one |
| 2 | QUICKSTART says to paste a prompt, but every finding needs an `evidence:` file and line. The stranger had to discover `_templates/evidence-pack/` and build one. | open |
| 3 | Nothing says where to save the report. | open |
| 4 | The six facts do not ask about law-enforcement authorisation or SME status, while `rules.md` makes an unstated row force INSUFFICIENT_EVIDENCE. Taken literally, that contradicts "nine of eleven get a verdict". | open |
| 5 | The deadline for a transitional finding has to be in the `finding` field. The verifier's message does not name the field, and it cost one failed run. | open |
| 6 | Pasted text: `observed` or `declared`? Not stated in `rules.md`. | open |
| 7 | The example reports say `python3 tools/verify_citations.py`. There is no `tools/`; the script is in `_verify/`. | open |
| 8 | The template has no `NONE` severity row and no "rests on the operator's word" section, though the examples and `rules.md` have both. | open |

## Run 2 · human outsider

Not yet run. Planned: one person who has never seen the repository, timed from the link to
a passing report, with their confusions written down here in the same shape as run 1.
