# Agents4Academia

![The research lifecycle, agent-augmented](lifecycle_ribbon.png)

A community building open-source agents for the boring parts of academic life —
so you can finally take that vacation (for real this time).

We build agents that live across the research workflow — from discovering
literature, to organising your notes, to reproducing baselines, to verifying
citations, to reviewing your own drafts. Every project is open-source, and we
welcome collaborators from any institution.

Our first cohort launched with a two-week hackathon in June 2026 across Oxford
Statistics, NUS, and NTU, with generous support from Anthropic. It shipped five
open-source agents that cover the research lifecycle end-to-end.

**House rule:** our agents show their sources and say "not found" rather than
guess. Fluent summaries are easy; checkable ones are the product.

## Projects

The five agents span the academic workflow:

| | Verb | Project | What it does |
|---|---|---|---|
| 🔍 | DISCOVER | [Prior](https://github.com/Agents4Academia-AI/prior) | Auditable knowledge graph of claims and contributions from primary literature — state of a field, contradictions, open questions. |
| 🗂️ | ORGANISE | [UReKA](https://github.com/Agents4Academia-AI/UReKA) | Personal research knowledge assistant unifying Zotero, Notion, Obsidian, and arXiv into one linked, queryable knowledge base. |
| 🔁 | REPRODUCE | [Benchmark-Replicator](https://github.com/Agents4Academia-AI/benchmark-replicator) | Clean, minimal, runnable implementation of any prior empirical paper. |
| ✅ | VERIFY | [RefWarden](https://github.com/Agents4Academia-AI/citation_verification) | For every (claim, citation) pair in your draft: does the reference exist, is the metadata right, does the cited paper actually support the claim? |
| 📝 | REVIEW | [Auto-Reviewer](https://github.com/Agents4Academia-AI/auto-reviewer) | 10-stage pipeline that turns a paper PDF into claim/evidence maps, novelty and rigor checks, and a self-critique pass for hallucinations. |

These aren't demos-on-slides: Prior mapped 152 papers into 581 contributions and
989 typed relations on its own field; Benchmark-Replicator rebuilt NGBoost from
the PDF alone and passed 36/36 tests and 7/7 verification criteria; RefWarden
verified 106 claim–citation pairs on a recent RL paper in under seven minutes,
catching real author and venue mismatches.

Building side by side, the teams kept reinventing the same plumbing — so we
carved it into [**academia-core**](https://github.com/Agents4Academia-AI/academia-core):
shared full-text ingestion, citation resolution, and evidence-grounded judging
that any research agent (yours too) can build on.

## Get involved

- **Try the tools.** Every repo has a README and a `pip install`. If something's confusing, open an issue.
- **Contribute.** Pull requests, evaluations on new domains, integrations with your existing workflow — all welcome.
- **Build on the plumbing.** Writing your own research agent? Adopt [academia-core](https://github.com/Agents4Academia-AI/academia-core) and skip the boring 20%.
- **Organise a chapter.** If you'd like to run an Agents4Academia hackathon at your institution, get in touch.
- **Join the next hackathon.** We're planning v2. Watch this space or contact the organisers.

## Acknowledgements

Supported by Anthropic (Claude Code plans and API credits), Oxford Statistics,
NUS School of Computing, and NTU College of Computing and Data Science.

Thanks to our advisors: [Tom Rainforth](https://github.com/twgr),
[Wee Sun Lee](https://github.com/WeeSun), [Luke Ong](https://github.com/lukeong).

## Contact

The organisers: [Klara Kaleb](https://github.com/klarakaleb) (Oxford),
[Harit Vishwakarma](https://github.com/harit7) (Oxford),
[Yee Whye Teh](https://github.com/ywteh) (Oxford),
[Wei Liu](https://github.com/jugechengzi) (NUS),
[Mingye Zhu](https://github.com/stevie1023) (NTU),
[Yunqiao Yang](https://github.com/hustyyq) (NTU).

Reach us via GitHub issues on any project, or through the linked profiles above.

---

*Agents4Academia is a community-led initiative. All projects are open-source
under permissive licences. Made with care by researchers, for researchers.*
