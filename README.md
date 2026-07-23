# html-summary

**A design system, as an agent skill, for standalone HTML summaries.**

Agents are good at producing the content of a report and bad at deciding how it
should look. Left alone they default to the same cream-and-serif landing page
every time. This skill replaces that default with one house style: monospace,
monochrome, sharp hairline borders, flat, dense, functional.

The deliverable is always a single `.html` file with everything inline. No build
step, no CDN, no folder of assets. A colleague clicks it and reads it.

Skills follow the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### html-summary

Design system for standalone HTML summaries, reports, comparison pages, and
shareable single-file docs. Covers the visual language, the copy rules, and a
working `template.html` with every token and component already wired for light
and dark.

**Use when:**

- "Make this a nice HTML page"
- "Write me an HTML summary/report/recap"
- "Give me a self-contained `.html` I can send to a coworker"
- Building a comparison or bake-off page
- Writing up a status or results page as a web page

**Covered:**

- One file, zero external assets (CSS, JS, images as `data:` URIs)
- Length discipline — a summary is one to two screens, not a document
- One file per step, so an earlier snapshot is never overwritten
- Copy and voice — executive summaries as political documents, and a list of
  the AI tells to cut ("não foi X, foi Y", em-dash drama, tricolon cadence)
- Hard bans — cream backgrounds, sans/serif body, rounded corners, shadows,
  accent colors, tracked caps, decorative status dots
- Tokens, type scale, layout, bento grids, inverted emphasis blocks
- Stacked opacity-ramped bars and hover disclosures
- Hand-coded inline SVG icons
- A hand-off checklist

## Installation

```bash
npx skills add yeksax/html-summary
```

Manual, for Claude Code:

```bash
cp -r skills/html-summary ~/.claude/skills/
```

Or without installing anything:

```bash
npx skills use yeksax/html-summary@html-summary | claude
```

## Usage

The skill is picked up on its own once installed — the agent invokes it when it
recognizes a summary-shaped request. You can also name it directly:

```
Turn this migration plan into an HTML summary I can send to the team
```

```
Read the audit output and give me a one-page comparison of the three options
```

## Skill Structure

```
skills/
  html-summary/
    SKILL.md          # the design system
    template.html     # working starter with every token and component
```

## Lattice

This repository holds the standalone design system, which depends on nothing.

[Lattice](https://github.com/yeksax/lattice) is the local-first app that gives
those files a home: a searchable library over `~/.summaries`, a dashboard, live
reload while an agent writes, one-command public sharing, and polls that collect
reader votes. It ships its own copy of this skill, extended with the theme
configuration and the interactive components that only work when a summary is
served through the daemon:

```bash
lattice skills install
```

Nothing here depends on any of that.

## License

[MIT](LICENSE)
