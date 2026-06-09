# Presentation: Design Reference & Slide Summary

**File:** `presentation.html`
**Tool:** [Reveal.js 6.0.1](https://revealjs.com/)
**Theme:** Custom OSN Deep Navy — adapted from the Linear.app Deep Space aesthetic
**Total slides:** 18
**Talk:** Spec First, Agents Second: Engineering AI Systems with Discipline
**Speaker:** Justin Grammens · Lab651 & Recursive Awesome & Applied AI
**Event:** Open Source North 2026

---

## Source Material

The presentation was recreated from `slides/OSN_Spec_First_Agents_Second_FINAL.pdf` (18-page slide deck) using the Deep Space design system established in `C:\TFS\Github\hypothesis-project-xantari\presentation.html` as the style reference.

---

## How This Was Built

### Prompt Used

> *"Analyze this power point and recreate the presentation in pure HTML form using C:\TFS\Github\hypothesis-project-xantari\presentation.html and presentation.md for guidelines on a style format."*

### Source Files

| File | Role |
|---|---|
| `slides/OSN_Spec_First_Agents_Second_FINAL.pdf` | Original 18-slide PowerPoint exported to PDF — full content source |
| `C:\TFS\Github\hypothesis-project-xantari\presentation.html` | Style reference: Deep Space theme, CSS architecture, Reveal.js config, star-field JS |
| `C:\TFS\Github\hypothesis-project-xantari\presentation.md` | Design system documentation reference |

---

## OSN Deep Navy Design System

This presentation adapts the Deep Space design system to the navy/teal palette used in the original OSN slide deck.

### Color Palette

| Token | Hex / Value | Usage |
|---|---|---|
| `--ds-bg` | `#0A1929` | Page/slide background |
| `--ds-bg-header` | `#0D2137` | Slide header band |
| `--ds-surface` | `#0F2740` | Card surfaces |
| `--ds-surface2` | `#163352` | Elevated surfaces |
| `--ds-border` | `rgba(255,255,255,0.08)` | Subtle card borders |
| `--ds-border-teal` | `rgba(45,212,191,0.35)` | Teal-accented borders |
| `--ds-border-green` | `rgba(74,222,128,0.35)` | Green-accented borders |
| `--ds-border-red` | `rgba(239,68,68,0.35)` | Red/alert borders |
| `--ds-text` | `#E8F4FD` | Primary text |
| `--ds-text-muted` | `rgba(232,244,253,0.60)` | Secondary / body text |
| `--ds-text-dim` | `rgba(232,244,253,0.35)` | Tertiary / metadata text |
| `--ds-teal` | `#2DD4BF` | Primary accent (headers, pills, REQ stripes) |
| `--ds-cyan` | `#22D3EE` | Secondary accent |
| `--ds-green` | `#4ADE80` | Positive / success states |
| `--ds-red` | `#EF4444` | Alert / danger / negative stats |
| `--ds-orange` | `#F97316` | Warm accent (Recursive Awesome brand) |
| `--ds-yellow` | `#FBBF24` | Research / warning emphasis |

### Typography

- **Font families:** [Inter](https://rsms.me/inter/) (Google Fonts, weights 300–800) for all UI text; [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (weights 400–500) for code blocks, REQ IDs, agent commands, and file paths
- **Headings:** `font-weight: 800`, `letter-spacing: -0.03em`, `text-transform: none`
- **Body/muted:** `font-size: 0.78–0.92rem`, `line-height: 1.55–1.65`
- **Section eyebrow labels:** `0.68rem`, `letter-spacing: 0.12em`, `text-transform: uppercase`, teal color

---

## Key Design Components

### `.section-pill` / `.eyebrow`
Small all-caps spaced label above each slide's `h2`. The pill variant has a teal-tinted background badge. The eyebrow variant is plain teal text.

### `.ds-card`, `.ds-card-teal`, `.ds-card-green`, `.ds-card-red`
Glass-morphism cards with subtle `rgba` backgrounds and matching border colors. Used throughout for content panels.

### `.fw-card` (Framework Cards)
Three-column numbered cards (01 / 02 / 03) with a colored top accent bar (`::before` pseudo-element). Colors: teal / cyan / green respectively. Used on slides 8.

### `.agent-card` (Agent Grid)
2×2 grid of cards for the four SpecKit agents (slide 15). Each card has a colored top accent bar, a mono-font command name, description, prompt block, and output path.

### `.req-row` (Requirements Table)
Row-based layout for requirements (slide 11). Each row has a colored 4px left stripe indicating priority/category: teal (functional), cyan (state), red (safety), green (determinism).

### `.contrast-wrap` / `.contrast-panel` (Side-by-Side Contrast)
Two-column layout for the vibe coding vs. spec-driven comparison (slide 12). Bad panel: dark red tinted background with red top bar. Good panel: dark green tinted background with green top bar.

### `.state-flow` (State Machine)
Horizontal flexbox flow of colored state boxes connected by arrow dividers with timing labels below (slide 10).

### `.vmodel-box.design` / `.vmodel-box.verify` (V-Model)
Left-indented design artifacts (teal left border) mirrored by right-indented verification artifacts (green right border), meeting at an implementation box at the bottom center (slide 16).

### `.scenario-item` (Practical Path)
Three numbered scenarios (slide 17), each with a large accent number, a colored vertical stripe, and nested bullet sub-items.

### `.truth-item` (Three Truths)
Full-width numbered closing statements with thin number labels and large body text (slide 18).

### Star-field Canvas
Identical to the hypothesis-project reference. `#starfield` canvas sits `position: fixed; z-index: 0` behind all Reveal.js content. Three boolean flags control behavior:

| Flag | Default | Effect |
|---|---|---|
| `STARFIELD_ENABLED` | `true` | `false` = skip all canvas rendering |
| `ANIMATE_STARFIELD_DOTS` | `false` | `true` = stars drift at ±0.25 px/frame |
| `PULSE_STARFIELD_DOTS` | `true` | `true` = organic per-star flicker (lerp to random alpha) |

### Slide 3 Special Background
Slide 3 (the "2:47 AM" story slide) uses `data-background-color="#120404"` to override the default dark navy with a very dark red, and the heading band uses `background: #B91C1C` to produce the alert-red aesthetic from the original.

### Slide 9 Special Background
Slide 9 (Director/Contract/Executor Venn) uses a white background (`background: #fff`) with dark text to match the original PowerPoint's white Venn diagram slide, rendered entirely in CSS with two overlapping `border-radius: 50%` divs.

---

## Reveal.js Configuration

```js
Reveal.initialize({
  hash: true,
  slideNumber: 'c/t',
  transition: 'slide',
  transitionSpeed: 'fast',
  backgroundTransition: 'fade',
  center: false,
  margin: 0,
  width: 1280,
  height: 720,
  minScale: 0.2,
  maxScale: 2.0,
  plugins: [RevealNotes]
})
```

---

## Slide Index

| # | Section Label | Title |
|---|---|---|
| 1 | — | Spec First, Agents Second: Engineering AI Systems with Discipline |
| 2 | ABOUT THE SPEAKER | 25 Years. Regulated Systems. Real Codebases. |
| 3 | — | 2:47 AM. Room 412. Insulin overdue. |
| 4 | THE PROBLEM | AI Amplifies What's Already There |
| 5 | THE PRODUCTIVITY PARADOX | Speed Goes Up. Quality Quietly Collapses. |
| 6 | SECURITY IS A CONCERN | Vulnerabilities Double in One Year |
| 7 | THE SCALE OF THE PROBLEM | More Code Shipped This Quarter Than All of Last Year |
| 8 | THE FRAMEWORK | Three Practices. One Disciplined Engineering Model. |
| 9 | THE FRAMEWORK | Director, Contract, Executor. |
| 10 | DEMO SYSTEM | Medication Dose Alert Monitor (MDAM) |
| 11 | STEP 1: REQUIREMENTS | Spec-First: Making Intent Explicit |
| 12 | THE CORE CONTRAST | Same AI. Completely Different Engineering. |
| 13 | THE ARGUMENT | The Industry Is Independently Arriving at the Same Answer |
| 14 | THE TOOL | GitHub SpecKit: Structure That AI Can Actually Use |
| 15 | BEFORE THE DEMO | This Spec Was Built With Four SpecKit Agents |
| 16 | THE V-MODEL | SpecKit Maps Directly to the V-Model |
| 17 | PRACTICAL PATH | Starting Monday: Three Scenarios. |
| 18 | — | Three Truths. (Closing) |

---

## Key Data Points Preserved

### Slide 4 — The Problem
- Source: CodeRabbit, State of AI vs. Human Code Generation Report (Dec 2025)
- 470 open-source pull requests analyzed (320 AI-coauthored, 150 human-only)
- **+20%** PRs per developer year over year
- **1.7×** issues per AI-authored pull request (10.83 vs. 6.45 for human PRs)
- AI code: 2.25× more likely to have logic errors, ~2× more security issues

### Slide 5 — The Productivity Paradox
- Source: GitClear, "AI Copilot Code Quality: 2025 Research" — 211M lines, Jan 2020 – Dec 2024
- Refactoring share: **−60%** (25% → under 10%)
- Duplicated code blocks: **8×** rise (8.3% → 12.3%)
- Code churn: **2×** increase (3.1% → 5.7%+)

### Slide 6 — Security Is A Concern
- Source: Apiiro Fortune 50 Enterprise Study, Dec 2024 – Jun 2025
- Monthly security findings: **10×** increase (baseline → 10,000+/month in 6 months)
- Privilege-escalation paths: **+322%**
- Architectural design flaws: **+153%**
- Vulnerabilities per 1,000 LOC: **2.74×** (Veracode, 100+ LLMs, 45% security failure rate)
- Repos with exposed secrets: **+40%**

### Slide 7 — The Scale of the Problem
- Source: GitHub COO Kyle Daigle, 2026; SemiAnalysis; Tomasz Tunguz
- GitHub commits: **14×** more than all of 2025 (on pace for 14B in 2026)
- Claude Code commit growth: **25×** in 6 months (100K → 2.5M/week)
- AI-agent PRs: **4×** since Sept '25 (4M → 17M+/month)
- Claude Code share of public commits: **~4%** (projected 20%+ by year-end)
- CI/CD compute: **2.1B** minutes in a single week (up from 500M in 2023)

### Slide 11 — Requirements (MDAM Feature 001)
Requirements shown: REQ-001, REQ-003, REQ-004, REQ-006, REQ-009, REQ-010

---

## Notes on Omitted Elements

The following visual elements from the original PowerPoint could not be faithfully reproduced in pure HTML/CSS without external image assets and were replaced with equivalent text/code representations:

- **Slide 2:** Lab651, Recursive Awesome, and Applied AI logos replaced with styled text equivalents
- **Slide 9:** Venn diagram reproduced in CSS using overlapping `border-radius: 50%` divs on a white background
- **Slide 16:** V-Model diagram reproduced with indented card layout rather than diagonal SVG lines
- **Slide 18:** QR code replaced with plain contact information text
