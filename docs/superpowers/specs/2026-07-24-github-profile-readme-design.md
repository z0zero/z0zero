# GitHub Profile README Redesign

- Status: Approved
- Date: 2026-07-24
- Profile: [github.com/z0zero](https://github.com/z0zero)

## Goal

Replace the current generator-style profile README with a focused personal-brand
dashboard that helps potential clients and recruiters understand Brian
Sangapta's positioning, strengths, and selected work within a short scan.

The primary positioning is:

> Software Engineer building AI-powered products

The profile will be written in English. It will present Brian as a hybrid
engineer who uses Python for AI and backend work and TypeScript/Next.js for
product interfaces. The primary commercial call to action is freelance and
contract work.

## Success Criteria

- The first screen communicates Brian's name, positioning, location, availability,
  and contact paths.
- A reader can identify the three strongest portfolio examples without scanning
  a long technology list.
- Project descriptions state the problem, implementation, and concrete technical
  scope rather than only listing repository names.
- Dynamic GitHub widgets support the portfolio content instead of dominating it.
- The README remains readable on narrow screens and in GitHub's light and dark
  themes.
- All links and image sources are valid, and every image has meaningful alt text.

## Audience

The primary audience is prospective freelance or contract clients. Recruiters
are the secondary audience. Both audiences should be able to quickly answer:

1. What kind of engineer is Brian?
2. What can he build?
3. Which projects demonstrate that ability?
4. How can they contact him?

## Visual Direction

Use a Modern Developer Dashboard with balanced density:

- A centered, high-energy hero followed by left-aligned content sections.
- Blue as the primary technical accent and green for availability.
- Compact badges rather than a large wall of technology icons.
- Clear spacing and short sections to preserve scanability.
- Two compact GitHub activity cards near the end.
- The existing contribution snake retained as a small footer signature.

The mockup is conceptual. The implementation must use GitHub-compatible Markdown
and supported HTML attributes; it must not depend on custom CSS that GitHub
strips.

## Content Architecture

### 1. Hero

The hero contains:

- Heading: `Hey, I'm Brian Sangapta 👋`
- Positioning: `Software Engineer building AI-powered products`
- Location: `Bandung, Indonesia`
- Availability: `Open to freelance & contract work`
- Primary links: LinkedIn and email

Proposed introduction:

> I turn machine-learning ideas into useful products—combining Python for AI
> and backend systems with TypeScript and Next.js for thoughtful web
> experiences.

Contact targets:

- LinkedIn: `https://linkedin.com/in/briansangapta`
- Email: `mailto:z0zerooooo@gmail.com`

### 2. Current Focus

Use three short focus areas:

- **Applied AI:** NLP, Transformer evaluation, and useful model-driven workflows.
- **AI Systems:** Reliable APIs, tooling, guardrails, and product integration.
- **Product Delivery:** Moving from a working prototype to a clear, usable web
  experience.

These statements describe the intended engineering direction without claiming a
job title or employment history that is not established by repository evidence.

### 3. Selected Work

Feature exactly three repositories:

1. **[UML Diagram Generator](https://github.com/z0zero/uml-diagram-generator)**

   An AI-assisted React application that turns natural-language prompts into six
   types of interactive UML diagrams. Highlight Gemini, React 19, TypeScript,
   React Flow, export support, and property-based testing.

2. **[Job Scam Detection](https://github.com/z0zero/job-scam-BERT-ALBERT-RoBERTa)**

   A Transformer-based text-classification project comparing BERT, ALBERT, and
   RoBERTa on 17,880 job postings, with multi-seed evaluation and a Streamlit
   inference application.

3. **[NeetCode Subtitle Translator](https://github.com/z0zero/NeetCode-Subtitle-Translator)**

   A Chrome extension that translates NeetCode subtitles from English to
   Indonesian using batch pre-translation, local caching, and Google
   Translate/DeepL fallback.

Each entry will use a linked title, a one-sentence outcome-oriented description,
and a compact technology line. The project section appears before the general
technology section so evidence leads the narrative.

### 4. Core Toolkit

Limit the main toolkit to eight relevant items:

- Python
- TypeScript
- Next.js
- React
- FastAPI
- Transformers
- Gemini
- Git

Use compact badges with consistent styling. Do not restore the previous
all-inclusive technology logo wall.

### 5. GitHub Activity

Keep two compact cards:

- GitHub profile statistics
- Top languages

Do not include the trophy showcase or streak card. The cards must use matching
themes, responsive sizing, meaningful alt text, and links back to Brian's
profile.

### 6. Footer

Use the personal signature:

> Fueled by curiosity, shipped with coffee ☕

Place the existing contribution snake below the signature. Reuse the current
`output` branch asset and existing workflow; changing the workflow is outside
this README redesign.

## Removals

Remove these elements from the current README:

- Generic `A passionate Software Engineer from Indonesia` subtitle
- Profile trophy showcase
- Long list of more than thirty unrelated technology logos
- Streak statistics card
- Generic learning and “ask me about” bullets
- Coffee fun-fact wording that does not support the new profile narrative
- Profile-view counter

## External Dependencies

The README may depend on:

- Shields.io for compact badges
- GitHub Readme Stats for the two activity cards
- The existing `raw.githubusercontent.com/z0zero/z0zero/output/snake.svg` asset

No new workflow, generated banner, or repository dependency is required. If an
external widget is unavailable, its alt text and surrounding section heading
must preserve context.

## Scope Boundaries

This redesign changes the profile README only. It does not:

- Change Brian's GitHub account bio, account-level location, or pinned
  repositories.
- Rewrite the featured projects' own README files.
- Add a portfolio website or new social platform.
- Modify the existing snake-generation workflow.
- Add new automation or generated visual assets.

The visual companion's `.superpowers/` directory is temporary design tooling and
must not be included in the implementation commit.

## Verification

Implementation verification will include:

1. `git diff --check`
2. Markdown and embedded HTML inspection for balanced tags and valid structure
3. Automated link and image-source checks where the endpoints permit them
4. A rendered preview at desktop and narrow widths
5. Confirmation that only intended profile files are staged

There is no application test suite in this repository, so verification focuses
on rendering, links, repository hygiene, and the resulting Git diff.
