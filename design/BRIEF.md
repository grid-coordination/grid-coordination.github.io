# Design brief: grid-coordination.energy

Paste this into the Claude Design chat. It is deliberately narrow.

## What this site is

An independent policy-and-engineering site arguing one thesis to a serious audience: California
regulators, standards bodies, and utility engineers. It is not a product site and has nothing to
sell. Credibility matters more than polish; it should read as considered, not marketed.

Static Jekyll, built by GitHub Pages from Markdown. **No build step, no bundler, no framework, no
JavaScript.** The entire stylesheet is one inline `<style>` block in `_layouts/default.html`.

## Deliver a renderer, not a rendering

Return **four files**, nothing else:

| File | Contents |
| --- | --- |
| `design/tokens.css` | CSS custom properties on `:root`. Derived from the existing seven tokens, extended where genuinely needed (spacing scale, type scale, a second accent if justified). |
| `design/components.css` | All component styles. Must depend only on `tokens.css`. |
| `design/reference.html` | A single static page demonstrating every component, using **placeholder text only**. Links `tokens.css` and `components.css` by relative path. |
| `design/README.md` | One short paragraph per component: what it is for and which class to apply. |

The test this has to pass: **after a copy change, I regenerate every page from Markdown without
coming back to you.** If any of my words are baked into what you return, that test fails.

## Style the markup that already exists

Kramdown generates plain HTML from Markdown. Style **bare elements** (`h1`-`h4`, `p`, `ul`, `ol`,
`li`, `table`, `thead`, `th`, `td`, `blockquote`, `code`, `pre`, `a`, `img`, `hr`) plus exactly
these existing class names, all of which are already in the markup:

`hero` · `card` · `card-grid` · `banner` · `caption` · `container`
`nav-inner` · `nav-links` · `site-name` · `active`
`footer-content` · `footer-inner` · `footer-col` · `footer-bottom`

**Do not invent new class names for things that already have one.** New classes are acceptable only
for genuinely new components, and each one must be listed in the README.

## Hard constraints

- **Do not change a single word of copy.** Not in the reference page, not anywhere. Use lorem-style
  placeholder text in `reference.html`.
- **Do not invent a new palette.** Start from `current-styles.css`. The accent green `#2a6e3f` and
  the dark `#1a1a2e` are established and appear in diagrams and slide decks across the project.
- **No external dependencies.** No CDN fonts, no icon libraries, no CSS frameworks, no JS. System
  font stack only. The site must render offline and on a locked-down conference network.
- **No em-dashes** anywhere in anything you write.
- Must stay legible when printed, and readable at 320px width.
- Accessible contrast (WCAG AA) on every text/background pair you define.

## What is actually wrong today

Diagnosis, so you fix causes rather than symptoms:

1. **No visual hierarchy between "this is the argument" and "this is a link."** Accent-bordered cards
   are used for both, so everything shouts equally.
2. **Tables are the workhorse element** on `/software`, `/policy` and `/resources` and they are
   plain. They carry most of the site's substance.
3. **Diagrams and photos have no treatment.** No frame, caption style, or figure convention.
4. **The hero is a flat dark band** and does no work.
5. **No type scale.** Sizes are ad hoc, so long argument pages read as undifferentiated.

## Reference files in this folder

- `current-styles.css` — the entire existing stylesheet, verbatim. The starting point.
- `current-markup-home.html` — the real generated HTML of the home page, so you can see exactly what
  Kramdown emits and what you must style.

## Not in scope

- The logo. Twenty candidates exist and none has been chosen; the site ships a placeholder. Do not
  design one and do not build layouts that depend on one.
- Slide decks. Those use a separate Marp theme and are out of scope here.
