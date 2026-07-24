# GitHub Profile README Refresh Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the outdated generator-style profile README with the approved,
English-language Balanced Dashboard that presents Brian as a Software Engineer
building AI-powered products and invites freelance or contract enquiries.

**Architecture:** Keep the profile as one GitHub-Flavored Markdown document with
small, supported HTML blocks for alignment. Put durable portfolio content before
dynamic widgets, limit external dependencies to Shields.io, GitHub Readme Stats,
and the existing snake asset, and leave the snake workflow unchanged.

**Tech Stack:** GitHub-Flavored Markdown, GitHub-supported HTML, Shields.io,
GitHub Readme Stats, existing GitHub Actions snake output

---

### Task 1: Replace, verify, and commit the profile README

**Files:**

- Modify: `README.md:1`
- Reference: `docs/superpowers/specs/2026-07-24-github-profile-readme-design.md`
- Do not modify: `.github/workflows/snake.yml`
- Do not stage: `.superpowers/`

**Step 1: Confirm the approved baseline**

Run:

```powershell
git status --short
git log -2 --oneline
Get-Content -Raw -Encoding utf8 "docs/superpowers/specs/2026-07-24-github-profile-readme-design.md"
```

Expected:

- Commit `0e7811a docs: add GitHub profile redesign spec` is present.
- The specification says `Bandung, Indonesia`, English, open to freelance and
  contract work, and identifies the three approved projects.
- `.superpowers/` may be untracked, but no unrelated tracked file is modified.

Stop and resolve unexpected tracked changes before continuing. Do not discard
user work.

**Step 2: Replace `README.md` with the approved content**

Use `apply_patch` to replace the entire existing README with:

```markdown
<h1 align="center">Hey, I'm Brian Sangapta 👋</h1>

<h3 align="center">Software Engineer building AI-powered products</h3>

<p align="center">
  I turn machine-learning ideas into useful products—combining
  <strong>Python</strong> for AI and backend systems with
  <strong>TypeScript</strong> and <strong>Next.js</strong> for thoughtful web
  experiences.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Bandung%2C%20Indonesia-181717?style=flat-square&logo=googlemaps&logoColor=white" alt="Location: Bandung, Indonesia" />
  <img src="https://img.shields.io/badge/Open%20to-Freelance%20%26%20Contract-238636?style=flat-square" alt="Open to freelance and contract work" />
</p>

<p align="center">
  <a href="https://linkedin.com/in/briansangapta">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="Connect with Brian on LinkedIn" />
  </a>
  <a href="mailto:z0zerooooo@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email Brian" />
  </a>
</p>

## What I'm focused on

- 🧠 **Applied AI** — NLP, Transformer evaluation, and useful model-driven workflows.
- ⚙️ **AI Systems** — Reliable APIs, tooling, guardrails, and product integration.
- ✨ **Product Delivery** — Moving from a working prototype to a clear, usable web experience.

## Selected work

| Project | What it demonstrates | Built with |
| --- | --- | --- |
| [**UML Diagram Generator**](https://github.com/z0zero/uml-diagram-generator) | Turns natural-language prompts into six types of interactive UML diagrams. | `Gemini` `React 19` `TypeScript` `React Flow` |
| [**Job Scam Detection**](https://github.com/z0zero/job-scam-BERT-ALBERT-RoBERTa) | Compares BERT, ALBERT, and RoBERTa on 17,880 job listings and serves the selected model through Streamlit. | `Python` `Transformers` `NLP` `Streamlit` |
| [**NeetCode Subtitle Translator**](https://github.com/z0zero/NeetCode-Subtitle-Translator) | Translates English subtitles to Indonesian with batch pre-translation, smart caching, and API fallback. | `Chrome Extension` `JavaScript` `Google Translate` `DeepL` |

## Core toolkit

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=000000" alt="Hugging Face Transformers" />
  <img src="https://img.shields.io/badge/Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white" alt="Google Gemini" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

## GitHub activity

<p align="center">
  <a href="https://github.com/z0zero">
    <img height="165" src="https://github-readme-stats.vercel.app/api?username=z0zero&show_icons=true&hide_border=true&theme=transparent&rank_icon=github" alt="Brian's GitHub profile statistics" />
  </a>
  <a href="https://github.com/z0zero">
    <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs?username=z0zero&layout=compact&langs_count=8&hide_border=true&theme=transparent" alt="Most used languages in Brian's public repositories" />
  </a>
</p>

<p align="center"><em>Fueled by curiosity, shipped with coffee ☕</em></p>

<p align="center">
  <img src="https://raw.githubusercontent.com/z0zero/z0zero/output/snake.svg" alt="Brian's GitHub contribution graph animation" />
</p>
```

Do not add profile trophies, streak cards, a profile-view counter, the old
technology wall, or extra social links.

**Step 3: Run the content-contract check**

Run:

```powershell
$profileReadme = Get-Content -Raw -Encoding utf8 "README.md"
$requiredText = @(
  "Software Engineer building AI-powered products",
  "Bandung%2C%20Indonesia",
  "Open%20to-Freelance%20%26%20Contract",
  "mailto:z0zerooooo@gmail.com",
  "z0zero/uml-diagram-generator",
  "z0zero/job-scam-BERT-ALBERT-RoBERTa",
  "z0zero/NeetCode-Subtitle-Translator",
  "Fueled by curiosity, shipped with coffee",
  "z0zero/z0zero/output/snake.svg"
)
$forbiddenText = @(
  "github-profile-trophy",
  "github-readme-streak-stats",
  "komarev.com/ghpvc",
  "A passionate Software Engineer from Indonesia"
)
foreach ($requiredItem in $requiredText) {
  if (-not $profileReadme.Contains($requiredItem)) {
    throw "Missing required README content: $requiredItem"
  }
}
foreach ($forbiddenItem in $forbiddenText) {
  if ($profileReadme.Contains($forbiddenItem)) {
    throw "Obsolete README content remains: $forbiddenItem"
  }
}
Write-Output "README content checks passed"
```

Expected: `README content checks passed`.

**Step 4: Check whitespace and the source diff**

Run:

```powershell
git diff --check -- README.md
git diff -- README.md
```

Expected:

- `git diff --check` exits successfully with no output.
- The diff is a complete replacement of the old generator content.
- Only approved wording, projects, toolkit badges, two stats cards, and the
  existing snake asset remain.

**Step 5: Validate GitHub-Flavored Markdown rendering**

Run:

```powershell
$renderedProfile = gh api markdown -F text=@README.md -f mode=gfm -f context=z0zero/z0zero
if ($LASTEXITCODE -ne 0) {
  throw "GitHub Markdown rendering failed"
}
$renderMarkers = @(
  "<h1",
  "Brian Sangapta",
  "Bandung",
  "uml-diagram-generator",
  "job-scam-BERT-ALBERT-RoBERTa",
  "NeetCode-Subtitle-Translator",
  "snake.svg"
)
foreach ($renderMarker in $renderMarkers) {
  if (-not $renderedProfile.Contains($renderMarker)) {
    throw "Rendered profile is missing: $renderMarker"
  }
}
Write-Output "GitHub Markdown rendering checks passed"
```

Expected: `GitHub Markdown rendering checks passed`.

Inspect the returned structure for these responsive-design constraints:

- No custom CSS or unsupported styling appears.
- The hero uses centered paragraphs that can wrap naturally.
- Project content is a standard Markdown table and may scroll on narrow screens
  without hiding information.
- Stats images set height only, allowing the pair to wrap rather than forcing a
  fixed combined width.
- All image elements include useful alt text.

**Step 6: Validate external image assets**

Run:

```powershell
$profileAssetUrls = @(
  "https://img.shields.io/badge/Bandung%2C%20Indonesia-181717?style=flat-square&logo=googlemaps&logoColor=white",
  "https://img.shields.io/badge/Open%20to-Freelance%20%26%20Contract-238636?style=flat-square",
  "https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white",
  "https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white",
  "https://github-readme-stats.vercel.app/api?username=z0zero&show_icons=true&hide_border=true&theme=transparent&rank_icon=github",
  "https://github-readme-stats.vercel.app/api/top-langs?username=z0zero&layout=compact&langs_count=8&hide_border=true&theme=transparent",
  "https://raw.githubusercontent.com/z0zero/z0zero/output/snake.svg"
)
foreach ($profileAssetUrl in $profileAssetUrls) {
  curl.exe --location --fail --silent --show-error --max-time 30 --output NUL $profileAssetUrl
  if ($LASTEXITCODE -ne 0) {
    throw "Profile asset failed: $profileAssetUrl"
  }
}
Write-Output "External profile assets are reachable"
```

Expected: `External profile assets are reachable`.

If one external service is temporarily unavailable, retry once and record the
specific URL. Do not silently remove approved content or replace it with a new
provider without reviewing the trade-off.

**Step 7: Confirm repository scope before staging**

Run:

```powershell
git status --short
git diff --name-only
```

Expected:

- `README.md` is the only modified tracked file.
- `.superpowers/` remains untracked and is not part of the change.
- `.github/workflows/snake.yml` is unchanged.

**Step 8: Stage only the README and verify the index**

Run:

```powershell
git add -- README.md
git diff --cached --name-only
git diff --cached --check
```

Expected:

- The cached file list contains only `README.md`.
- The cached whitespace check succeeds with no output.

**Step 9: Commit the implementation**

Run:

```powershell
git commit -m "feat: refresh GitHub profile README"
```

Expected: one commit that changes only `README.md`.

**Step 10: Verify the completed commit**

Run:

```powershell
git show --check --stat --oneline HEAD
git show --name-status --format="" HEAD
git status --short
```

Expected:

- `git show --check` reports no whitespace errors.
- The commit file list contains only `README.md`.
- `.superpowers/` may remain as temporary untracked design tooling; it is not
  included in the commit.
