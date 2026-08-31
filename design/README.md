# Design system

Three files. `tokens.css` holds every value; `components.css` holds every rule and reads
only from tokens; `reference.html` shows all of it with placeholder text.

Load order in `_layouts/default.html`, replacing the inline `<style>` block:

```html
<link rel="stylesheet" href="/design/tokens.css">
<link rel="stylesheet" href="/design/components.css">
```

No new markup is required. Every page renders from Markdown as it does today.

## What changed and why

The brief named five causes. The fixes:

1. **Accent inflation.** The green sat on `h1`, on `.card`, on `.banner` and on the
   inline styled emphasis boxes at once, so nothing outranked anything. The green is now
   reserved for links, for the rule above `h1`, for the rule under a table head, for
   ordered list numerals, and for exactly one component: `.callout`. Cards went quiet.
2. **Tables.** Rebuilt as editorial tables: no outer box, horizontal hairlines only, an
   accent rule under an uppercase head, roomy rows, first column set in medium weight.
3. **Figures.** Images now get a mat, a hairline and a radius, so a transparent SVG reads
   as a figure. `.caption` is a real caption with a rule on its left edge.
4. **Hero.** Left aligned on the same axis as the body text, with an accent rule along its
   top edge and the lede set at 28px. It no longer centres one sentence in a dark box.
5. **Type scale.** A 1.22 scale from 13px to 46px, plus `h2` opening each section with a
   hairline. Long argument pages now have visible structure.

## Tokens

`tokens.css` is the only file with literal values. Colour, type scale, spacing scale
(4px base), structure, plus two overrides in one place each: a narrow screen block that
steps the scale down, and a print block that turns filled bands into ink on paper.

The seven original tokens are unchanged in name and value. Added colours are neutrals
derived from them plus two lifted variants for text on the dark background
(`--accent-on-dark`, `--fg-inverse-muted`), both of which meet WCAG AA on `--nav-bg`.
No second hue was introduced: the site's problem is hierarchy, and another colour would
have made it worse.

## Components

**`nav`, `.nav-inner`, `.site-name`, `.nav-links`, `.active`**
The masthead. Eight links wrap at any width and stack below 600px. The active link is
marked by an accent underline, not a colour change.

**`.banner`**
The announcement strip above the page. Now a quiet dark band with the label in accent
green rather than a filled green band at 1.15rem. Two adjacent banners separate with a
hairline. No wrapper element is needed: the page column sits on the banner's own content
box, so the bare inline markup the layout already emits works as is.

**`.hero`**
Page opener, home page only. Takes an `h1` and one or two paragraphs. The first paragraph
is the lede at 28px; a second paragraph drops to body size automatically. Bleeds to the
container edges without extra markup.

**`.container`**
The page column, 52rem, gutters from `--gutter`. Unchanged in role.

**`h1` to `h4`, `p`, `strong`**
`h1` is dark with a short accent rule above it. The paragraph directly after `h1` is
styled as a lede automatically. `h2` opens a section with a hairline above it, suppressed
when it is the first element or follows the hero. `h3` and `h4` are subheads inside a
section.

**`ul`, `ol`, `li`**
Ordered lists get a hanging monospace numeral in accent green, which is what the numbered
argument on the home page needs. Unordered lists get a small square marker. Both nest.

**`blockquote`, `cite`**
Quoted external text: regulatory language, standards text, someone else's words. Grey
rule, muted type, no tint. It is not a highlight box. Use `.callout` for emphasis. An
optional `cite` renders as an attribution line.

**`table`, `thead`, `th`, `td`, `caption`, `.table-scroll`**
The workhorse. Kramdown pipe tables need no classes. The first column is treated as the
row label; links in it stay on one line above 600px. Add an optional `caption` for a table
title. Below 600px every table scrolls itself, so no wrapper is required for Markdown
generated tables. `.table-scroll` is only for hand written markup where you want a wide
table to scroll on desktop too.

**`img`, `.caption`, `figure`, `figcaption`**
Any image inside `.container` becomes a figure: white mat, hairline, padding. A following
`p.caption` tucks under it and is set as a caption. Native `figure` and `figcaption`
work identically if you ever hand write one.

**`code`, `pre`**
Inline code is a bordered chip; blocks are sunken with a grey rule on the left edge and
scroll horizontally. Nothing highlights syntax, by design: no JavaScript.

**`.card`, `.card-grid`**
Navigational blocks. White, hairline, a heavier top rule, heading in body colour, text one
step down. Deliberately quiet so the accent means something elsewhere. `.card-grid` is a
responsive auto fit grid with a 15rem minimum, so three cards become one column on a
phone.

**`.callout`** (new)
The one accent block on a page: this is the argument, or this is running today. Tinted
background, accent rule on the left edge, optional `h3` title. It replaces the inline
`style` attributes on the accent cards in the current home page markup, so delete those.
One per page, two at the outside. A third stops it meaning anything.

**`footer`, `.footer-inner`, `.footer-content`, `.footer-col`, `.footer-bottom`**
Three or more link columns, headings as small uppercase labels with a hairline under each.
Auto fit at an 11rem minimum.

**`hr`**
A section break with generous space. Rarely needed now that `h2` carries a rule.

## New class names

Two, both listed above: `.callout` and `.table-scroll`. Everything else styles bare
elements or class names already in the markup.

## Constraints held

No copy. No external requests: system font stack, no CDN, no icons, no JavaScript, so it
renders offline and on a conference network. No em dashes. Readable at 320px. Prints as
ink on paper with the nav and banners suppressed. Every text and background pair defined
here meets WCAG AA. No logo dependency: the masthead is a text wordmark and no layout
reserves space for a mark.

## Checking it

Open `reference.html` in a browser. Then print it, and then narrow the window to 320px.
All three should hold.
