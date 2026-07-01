# Proposal — `academia-core`: a shared library for Agents4Academia

*RFC / draft for discussion · seeded by the Prior team · built on `docs/shared-substrate.md` (Prior repo)*

## Why

Read the cohort's repos side by side and the same plumbing appears in nearly every one — each team built it from scratch:

| Primitive | Reinvented by |
|---|---|
| paper / PDF / arXiv / LaTeX → clean full text | prior · benchmark-replicator · citation-verification · UReKA |
| DOI ↔ arXiv-id ↔ OpenAlex-id resolution + metadata validation | prior · citation-verification |
| rate-limited source clients (OpenAlex / Semantic Scholar / Unpaywall) + backoff | prior — the 429 tax everyone paid |
| evidence-grounded LLM judging (claim ↔ evidence) | prior (self-eval) · citation-verification (relevance) · benchmark evaluator |
| multi-provider LLM backend (Claude Code / Anthropic / OpenAI / Gemini / Ollama) | prior · benchmark-replicator |
| Claude Code skills (fetch / verify / extract) | citation-verification · UReKA · PKA |

Six teams solved "get me the clean text of this paper" six times, and all of us fought Semantic Scholar / OpenAlex 429s independently. **Extract once, reuse everywhere** would have saved days.

## Proposal

A small, permissively-licensed (MIT) org package — working name **`academia-core`** — that packages the *plumbing*, not anyone's application logic. Deliberately thin.

### Modules
- **`sources/`** — resilient clients for OpenAlex, arXiv, Semantic Scholar, Unpaywall, Crossref. Backoff + caching + preflight baked in, so no team eats the 429 tax again.
- **`ingest/`** — `fetch_fulltext(id | doi | url | pdf | tex)` → clean, section-structured text via a multi-source cascade (arXiv → OA → Unpaywall → preprint → publisher-TDM → `citation_pdf_url`). License-aware: free channels by default, publisher TDM opt-in via your own keys. *(Seed: Prior's `get_fulltext.py`.)*
- **`resolve/`** — `resolve_ref(...)` → `{doi, arxiv_id, openalex_id, exists, metadata_issues}`; the "is this citation real, and are authors / venue / year right?" primitive.
- **`judge/`** — `supports(claim, evidence)` → `{verdict, justification, confidence}`; one grounded-judging schema for citation-support, claim-faithfulness, and correctness checks.
- **`llm/`** — a thin backend over Claude Code / Anthropic / OpenAI / Gemini / Ollama with one `complete()` / `judge()` interface.
- **`skills/`** — drop-in Claude Code skills (`fetch-fulltext`, `verify-citation`, `extract-claims`).

### API sketch
```python
from academia_core.ingest import fetch_fulltext
text = fetch_fulltext("arxiv:2308.08155")          # doi / url / local PDF / .tex zip all work

from academia_core.resolve import resolve_ref
ref = resolve_ref(title="...", authors="...", year=2024)   # -> exists?, ids, metadata_issues

from academia_core.judge import supports
v = supports(claim="RAG reduces hallucination", evidence=abstract)   # -> verdict + justification + confidence

from academia_core.sources import openalex
hits = openalex.search("retrieval augmented generation", per_page=50)   # backoff handled
```

## What each team gets
- **benchmark-replicator / evaluator** — `ingest` (paper → text) + `resolve`, free; keep your replication logic.
- **citation-verification** — `ingest` (arXiv/PDF/LaTeX) + `resolve` (reality + metadata) + `judge` (support) = steps 1–2 of your pipeline, shared.
- **UReKA** — `ingest` for arXiv/web sources; `resolve` for linking.
- **Prior** — donates the seed and drops its private copies.
- **automated review** — `judge` + `ingest` when it lands.

## Migration path (incremental, opt-in)
1. **Carve** Prior's `sources/`, `fulltext.py`, resolution, `llm.py`, and judging into a standalone `academia-core` repo (Prior keeps a thin dependency, loses no behaviour).
2. **Publish** `pip install "academia-core @ git+..."` (benchmark-replicator already installs this way).
3. **Adopt one module at a time** — start with `ingest.fetch_fulltext` (the biggest shared pain), then `resolve`, then `judge`. No big-bang rewrite.
4. **Versioned** (semver), CI + tests, one maintainer per module.

## Scope — what it is *not*
Not a framework, and not anyone's agent. Application logic — Prior's Cartographer, the replicator's codegen, the reviewer's judgement — stays in each repo. `academia-core` is the boring, shared 20% everyone needs and no one should own twice.

## Relation to the shared claim-graph
This is the **code** layer. There's a complementary **state** layer — a shared claim graph agents read and write (Prior's `docs/shared-substrate.md`): enrichers stamp verifications, consumers query. You need the library to populate that graph. Adopt the library first; the shared graph can follow.

## Open questions
- Name + license (MIT for a library, even though some repos are AGPL?).
- Home: a new `academia-core` repo (preferred) vs. a package here.
- Who maintains each module after the hackathon?

---
*Comments welcome — via issues on the eventual `academia-core` repo, or the cohort channel.*
