# Postgraduate Research Planner

A free, single-file, privacy-first planner for PhD and MRes applicants — find a supervisor, draft a proposal, write outreach emails, build a CV and portfolio, and track your application timeline. **Researcher Arena**, at the top of the sidebar, adds a layer of research-planning-and-development tools: scholarly-graph and researcher search, dataset discovery with an in-browser dataset health check, a research-gap finder, an eight-style citation generator, compute/GPU guidance, a reproducibility checklist, a statistical-test advisor, and a literature-matrix builder.

**Live site:** https://pathik0007.github.io/postgrad-research-planner/ *(active once GitHub Pages is enabled — see below)*

## Why this exists

Most of what a graduate research applicant needs is scattered across a dozen different sites — Google Scholar, OpenAlex, ORCID, FindAPhD, citation managers, GPU pricing pages, dataset repositories — with no single place that turns "I have some research interests" into a shortlisted supervisor, a drafted proposal, and a packaged application. This tool doesn't replace any of those sites; it sits in front of them, turning your profile into targeted, correctly-built search links and giving you a structured workspace for everything you draft along the way.

## What it does

**Core workflow**
- **My profile** — your interests, target degree, region and background, set once and reused everywhere else.
- **Find supervisors** — live, targeted searches across Google Scholar, ORCID, LinkedIn, ResearchGate and site-restricted university faculty pages, plus a funding & grants finder scoped to your selected region.
- **Papers & frameworks** — literature search across the tools researchers actually use, plus a reference shelf of common frameworks and dataset hubs.
- **Proposal builder** — a nine-section guided structure (title, background, research questions, significance, methodology, research environment, timeline, ethics, references), each with an optional AI-assisted first draft.
- **Outreach emails** — cold introduction, follow-up, thank-you and status-inquiry templates generated from your profile, ready to edit before sending.
- **CV & résumé** — style guidance for an academic CV vs. an industry résumé, a bullet-point rewriter, and real template links.
- **Portfolio** — format guidance and site-builder links (GitHub Pages, Academic Pages, Carrd, Google Sites).
- **Journals & publishing** — journal-matching tools, citation-style reference, and reference-manager links.
- **Timeline & checklist** — a 12-month application runway with saved progress.
- **Resource library** — every link in the tool, searchable and typo-tolerant.

**Researcher Arena** (9 tools)
- Scholarly & researcher search — OpenAlex, Semantic Scholar and Crossref, with a Papers/Researchers toggle.
- Dataset corner — dataset search across major hubs, plus a real, in-browser CSV health check (row/column counts, missing values, duplicates, class balance) that never leaves your browser.
- Research gap finder — AI-assisted, but grounded only in the paper list you paste in; every gap is traced back to specific numbered items.
- Citation generator — one entry, eight reference styles (APA, IEEE, Harvard, Vancouver, MLA, Chicago, BibTeX, RIS).
- Compute & GPU finder — GPU tiers by VRAM, real provider links, a VRAM estimator, and your own compute-cost math (never an invented price).
- Metrics & baselines — when to use (and avoid) each evaluation metric, plus starting baseline model sets by task.
- Reproducibility checklist — a transparent, self-scored checklist against real reproducibility standards.
- Statistical test advisor — a decision-tree recommendation from your study design, not guesswork.
- Literature matrix builder — an exportable comparison table across papers, with optional AI-assisted row extraction from a pasted abstract.

## How it's built

- **Single HTML file.** Everything — markup, styles, and logic — lives in `index.html`. No build step, no framework, no package installs.
- **No backend, no tracking.** Everything you type is saved only to your browser's `localStorage`. Nothing is uploaded anywhere, and there's no login, analytics, or third-party tracking script.
- **Real links, not invented data.** Every "search" feature builds an actual, correctly-encoded URL to the real site (Google Scholar, OpenAlex, ORCID, Crossref, Zenodo, and so on) rather than fabricating results. Nothing here claims to know a fact — such as a supervisor's name, a paper's existence, or a live GPU price — that it hasn't linked you to verify yourself.
- **AI-assisted features are optional and additive.** Draft buttons (marked with a spark) for the proposal, outreach polish, CV bullets, gap finder and portfolio summary only appear when the page is running inside a Claude-connected environment. Outside of that (for example, this GitHub Pages copy, or opening the file directly in a browser), those buttons stay hidden and the rest of the tool works identically — it's the same reason no invented fact ever appears without a real link behind it.

## Running it locally

No installation needed — just open `index.html` in any modern browser. To serve it locally instead of using `file://` (recommended if you plan to test the file-upload dataset checker):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploying your own copy

This repository is set up to serve directly from GitHub Pages — `index.html` at the repository root becomes the live site with no build step. See the deployment commands provided alongside this README for the exact steps.

## Project structure

```
.
├── index.html   # the entire application — markup, CSS and JavaScript
└── README.md    # this file
```

## Limitations

- No live external API calls (OpenAlex, Semantic Scholar, etc.) are made from the page itself — every "search" opens the real site in a new tab instead of embedding results. This is a deliberate choice, not a missing feature: it keeps every result 100% real and verifiable, with no risk of showing stale, wrong, or fabricated data.
- Nothing here can guarantee search-engine ranking or inclusion in AI answer summaries — the SEO and structured-data work behind this site improves how accurately it can be found and described, not whether it will be.
