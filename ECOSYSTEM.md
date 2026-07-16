# Join the Agents4Academia ecosystem

Built an open-source agent for academic work — literature, data, reproducibility,
review, writing, teaching, admin — and want it to be part of a shared effort rather
than another tool built in isolation? This is the on-ramp. There's no heavy process:
read this, pick a direction, and open an issue (or ping us) — we'll help wire it in.

## Where your project fits — the research lifecycle

Our first cohort shipped five agents spanning one arc of the lifecycle:

**🔍 Discover → 🗂️ Organise → 🔁 Reproduce → ✅ Verify → 📝 Review**

That arc is not the whole map. Real research runs earlier and wider — **question
formation and ideation**, experiment design, data curation, teaching, administration.
A new project is welcome whether it **fills a gap** no current agent covers or
**deepens a stage** that already exists. If you're not sure where yours sits, that's
a great thing to open a discussion about.

## Two ways to join

Pick whichever fits — **you keep your license and ownership either way.**

1. **Interoperate + cross-link.** Keep your repo exactly where it is. Adopt the light
   conventions below, lean on [`academia-core`](https://github.com/Agents4Academia-AI/academia-core)
   where it overlaps, and we cross-link your project from the org profile and lifecycle
   map. Lowest friction — good for established projects with their own PyPI / DOI / CI.
2. **Bring it into the org.** Transfer or mirror the repo under `Agents4Academia-AI`.
   You stay the maintainer and keep your license; in return you get org-level
   visibility, shared infrastructure, and a community around it.

Not sure? Start with (1); moving to (2) later is easy.

## Build on the shared infrastructure

While building side by side, the cohort kept reinventing the same plumbing, so we
extracted it into [**academia-core**](https://github.com/Agents4Academia-AI/academia-core):

- paper / PDF / arXiv / LaTeX → clean full text
- DOI ↔ arXiv-id ↔ OpenAlex-id resolution + metadata validation
- rate-limited source clients (OpenAlex / Semantic Scholar / Unpaywall) with backoff
- evidence-grounded judging (answers/verdicts grounded in retrieved sources, with
  honest "not found" abstention)
- a multi-backend LLM seam (API / Claude Code / CLI)

Use what helps; ignore what doesn't. Contributions back are welcome.

## Light conventions we ask for

Just enough to make projects legible and citable — nothing heavy:

- **Open license** (Apache-2.0 preferred; any OSI-approved permissive license is fine).
- **A `CITATION.cff`** so people can cite your work.
- **A clear README** with setup instructions and a runnable example.
- **Repo topics + a one-line description** that says which stage/gap you address.
- **Transparency about sources and uncertainty** — outputs should be checkable and
  traceable (see our [principles](https://github.com/Agents4Academia-AI/.github/blob/main/profile/README.md#our-principles)).

## How to start

Open an issue or discussion on the [`.github`](https://github.com/Agents4Academia-AI/.github)
repo — tell us what your project does and which stage or gap it fits — or reach us on
[Discord](https://discord.gg/fEDXaSWwj), [X](https://x.com/agents4academia), or
[Bluesky](https://bsky.app/profile/agents4academia.bsky.social). We'll take it from there.
