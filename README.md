# border-radius-killed-my-parents

> AI keeps putting `border-radius: 9999px` on everything.  
> I decided to fight back.

`border-radius-killed-my-parents` is a design skill for fixing the typical visual habits of AI-generated frontend code.

It detects and fixes patterns like:

- too much `border-radius`
- pill-shaped badges everywhere
- cards inside cards inside cards
- vague landing-page copy
- unnecessary technology-name flexing
- emoji-driven decoration
- Japanese font mistakes
- UI that looks polished but says nothing

This is not a war against rounded corners.

This is a war against **meaningless roundness**.

## Why?

AI-generated UI often looks "modern" at first glance.

Then you look closer and realize everything is:

- softly rounded
- vaguely gradient
- wrapped in pills
- separated by too many cards
- filled with words like "seamless", "powerful", and "intuitive"

It is not design.

It is frontend-shaped foam.

This skill exists to remove that foam.

## Philosophy

A rectangle does not need therapy.

A badge does not make text more meaningful.

A card does not become more useful by becoming rounder.

A product description should explain what the product does, not what stack it was built with.

Good UI does not have to scream:
"Look, I was made by an AI that has seen 40,000 SaaS landing pages."

## What it does

The skill reviews a project and looks for AI-ish design patterns.

It does not blindly delete every rounded corner.

Instead, it tries to identify design smells by category, then fixes them in a more restrained direction.

Examples:

```css
/* before */
border-radius: 24px;

/* after */
border-radius: 10px;
```

```html
<!-- before -->
<span class="badge badge-primary">TypeScript</span>
<span class="badge badge-primary">Cloudflare Workers</span>
<span class="badge badge-primary">PostgreSQL</span>

<!-- after -->
(deleted)
```

```html
<!-- before -->
<p>Built with Hono + Cloudflare Workers + D1. Fully serverless architecture with edge-first design.</p>

<!-- after -->
<p>An SNS I designed and run myself. Timeline, follows, notifications — all the basics. Live in production.</p>
```

## Patterns

| | Pattern | Auto-fix |
|---|---|---|
| A | Excessive border-radius | ✅ |
| B | Pill badges | ✅ |
| C | LP-style layout (everything in one scroll) | Propose only |
| D | Excessive accent color | Propose only |
| E | Missing page responsibility | Propose only |
| F | Prose-ified copy | Propose only |
| G | Missing visuals per page | Propose only |
| H | Fill-based separation (background + border redundancy) | Propose only |
| I | Japanese site font mistakes | ✅ |
| J | Tap highlight not removed | ✅ |
| K | Subpage scroll overload | ✅ + Propose |
| L | Describing with tech names (prose or tag lists) | ✅ (tag lists) + Propose (prose) |
| M | Emoji → Lucide SVG icon replacement | ✅ |

## Install

Copy `SKILL.md` into `~/.claude/skills/border-radius-killed-my-parents/SKILL.md`.

Then in Claude Code:

```
/border-radius-killed-my-parents [target directory]
```

## Note

This skill was built for Japanese-language websites.  
Pattern I (font design) is Japanese-specific.  
Example copy in patterns F and L is written in Japanese.  
All other patterns apply to any language site.
