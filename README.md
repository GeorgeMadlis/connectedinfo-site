# ConnectedInfo Site

Public website for **ConnectedInfo** — a sibling project to [ConnectedNature](https://connectednature.org).

ConnectedInfo reframes AI-assisted queries into focused questions and checks the validity of claims that circulate widely online. Each published inquiry picks a specific widely-shared statement, reframes it as a testable question, connects independent primary sources, and publishes the synthesis with its limits visible.

The research method is inherited directly from ConnectedNature; the research engine behind both sites is [COIN](https://github.com/GeorgeMadlis/coin).

## Purpose

Often, we need to connect or synthesise information from different independent sources to obtain a broad perspective on answers to questions we are interested in. ConnectedInfo publishes the result of doing that work on specific, testable claims — typically claims that come from AI-assisted content formats (short-form video, algorithm-promoted articles) where factual accuracy is rarely the optimisation target.

The first published inquiry examines a 300k-view YouTube video that reframes longstanding passenger-rights law as "silent" 2026 airport rule changes for travellers over 65, and tests each of its twelve claims against the actual regulator.

## Relationship to ConnectedNature and COIN

- **ConnectedNature** is the public site for broad inquiries into connectedness across nature, society, knowledge, and history.
- **ConnectedInfo** (this site) is the public site for focused claim-by-claim fact-checks.
- **COIN** is the shared research engine behind both. Working materials for each inquiry live in `coin/research/<inquiry-slug>/`.

The two sites share a visual family — off-white background, serif headings, muted palette — but ConnectedInfo adds a warm secondary accent to signal its own voice (fact-checking, investigative) as distinct from ConnectedNature's primary green (scholarly, contemplative).

## Editorial principles

When adding or revising content here:

- Do not repeat a claim being tested; investigate it.
- Every specific assertion cites a primary source (regulator, statute, official airline/airport policy).
- Never cite a video, social-media post, or content-farm article as evidence.
- Mark each claim as `law`, `airline-policy`, `airport-practice`, or `discretion`.
- Do not repackage primary-source language as magic-phrase scripts.
- Uncertainty is visible where it exists.
- Finding and framing can diverge — a viral claim can be directionally suggestive while being specifically false, and the inquiry should say so.

## Page structure

Each published inquiry follows the ConnectedNature structure:

1. Title
2. Originating statement
3. Why this matters
4. Research question
5. Evidence base
6. Source evaluation
7. Competing interpretations
8. Critical synthesis
9. Limits
10. Open questions
11. Sources

## Technical direction

Plain HTML and CSS, semantic markup, no framework, no build step. Deployable directly to Cloudflare Pages from `site/`.

```
AirportRules.txt                   Source transcript for the first inquiry (not evidence)
site/
  index.html                        Landing page
  airport-rules-for-seniors.html    First published inquiry
  style.css                         (optional — CSS is currently inline per page)
```

## Cloudflare Pages settings

- Source: GitHub → `connectedinfo-site`
- Production branch: `main`
- Framework preset: `None`
- Build command: _(none)_
- Build output directory: `site`
- Custom domains: `connectedinfo.org` and `www.connectedinfo.org`

No bundler, package manager, or build tooling is required as long as deployable files remain in `site/`.

## Relative links

Top-level pages inside `site/` link like `index.html`, `airport-rules-for-seniors.html`. If posts are later moved to a subdirectory (`site/inquiries/`), internal links must be updated accordingly and home links use `../index.html`.

## Development workflow

1. Edit locally in VS Code.
2. Use the agent prompts in `.github/prompts/` for drafts (when they exist).
3. Commit to GitHub.
4. Cloudflare Pages auto-generates a preview deployment per branch.
5. Merge to `main` to publish.

## License

MIT (matching ConnectedNature and COIN).
