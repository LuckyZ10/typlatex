# Typlatex

**A LaTeX-style theme family for Typora — write Markdown, get a typeset
journal article.**

[中文文档](README.zh-CN.md) · [Theme gallery post](https://theme.typora.io/) · Typora ≥ 1.6 · MIT

![typlatex-ink](screenshots/typlatex-ink.png)

Documents render on an **A4 paper card** with **justified two-column text**,
serif body type, LaTeX-style first-line indents, **booktabs three-line
tables**, figures that **span columns automatically**, blue centered
captions — and export to a true **A4 two-column PDF** with one click.

---

## Pick your variant

| | Plain | Ink |
|---|---|---|
| **Journal** — two-column, continuous flow | [`typlatex`](screenshots/typlatex.png) | [`typlatex-ink`](screenshots/typlatex-ink.png) |
| **Book** — every H2 spans the page, chapters restart columns | [`typlatex-book`](screenshots/typlatex-book.png) | [`typlatex-book-ink`](screenshots/typlatex-book-ink.png) |
| **Article** — single column, 12pt, traditional | [`typlatex-article`](screenshots/typlatex-article.png) | [`typlatex-article-ink`](screenshots/typlatex-article-ink.png) |

**Plain** keeps headings quiet and typographic. **Ink** renders H2 as a dark
label with a single huge bottom-right round corner set into a light-gray
track, and prints bold text in coral. The screenshots above are all the
**same document** — switch themes any time from Typora's `Themes` menu.

<details>
<summary><b>All six previews</b></summary>

| Theme | Preview |
|-------|---------|
| `typlatex` | ![typlatex](screenshots/typlatex.png) |
| `typlatex-book` | ![typlatex-book](screenshots/typlatex-book.png) |
| `typlatex-ink` | ![typlatex-ink](screenshots/typlatex-ink.png) |
| `typlatex-book-ink` | ![typlatex-book-ink](screenshots/typlatex-book-ink.png) |
| `typlatex-article` | ![typlatex-article](screenshots/typlatex-article.png) |
| `typlatex-article-ink` | ![typlatex-article-ink](screenshots/typlatex-article-ink.png) |

</details>

## Install

1. Download & unzip this repository.
2. Typora → `File → Preferences → Appearance → Open Theme Folder`.
3. Copy the `.css` files you want into that folder.
4. Restart Typora → pick a theme from the `Themes` menu.

> Enable **Preferences → Markdown → Inline Math** if you use `$…$`.

## What it does

**Figures & captions.** An image alone in a paragraph spans both columns
(like `figure*`); inline images stay in-column. An italic-only paragraph
right after a figure — blank line or not — becomes a centered blue caption
that follows the figure's span.

**Span anything with `---`.** A horizontal rule is an invisible trigger:
the next block — paragraph, `$$` math, or table — spans both columns.

```markdown
---

$$
\begin{aligned}
f(x) &= a+b+c+d+e \\
     &= g+h
\end{aligned}
$$
```

Long formulas break with `aligned` + `\\` + `&`; display math is centered
and never clipped.

**Tables.** Booktabs-style three-line tables, in-column at 8.5pt; put `---`
above a table to span it at 9pt.

**Headings.** H1 is the article title (spans, centered). No auto-numbering —
write `## 1. Introduction` yourself, or re-enable numbering via the
commented block at the end of each CSS file.

## Customize

Everything lives in the `:root` block at the top of each CSS file:

| Variable | Default | Meaning |
|----------|---------|---------|
| `--page-width` | `178mm` | A4 content width |
| `--page-margin` | `16mm` | Screen & print margins |
| `--col-gap` | `7mm` | Column gap |
| `--font-size` | `10.5pt` | Body size (12pt in article themes) |
| `--para-indent` | `0em` | First-line indent (set `2em` + `--para-gap: 0` for LaTeX style) |
| `--para-gap` | `0.55em` | Paragraph spacing (separates paragraphs when not indenting) |
| `--caption-color` | `#0b53c2` | Caption color |

Ink heading geometry (colors `#212122`/`#FBFBFB`, 35pt corner radius) is
marked with a `装修` comment in the Ink themes.

## Know before you go

- Leave a **blank line above `---`** — otherwise the line above turns into
  a setext H2 (a Markdown rule).
- Spanning blocks rebalance the columns above them; place big spans at
  natural paragraph boundaries for the cleanest look.
- Blank lines can't act as triggers: `---\nX` and `---\n\nX` render
  identically, so no theme can distinguish them.

## License

[MIT](LICENSE) — © 2026 LuckyZ10
