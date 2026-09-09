# LNGAI-Barcelona

Slides for **"Agentic LLMs for Argument Mining in Philosophical Texts"**
(Maximilian Noichl & Jan Broersen), presented at the
[Sixth International Workshop on Logics and Argumentation for New-Generation
Artificial Intelligence (LNGAI 2026)](https://www.zlaire.net/lngai2026/),
co-located with COMMA 2026 in Barcelona, Spain, on 14 September 2026.

The talk is listed in [Session 03: Argument Mining](https://www.zlaire.net/lngai2026/program.html).
The [workshop venue](https://comma2026.vercel.app/venue/) is the CSIC Delegation
in Catalonia, Carrer de les Egipcíaques, 15, Barcelona.

The deck is `index.qmd`, rendered with Quarto Reveal.js; the rendered site is
committed (`index.html` + `index_files/`) for hosting. Large local data files
and the unpublished paper draft are excluded via `.gitignore`.

Git uses an explicit allowlist for the slide source, configuration, template
files, modal extension, bibliography, and six figures used by the talk. Other
local material (old decks, notebooks, datasets, unused images, and drafts) stays
on disk but is ignored, including material inside template directories. Add
new source files or figures to `.gitignore` when the deck starts using them.
The generated libraries in `index_files/libs/` remain tracked for hosting.

---

# Scholarly Folio Quarto Template

This folder is a Quarto Reveal.js template with a clean academic visual system:
ivory paper, thin warm beige rules, restrained black typography, high-contrast
serif headings, and small-caps sans labels.

The old slide mechanics remain in place. Write semantic Markdown first, then add
the existing `layout="..."` attributes and `data-*` hooks when a slide needs a
specific behavior.

## Render

```bash
quarto render index.qmd
```

Preview over HTTP, especially for iframe and shader slides:

```bash
quarto preview index.qmd
```

## Slide Layouts

Use layout attributes on slide headings:

```markdown
# Talk title {layout="title" data-gp-kicker="MONOLINE FOLIO" data-gp-code="The Case for Clarity"}

# Agenda {layout="outline"}

# Key Points {layout="bullets"}

# A Study in Structure {layout="half" data-gp-fragments="off"}

# Framed Exhibit {layout="exhibit" data-gp-caption="Fig. 1 - Caption text."}

# Literature {layout="references"}
```

Supported layout values are `title`, `outline`, `divider`, `claim`, `bullets`,
`reading`, `quote`, `exhibit`, `half`, `filters`, `table`, and `references`.

## Interaction Hooks

Modal anchors still work:

```markdown
[Open](#){.opens-modal data-modal-type="image" data-modal-url="images/example.png"}
```

Common modal types are `image`, `iframe`, `video`, and `html`.

Use `aside` blocks for the stable footer citation band:

```markdown
::: aside
[@tufte2006; @bringhurst2012]
:::
```

For changing images next to bullet points, keep `layout="half"
data-gp-fragments="off"` and pair manual `fragment` list items with a
`.gp-fragment-stack` of framed figures, as shown in `index.qmd`.

## Source Files

- `_quarto.yml` wires Quarto and Reveal.
- `index.qmd` is the editable template deck.
- `gp-quarto.js` maps Quarto output to template classes and behaviors.
- `gp-template/js/grid-protocol.js` handles folios, running labels, and column automation.
- `gp-template/css/grid-protocol.css` defines the scholarly visual system.
- `gp-quarto.css` contains Quarto-specific parity and modal overrides.

Generated files such as `index.html`, `index_files/`, and `.quarto/` are not the
source of truth.
