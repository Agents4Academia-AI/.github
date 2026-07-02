# Agents4Academia — what six agents taught us about research work

*Agents4Academia hackathon · 14–26 June 2026 · built almost entirely on Claude Code*

## The premise

Research is a lifecycle — **find** the relevant work, **organise** what you know,
**reproduce** and benchmark it, **verify** and review it. Every stage is full of
toil that is *almost* mechanical but needs judgement. We asked a simple question:
how far can LLM agents get on each stage if you take **grounding and auditability**
seriously — no fluent-but-uncheckable answers? Six teams each took a slice.

```
     DISCOVER              ORGANISE             REPRODUCE            VERIFY / REVIEW
  ┌────────────┐       ┌────────────┐       ┌──────────────┐     ┌────────────────┐
  │   Prior    │       │   UReKA    │       │  benchmark-  │     │   citation-    │
  │  atlas of  │       │    PKA     │       │  replicator  │     │  verification  │
  │   claims   │       │            │       │ (+ evaluator)│     │ Team 5: auto-  │
  └────────────┘       └────────────┘       └──────────────┘     │     review     │
                                                                 └────────────────┘
```

## The projects

**Prior** — *turn primary literature into an auditable contribution graph.* Reads
OpenAlex + arXiv, extracts each paper's contributions and claims, links them across
the literature (supports / extends / refines / **contradicts**), and reasons over
the graph. Every claim is one click from its source; contradictions are surfaced,
not averaged. `Scoper → Contributor → Cartographer → Navigator`. *(Team 6 — Klara,
Harit.)*

**UReKA** — *a knowledge-management agent.* Ingests annotated sources (Zotero PDFs,
Notion, Obsidian, arXiv, web) into an interlinked base of paper- and concept-pages,
answers cited natural-language questions (and flags gaps), and even builds full
learning courses: `/goal → /curriculum → /tutor`.

**PKA (personal-knowledge-assistant)** — *an agent that lives inside your Obsidian
vault.* PARA organisation + "calendar, not to-do lists" time management, filing
captures from Apple Notes/Reminders — always human-in-the-loop. The shareable,
de-personalised template of one researcher's working system.

**benchmark-replicator** — *paper PDF → a clean, minimal, runnable implementation*
of the method, plus the experiments to reproduce its key results. Code you can
actually read and build on, rather than a bit-rotted repo. Multi-provider
(Anthropic / OpenAI / Google / Ollama). *(Public, AGPL.)*

**benchmark-replicator-evaluator** — *does the replica actually work?* A curated
eval set of papers with reference code (DIRECT, DSOF, SimSiam, NGBoost) and
correctness tests for the replicator's output. *(Team — Arya, Olga, Sahel.)*

**citation-verification** — *check a draft's citations against evidence, not
memory.* For each `(claim, citation)` pair: is the reference **real**, is the
**metadata** right, and does the cited paper **actually support** the claim it's
attached to? Grounded in retrieved evidence, never model recollection.

**auto-reviewer** — *author-facing peer review for deep-learning papers.* A
10-stage Claude-API pipeline: PDF → structured paper → claim/evidence map →
section-by-section issues → novelty check (web search for prior work) →
significance from five reviewer personas → rigor check → drafted review →
self-critique for hallucinations and over-claims → final review + an author
improvement checklist. The PDF rides along as a **cached document block**, so each
stage sees the real figures, tables and layout — not a paraphrase; a small web app
streams the ten stages live. Aimed at helping authors *improve* papers, not
gatekeep. *(Team 5.)*

## The shared-substrate opportunity

Read six codebases side by side and the same primitives recur: **paper/PDF
ingestion + full-text fetching**, **citation / reference resolution** (DOI ↔
arXiv-id), **evidence-grounded LLM judging**, and **Claude-Code skills + a
multi-provider backend**. Prior's three standalone stages (`explore` /
`get_fulltext` / `extract`) and its `docs/shared-substrate.md` are a natural seed
for a small library the org could stand behind — so the *next* project starts from
ingestion-solved, not ingestion-again. See **[SHARED_LIBRARY_PROPOSAL.md](https://github.com/Agents4Academia-AI/.github/blob/main/SHARED_LIBRARY_PROPOSAL.md)**.

## What's next — from phenomena to problems

van der Schaar's *Open-Beginningness* (2026) names the frontier several of these
projects gesture at: not just answering posed questions, but helping decide **which
phenomena deserve attention and what questions to form around them** — the
judgement *prior* to the task. Prior's gaps and contradictions,
citation-verification's "does this actually support the claim," the review agent's
judgement calls — each is a step toward AI that helps shape *which* problems get
pursued, with the evidence and uncertainty made auditable.

## Links & credits

- **Prior** — github.com/Agents4Academia-AI/prior · *(slides linked in its README)*
- **benchmark-replicator** *(public)* · **benchmark-replicator-evaluator**
- **citation-verification** · **UReKA** · **personal-knowledge-assistant**
- **auto-reviewer** — github.com/Agents4Academia-AI/auto-reviewer

Built during [Agents4Academia](https://github.com/Agents4Academia-AI), 14–26 June
2026, largely through Claude Code.
