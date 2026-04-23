# ConnectedInfo website instructions

This repository contains the public website for **ConnectedInfo**.

## Project purpose

ConnectedInfo is a sibling project to [ConnectedNature](https://connectednature.org). Where ConnectedNature publishes broad inquiries into connectedness across nature, society, knowledge, and history, ConnectedInfo publishes focused claim-by-claim evaluations of specific statements that circulate widely online — typically AI-assisted short-form content whose factual basis is thin.

Each published inquiry:

1. Picks a specific widely-shared claim (usually from a viral video, social post, or algorithmically-promoted article).
2. Reframes it as a testable research question.
3. Tests each specific factual claim against the relevant primary source (regulator, statute, official policy).
4. Publishes a synthesis that separates real rights from invented framing.

The working research materials for each inquiry live in [COIN](https://github.com/GeorgeMadlis/coin) under `research/<inquiry-slug>/`. This repository contains only the public-facing site.

## Editorial principles

When writing or revising content:

- **Do not repeat the claim; investigate it.** A page that just quotes a viral claim and then argues about it amplifies the claim. Reframe it as a research question first.
- **Primary sources only.** Every factual assertion cites a regulator, statute, or official operator/airline policy — never another video, blog, or content farm.
- **Claim classification is mandatory.** Each right, rule, or entitlement in an inquiry is marked as one of: `law`, `airline-policy`, `airport-practice`, or `discretion`. Never blur them.
- **No magic phrases.** Do not repackage primary-source language as scripted sentences for readers to recite at staff. If a reader needs to know how to invoke a right, describe the mechanism (for example, "request at booking, at least 48 hours before departure") rather than a line to say.
- **Uncertainty is visible.** If a claim is contested, if scope varies by carrier, or if the evidence supports a narrower conclusion than the framing suggests, the page says so.
- **Findings and framings can diverge.** A viral claim can be directionally suggestive while being specifically false. An inquiry should be able to say both things at once.
- **No hype, no "the truth they don't want you to know."** The tone is calm, precise, evidence-first. If the inquiry's finding sounds like a clickbait headline, the framing is wrong.

## What every inquiry page should contain

Preferred structure (inherited from ConnectedNature):

1. Title
2. Originating statement (quoted verbatim from the source being tested, in a distinguishable block)
3. Summary verdict — stated up front, before the evidence
4. Why this matters
5. Research question
6. Evidence base (list of primary sources consulted)
7. Source evaluation of the original claim itself
8. Claim-by-claim table (if the source makes multiple specific claims)
9. Jurisdiction check (if the claim is about rules that might vary geographically)
10. Competing interpretations
11. Critical synthesis
12. Limits of the inquiry
13. Open questions
14. Sources (numbered, each linking to the primary source)

Pages may omit steps that do not apply — for example, an inquiry into a single claim does not need step 8.

## Design principles

The visual style inherits from ConnectedNature:

- Off-white warm background
- Dark neutral text
- Muted green primary accent (shared with ConnectedNature)
- **Warm ochre secondary accent** — this is the distinguishing ConnectedInfo mark. Use it for eyebrows, the "published inquiry" badge, feature-card left borders, and call-to-action buttons. This signals investigative / fact-checking tone without breaking the ConnectedNature family.
- Serif headings (Iowan Old Style / Palatino family)
- Sans-serif body text
- Spacious layout, subtle borders, calm cards
- No flashy animation, no hero video, no unnecessary JavaScript

The site should read like a research record, not like a news aggregator or an "AI product" landing page.

## Technical rules

Unless explicitly told otherwise:

- Plain HTML and CSS only. No framework, no bundler, no package manager.
- Semantic HTML, accessible markup.
- Styling should be centralised where possible (currently inline per page, can be externalised to `site/style.css`).
- Relative links; no build-time path rewriting.
- No tracking scripts.

## Site structure

```
site/
  index.html                            Landing page
  airport-rules-for-seniors.html        First published inquiry
  inquiries/                            (future — for expansion)
  style.css                             (optional externalised CSS)
```

## Content relationship to ConnectedNature and COIN

- ConnectedInfo pages can link to ConnectedNature where the topic overlaps.
- Each inquiry should include a link to the working research folder in COIN where the claims ledger, source notes, and evaluation live (the pattern ConnectedNature uses for its Research Trail sections).
- Do not expose engine-level implementation details (COIN pipeline, SQLite schema, prompts) on the public site unless they help the reader understand the research method.

## When creating or editing pages

Always preserve:

- The separation between quoted originating claim and published synthesis.
- The sibling relationship to ConnectedNature (linked in both the header and the footer).
- The primary-source-only rule.
- The calm, evidence-first tone.
- The `law` / `airline-policy` / `airport-practice` / `discretion` classification for any right cited.

When making improvements:

- Clarity first.
- Source strength second (prefer the regulator to the summary of the regulator).
- Visual hierarchy third.
- Keep the site simple.
