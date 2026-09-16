# EU AI Act Article 50 auditor

**Drop this folder into Claude and it audits your AI product against Article 50 of the
EU AI Act. A script then checks every quote in the report against the law itself.**

**Scope: Article 50 only.** It does not cover the high-risk rules, the prohibitions, the
general-purpose AI obligations or the GDPR. It is a gap analysis, not legal advice or a
certification. The scripts check that each finding cites real law correctly. They cannot
tell you whether a verdict is legally right.

## Quickstart

1. **Load it.** Upload this folder to a Claude project, or clone it and open it in Claude Code.
2. **Ask for an audit.** Paste the prompt in [QUICKSTART.md](QUICKSTART.md): what a user
   first sees, plus six facts about your product. Nine of the eleven obligations get a
   verdict from that alone.
3. **Check the report.** Needs Python 3.9+ and nothing else:

   ```bash
   python3 _verify/verify_citations.py path/to/audit-report.md
   ```

   It fails if a quote does not match the law line by line, an obligation was skipped, or a
   severity does not follow from the published matrix. A report that fails is not finished.

To see a finished audit first, read [example 01](examples/01_fixture-saas-chatbot/).
`make verify` checks everything shipped in this repository. It works offline.

The README is tested on strangers, not argued: [docs/stranger-tests.md](docs/stranger-tests.md)
records every run and every place a newcomer got stuck.

## Where things are

| | |
|---|---|
| [`reference/`](reference/) | The law, verbatim from the EU Publications Office, hashed and re-fetchable |
| [`provisions/article-50.md`](provisions/article-50.md) | The eleven obligations the auditor checks |
| [`identity.md`](identity.md) · [`rules.md`](rules.md) | What the auditor refuses to do, and its procedure |
| [`examples/`](examples/) | Three worked audits, including a self-audit of its author's own paid service |
| [`docs/how-it-works.md`](docs/how-it-works.md) | The full reasoning: design, guarantees and limits, the Digital Omnibus, how to break it |

## Who made it

Built by Gregorio von Hildebrand as the open core of [Vigilia](https://aivigilia.com), which
sells Article 50 audits. That commercial tie is why example 03 audits Vigilia itself.

MIT licence for the auditor. The legislation in `reference/` is © European Union, reused
under Commission Decision 2011/833/EU, and is not affiliated with or endorsed by the EU.
See [`reference/MANIFEST.md`](reference/MANIFEST.md).
