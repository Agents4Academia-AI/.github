# Agents4Academia

A two-week open-source AI-for-science hackathon.

**14–26 June 2026** · Oxford (Department of Statistics) and Singapore (NUS + NTU) — hybrid via video, no travel.

We're building open-source AI agents for the parts of research that AI really should be helping with — keeping up with literature, hunting for grants, evaluating the agents themselves, cross-disciplinary translation, and whatever pain participants most want gone. Teams pitch problems on Day 1, self-organise around them, and ship working systems plus technical write-ups by the end of the fortnight.

🌐 [agents4academia.github.io](https://agents4academia.github.io)

---

## Where to find what

| | |
|---|---|
| 📄 **Motivation white paper** | [Google Doc](https://docs.google.com/document/d/1GTOP_8SN2efNR4bdRnMmcNZUERBlsN2ihLt2mlUFJYg/edit?usp=sharing) — the *why* this hackathon exists |
| 🗓️ **Schedule** | [Google Doc](https://docs.google.com/document/d/1B3b99ug1ygjJ-_M99URbHuIcsk-SRwqbnF8hu_-7yGU/edit?usp=sharing) — day-by-day, presence model, locations |
| 👋 **Introductions deck** | [Google Slides](https://docs.google.com/presentation/d/19d5hSmsinA1zZN9ncZYQT1kU2mjdyN-suy5MWghKW7k/edit?usp=sharing) — who's in the cohort |
| 💡 **IDEAS deck** | [Google Slides](https://docs.google.com/presentation/d/1pkmUqRoULQxsCMauU6raMWSkNoZio7rPVcl6rvJscW8/edit?usp=sharing) — what we're building and starter ideas |

## Repositories

| Repo | What |
|------|------|
| [example-agents](https://github.com/Agents4Academia-AI/example-agents) | Day-1 workshop materials — three tracks for *building* agents (Claude Code, Anthropic SDK, Agent SDK) plus a bonus track on *operating* them well |
| `team-…` | One repo per team, created on Day 1 after team formation |

## Teams & projects

Six teams, spanning the research lifecycle — **find → organise → reproduce → verify**:

| Project | What it does | Repo |
|---|---|---|
| **Prior** | primary literature → an auditable graph of claims & contributions (provenance · contradictions · confidence) | [prior](https://github.com/Agents4Academia-AI/prior) |
| **UReKA** | ingest Zotero/Notion/Obsidian/arXiv → a linked knowledge base + auto-built learning courses | [UReKA](https://github.com/Agents4Academia-AI/UReKA) |
| **PKA** | a Claude Code agent inside your Obsidian vault — PARA + calendar-based time management | [personal-knowledge-assistant](https://github.com/Agents4Academia-AI/personal-knowledge-assistant) |
| **benchmark-replicator** | paper PDF -> a clean, runnable implementation + reproduction experiments | [benchmark-replicator](https://github.com/Agents4Academia-AI/benchmark-replicator) |
| **benchmark-replicator-evaluator** | evaluates the replicas against reference code | [...-evaluator](https://github.com/Agents4Academia-AI/benchmark-replicator-evaluator) |
| **citation-verification** | verify a draft's citations against retrieved evidence — real? metadata right? claim supported? | [citation_verification](https://github.com/Agents4Academia-AI/citation_verification) |
| **automated review** *(Team 5)* | agentic assessment / peer review of papers | *forthcoming* |

## Outcomes & write-up

**Full report -> [REPORT.md](https://github.com/Agents4Academia-AI/.github/blob/main/REPORT.md)** — the research-lifecycle framing, each project, and an honest **model-behaviour & failure-modes** section.

A few things every team hit: models **confabulate citations** unless you force retrieval; **provenance beats fluency**; **confidence is easy to show, hard to earn**; and the **infrastructure tax** (Semantic Scholar / OpenAlex rate limits, PDF extraction, full-text licensing) is real and shared. Built almost entirely on **Claude Code**.

## Organisers

Klara Kaleb · Harit Vishwakarma · Yee Whye Teh — all at Oxford Department of Statistics.

## Advisors

Tom Rainforth (Oxford) · Wee Sun Lee (NUS) · Luke Ong (NTU).

## Supported by

University of Oxford (Department of Statistics) · Anthropic (Claude Code licenses + Claude API credits for the cohort).
