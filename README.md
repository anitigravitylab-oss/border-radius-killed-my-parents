# border-radius-killed-my-parents

A design skill for fixing AI-generated web UI — a Claude Code skill that detects and fixes the "looks okay but feels clunky" patterns that AI tends to produce.

## Install

Copy `SKILL.md` into `~/.claude/skills/border-radius-killed-my-parents/SKILL.md`.

Then invoke with:

```
/border-radius-killed-my-parents [target directory]
```

## What it fixes

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

## Note on language

This skill was built primarily for Japanese-language websites. Pattern I (font design) is Japanese-specific. The example copy in patterns F and L is written in Japanese. All other patterns apply to any language site.
