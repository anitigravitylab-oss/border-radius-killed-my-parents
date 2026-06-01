---
name: border-radius-killed-my-parents
description: Detects and fixes typical AI-generated design anti-patterns (excessive border-radius, pill badges, LP-style layout, prose-ified copy, missing visuals, fill-based separation, font mistakes, tech-name descriptions, emoji) from a project, category by category. Invoke with /border-radius-killed-my-parents.
user-invocable: true
allowed-tools:
  - Bash
  - Read
  - Edit
  - AskUserQuestion
---

# /border-radius-killed-my-parents — AI Design Anti-Pattern Fixer

Arguments: `[target directory]` (defaults to current directory)

## Overview

Detects "looks okay but feels clunky" patterns that AI tends to generate, and fixes them category by category with Y/N confirmation.

## Patterns

| Category | Detection condition | Fix policy |
|----------|---------------------|------------|
| **A: Excessive border-radius** | Smaller corner radius looks more honest. Any element with an oversized `border-radius`. Threshold guideline: `12px` or more (e.g. `border-radius: 24px` / Tailwind `rounded-xl`+ / `9999px`) | Normalize to `10px`. Exception: skip `border-radius: 50%` circular elements |
| **B: Pill badges** | Don't wrap information in decorative badge/tag elements. If it can be written as text, write it as text. Detect label elements that are small, have large border-radius (guideline: `20px`+), and are pill-shaped. Class name is irrelevant. | Delete badge elements from HTML. Also delete parent elements that become empty. Delete CSS badge definitions. |
| **C: LP-style layout** | One page, one responsibility. Don't stack multiple concerns in a single scroll. Detect when a single page has 3+ `<section>` elements, or independent concerns are crammed into one scroll. Section names are irrelevant. | Cannot auto-fix. Propose splitting into separate pages with navigation transitions. |
| **D: Excessive accent color** | Don't use chromatic colors without intent. White, black, and grey are enough for most UIs. Detect chromatic colors (any hue other than grey/black/white) used in text, backgrounds, borders, or gradients. Color code format is irrelevant. | Cannot auto-fix. Propose migration to **white base + black accent** (background: white, text: black, accent: black or dark grey). |
| **E: Missing page responsibility** | Each page must fulfill its information responsibility. Detect when the top page is only an intro/nav with the most important info buried deeper, or when a subpage's purpose isn't immediately clear. | Cannot auto-fix. Propose: (1) put a summary of the most important info on the top page (2) one page = one responsibility (3) make each page's purpose clear at a glance (4) consolidate navigation into header/sidebar etc. |
| **F: Prose-ified copy** | Top page copy, subpage headings, and section titles read like descriptions ("I specialize in X and handle Y"). Every page just lists features/tech/achievements without making the user feel anything. | Cannot auto-fix. Propose rewriting as plain explanation of "what changes and how." Check not just the top copy but also subpage headings, descriptions, and CTA text. Present suggestions based on the principles in Step F. |
| **G: Missing visuals per page** | Each page has only text and navigation, with no real artifact (product screenshot, work sample, diagram, comparison) backing up the page's purpose. | Cannot auto-fix. Propose what's missing based on the page's purpose. For the top page, check for: (1) name/service name (2) one-line copy (3) real visual (4) call to action. Don't add hover animations or excessive motion. |
| **H: Fill-based separation** | If border or whitespace can do the job, don't fill with background color. Detect any element that already has a `border` but is filled with a non-pure-white background (including light grey). Class name is irrelevant. | Cannot auto-fix. Propose switching to border-only separation. Replace CTAs with text links (main CTA: bold + underline, sub CTA: light + grey + underline). Add more whitespace where decoration was removed. |
| **I: Japanese site font mistakes** | Japanese site with only Latin fonts specified (`"Inter", sans-serif` etc.) / strong negative `letter-spacing` on body text (`-0.03em` or less) / `line-height: 1.4` or less / `font-weight: 300` body text / too many Google Fonts weights (4+) | Fix as follows: add Japanese fonts to `font-family` (prefer system fonts) / body `line-height: 1.75` / body `letter-spacing: 0–0.02em` / headings only `letter-spacing: -0.02–-0.03em` / body `font-weight: 400` / Google Fonts: 3 weights only (`400;500;700`) |
| **J: Tap highlight not removed** | Blue highlight appears when tapping links/buttons on mobile (`-webkit-tap-highlight-color` not set) | Add `a, button { -webkit-tap-highlight-color: transparent; }` globally |
| **K: Subpage scroll overload** | Subpages (non-top) require scrolling due to: (1) excessive padding (2) lack of information curation (3) card grid inefficient for content volume | (1) Auto-fix: compress section padding ≥ `80px` to `40px` (guideline, not absolute), remove `min-height: 100svh` from subpages. (2)(3) Propose only: suggest trimming to 3–5 items + "see all" link for pages with 5+ items (guideline). Propose list layout if it fits better than card grid. Ask: "Is the scroll on this page justified by the content?" |
| **L: Describing with tech names** | Don't explain using technology names, implementation names, or tool names. Meaningless to those who don't know them; redundant to those who do. Format doesn't matter — writing them in prose ("Built with Hono + Workers") or listing as UI parts (tag list, badge group, inline list) is the same problem. Read the HTML and judge by content. | Fix method varies by format. (1) Prose text: cannot auto-fix. Propose rewriting with the user or product as subject — "what it does / what changes when you use it." Present suggestions based on the principles and examples in Step L. (2) UI parts (tag lists, badge groups, etc.): auto-fix. Delete the UI parts from HTML. Delete empty parent elements. Delete corresponding CSS definitions. |
| **M: Emoji usage** | Don't use emoji in UI. Icon libraries can replace them. Read the file to check if emoji are present. Exclude content inside `<code>` / `<pre>` / `<meta>` tags. | Auto-fix. Replace each emoji with a Lucide icon SVG (MIT/ISC license, free for commercial use) that matches the emoji's meaning and context. Fetch SVG from `https://unpkg.com/lucide-static@latest/icons/{name}.svg`. When embedding inline, add `width="1em" height="1em" style="display:inline;vertical-align:-0.125em"` to keep it in the text flow. |

## Steps

### 1. Confirm target directory

Use the argument if provided, otherwise use current directory.

```bash
TARGET=${1:-.}
```

### 2. Collect target files

Recursively scan for: `.css` / `.scss` / `.sass` / `.less` / `.html` / `.jsx` / `.tsx` / `.vue` / `.svelte`

```bash
find "$TARGET" -type f \( \
  -name "*.css" -o -name "*.scss" -o -name "*.sass" -o -name "*.less" \
  -o -name "*.html" -o -name "*.jsx" -o -name "*.tsx" \
  -o -name "*.vue" -o -name "*.svelte" \
) \
  ! -path "*/node_modules/*" \
  ! -path "*/.git/*" \
  ! -path "*/dist/*" \
  ! -path "*/build/*"
```

### 3. Detect and tally by category

Detection method differs by category.

**grep-detectable (A/I/J):**
Extract matches with grep and record:
- Number of files matched
- Total number of lines matched
- Up to 3 representative lines as preview

Example output:
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[A] Excessive border-radius  — 5 files / 18 occurrences
  src/components/Button.css:12    border-radius: 9999px
  src/components/Card.tsx:34      className="rounded-full"
  src/styles/global.css:88        border-radius: 50px
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Read-and-judge (B/C/D/E/F/G/H/K/L/M):**
Read files with the Read tool and confirm content. grep cannot make these judgments — always read the full file.

Note for B detection: when you find a pill-shaped element, check whether the content is a tech name / tool name / language name. If so, report it as L, not B (content takes priority).

### 4. Confirm per category with AskUserQuestion

Only ask about detected categories (skip categories with 0 hits).

For each category, offer:
- `Fix` — auto-fixable ones (A/B/I/J/K partial/L partial/M): apply code changes. Non-auto-fixable ones (C/D/E/F/G/H/L prose): present concrete improvement suggestions. K and L do both depending on the case.
- `Skip` — skip this category

AskUserQuestion accepts a maximum of 4 questions per call. If 5 or more categories are detected, split into batches of 4 and call multiple times.

### 5. Apply fixes for chosen categories

#### A: Excessive border-radius
- Replace oversized `border-radius` values (guideline: `12px`+) with `10px`
- Tailwind: replace `rounded-xl`+ with `rounded-lg` (approx. 8px)
- Exception: skip `border-radius: 50%` circular icons/avatars

#### B: Pill badges
- Delete pill-shaped label elements from HTML (judge by shape, not class name)
- Also delete parent elements that become empty
- Delete CSS badge style definitions
- **Note:** if content is a tech/tool/language name, handle as L, not B (content takes priority)

#### C: LP-style layout (warn only, no auto-fix)
- Detect when a single page has 3+ `<section>` elements or multiple independent concerns in one scroll (section names irrelevant)
- Propose to the user:
  - Make the top page navigation-only
  - Split each section into a separate page (separate HTML or route)
  - Design with page transitions, not scrolling (one screen = one responsibility)

#### D: Excessive accent color (warn only, no auto-fix)
- List all locations where chromatic colors (non-grey/black/white) are used and present to user
- Elements with a border AND a chromatic background: handle as H (H takes priority)
- Propose:
  - Background: white (`#ffffff`)
  - Text: black (approx. `#111111`)
  - Accent: black or dark grey
  - Border: approx. `rgba(0,0,0,0.1)`
  - Remove gradients and color shadows

#### E: Missing page responsibility (warn only, no auto-fix)
- Read the HTML structure of each page and check whether it fulfills its information responsibility
- Propose:
  - Put a summary of the most important info on the top page (who/what it does)
  - One page = one responsibility
  - Make each page's purpose clear at a glance
  - Consolidate navigation into header/sidebar etc. (to match the site's structure)

#### F: Prose-ified copy (warn only, no auto-fix)

- If text contains tech/tool names, handle as L, not F (L takes priority)
- F applies to text that reads like a description ("I specialize in X and handle Y") without tech names

The following principles and examples are for reference only — do not copy verbatim. Read the site's content, target audience, and tone, then come up with multiple copy suggestions specific to that site.

**Principle: explain plainly what changes and how. Don't write catchphrases.**
- Top page copy should be short, but a complete sentence with subject and predicate — not a fragment like "Into something that works."
- Headings and subtitles should communicate in one line what the page is for
- CTA text should make clear what happens ("See my work" beats "Learn more")

**Examples (reference — always write in the site's own words):**
- Portfolio top: "I design and operate web services solo, from concept to production."
- Portfolio top: "An indie developer who keeps shipping things: SNS, tools, bots."
- Service: "Manage your team's schedule in one place."
- Tool: "Paste a URL and get the key points extracted."

#### G: Missing visuals per page (warn only, no auto-fix)
- Check whether each page has only text and navigation
- For the top page, check for these 4 elements and flag what's missing: (1) name/service name (2) one-line copy (3) real visual (4) call to action
- For subpages, check whether real artifacts (product screenshots, work samples, diagrams, comparisons) are present
- When proposing implementations, explicitly note: no hover animations or excessive motion

#### H: Fill-based separation (warn only, no auto-fix)
- List all elements with a border that have a non-pure-white background and present to user
- Propose:
  - Change background to white, use border alone for separation
  - Replace CTAs with text links (main CTA: bold + underline, sub CTA: light + grey + underline)
  - Add more whitespace where decoration was removed

#### I: Japanese font mistakes
- Add Japanese fonts to `font-family`: `system-ui, -apple-system, BlinkMacSystemFont, 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Yu Gothic', 'YuGothic', 'Meiryo', sans-serif`
- Body `line-height` ≤ `1.4` → replace with `1.75`
- Body `letter-spacing` ≤ `-0.03em` → relax to `-0.02em` (headings only allowed, skip body)
- `font-weight: 300` → replace with `font-weight: 400`
- Remove `300` / `600` from Google Fonts weight list, keep only `400;500;700`

#### J: Tap highlight not removed
- Add the following to the global CSS reset:
  ```css
  a, button { -webkit-tap-highlight-color: transparent; }
  ```

#### K: Subpage scroll overload

**Auto-fix:**
- Compress section `padding-top` / `padding-bottom` ≥ `80px` to `40px` (guideline, not absolute)
- Remove `min-height: 100svh` / `min-height: 100vh` from subpage sections

**Propose only:**
- For pages with many items (guideline: 5+), propose trimming and moving the rest to a separate page (guideline, not absolute)
- If a list layout would fit more content in one screen than a card grid, propose the layout change
- Ask the user: "Is the scroll on this page justified by the content?"

#### L: Describing with tech names

Read the HTML to confirm content, then respond based on format:

**(1) Prose text (warn only, no auto-fix)**

The following principles and examples are for reference only — do not copy verbatim. Read the site/product content and target audience, then come up with multiple description suggestions specific to that product.

Principles:
- Make the user or the product itself the subject
- Write "what it does / what changes when you use it" — not "what it was built with"
- Don't use tech names, implementation names, or architecture terms (React, API, DB, from scratch, modular, etc.)
- Aim for 2–3 sentences. Not a catchphrase, not a spec sheet.

Examples (by site type — do not copy):

*Portfolio — project card*
- "An SNS I designed and operate myself. Has all the basics: timeline, follows, notifications. Live in production."
- "An app for recording expenses by voice or text. You can just type something like 'convenience store, $5'."
- "A temporary image sharing service. Share the URL and it's viewable; auto-deleted after 48 hours."
- "A Q&A service focused on a specific topic. Post a question and answers come in from people interested in the same area."
- "A task management tool that runs in the browser. Manage projects in board format. No sign-up needed to get started."

*SaaS / Tool*
- "Manage posts to multiple SNS in one place. Schedule posts, save drafts, and review post history."
- "An app that auto-tallies your monthly income and expenses. Connect your bank account and see spending by category."
- "A tool that extracts the key points from any page — just paste the URL. Saves time before reading long articles or specs."
- "Create a form, share the URL, and start collecting survey responses. Results are tallied in real time as a chart."

*App (mobile)*
- "An app for recording how you feel in one sentence a day. Look back and see how your mood changed over time."
- "An app for tracking books you've read. Add a quick note and the date you finished. Browse your shelf later."
- "A habit tracking app. Register what you want to keep doing daily, and watch the days fill in as you complete them."

*SNS / Community*
- "A photo-only SNS. No text posts; one photo per day. Your timeline shows only photos from people you follow."
- "A community for sharing book reviews. See what others thought of the same book and swap recommendations."
- "An anonymous message board for posting worries. React with 'same' to posts you relate to. Replies are also anonymous."

*Service / Company*
- "A hiring support service for small businesses. We handle the paperwork: job listings, applicant management, all of it."
- "A contract template service for freelancers. Choose a template for your industry, fill in the details, and it's ready to use."
- "An end-to-end accounting service. Monthly bookkeeping, tax return preparation, and tax consultation — all in one package."

**(2) UI parts (tag lists, badge groups, inline lists, etc.) — auto-fix**
- Delete the UI parts listing tech/tool/language names from HTML (class name and placement are irrelevant — judge by content)
- Delete parent elements that become empty
- Delete corresponding CSS style definitions

#### M: Emoji usage

1. Read files with the Read tool and check whether emoji are present (exclude content inside `<code>` / `<pre>` / `<meta>`)
2. For each emoji, read its meaning and context to determine the corresponding Lucide icon name
3. Fetch the SVG: `curl -s https://unpkg.com/lucide-static@latest/icons/{name}.svg`
4. Add `width="1em" height="1em" style="display:inline;vertical-align:-0.125em"` to the `<svg>` tag and embed inline
5. Replace the original emoji
6. If the icon name is hard to determine, present `https://lucide.dev/icons` to the user and let them choose

### 6. Cycle completion report and transition to next cycle

**[Continuation condition]** This skill must not terminate until at least 10 cycles are complete.
At the end of each cycle, output the following without fail:

```
Cycle N/10 complete. Starting next cycle.
```

Do not report completion to the user until cycle 10 is done. Even if you judge that "there's nothing left to fix" or "no issues found," proceed to the next cycle. Each cycle restarts from Step 2 (file collection). Always re-scan files after modifications.

After cycle 10 is complete, output:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Done (10 cycles complete)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[A] border-radius       ✅ N fixes
[B] pill badges         ✅ N fixes
...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

List any remaining issues or items requiring manual attention at the end.

## Notes

- Exclude `node_modules` / `dist` / `build` / `.git`
- Do not modify generated files from design libraries (shadcn, daisyUI, etc.) — confirm and exclude `components/ui/` etc.
- Before making changes, check whether git is tracking the files; warn the user if not
