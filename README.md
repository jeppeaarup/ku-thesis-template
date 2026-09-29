# ku-thesis-template

![License](https://img.shields.io/github/license/jeppeaarup/ku-thesis-template)
![LaTeX](https://img.shields.io/badge/LaTeX-pdfLaTeX-008080?logo=latex&logoColor=white)
![Last commit](https://img.shields.io/github/last-commit/jeppeaarup/ku-thesis-template)

A LaTeX thesis template for the University of Copenhagen (KU), with a title page that follows the KU design guide, IEEE references, an abbreviation list, running headers and an appendix.

Click the button below to open the template in Overleaf:

[![Open in Overleaf](https://img.shields.io/badge/Open%20in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/jeppeaarup/ku-thesis-template/archive/refs/heads/main.zip&snip_name=ku-thesis-template&engine=pdflatex)

## Features

- KU title page with faculty logo (`ku-titlepage.sty`), configurable text, positions and font sizes
- Front matter: AI declaration, abstract, preface, table of contents, list of abbreviations
- Running headers that show the current section, or the name of the part in the front matter, references and appendix
- IEEE-style numbered references with `biblatex` and `biber`
- Abbreviations with first-use expansion and an automatic list (`acro`)
- Cross-references with `cleveref`, and clickable links in KU red
- Appendix with lettered sections (A, B, ...)
- Roman page numbers for the front matter, arabic for the main text

## Folder structure

| Path | Content |
|---|---|
| `main.tex` | Main file: defines the order of the document |
| `config/` | Settings: `preamble.tex` (packages), `layout.tex` (margins, headers), `fonts.tex` (headings), `references.tex` (bibliography, links), `acronyms.tex` (abbreviations) |
| `frontmatter/` | Title page, AI declaration, abstract, preface, abbreviations |
| `chapters/` | Main text and appendix |
| `figures/` | Your images |
| `logos/` | KU logos used by the title page |
| `ku-titlepage.sty` | Title page package ([source](https://github.com/jeppeaarup/ku-titlepage)) |
| `references.bib` | Your bibliography |

## Getting started

1. Clone or download the repository, or open it directly in Overleaf with the badge above.
2. Edit `frontmatter/titlepage.tex` with your title, name, assignment type and supervisor.
3. Choose your faculty in `config/preamble.tex`:
   `\usepackage[science, titlepage]{ku-titlepage}`
   Options: `science`, `teo`, `sund`, `samf`, `jura`, `hum`.
4. Write your text in `chapters/` and add each file to `main.tex` with `\input{...}`.
5. Add your sources to `references.bib` and cite them with `\cite{key}`.
6. Add abbreviations in `config/acronyms.tex` and use them with `\ac{key}`.
7. Remove the placeholder text (`\lipsum`) from the abstract, preface and chapters.

## Building

The template uses pdfLaTeX and `biber`. The simplest way to build is:

    latexmk -pdf main.tex

If you compile manually, run pdfLaTeX, then `biber main`, then pdfLaTeX twice more. Run LaTeX twice after changing abbreviations.

## Quick reference

**Abbreviations** (defined in `config/acronyms.tex`)

| Command | Result |
|---|---|
| `\ac{key}` | Full form on first use, short form after |
| `\acs{key}` / `\acl{key}` | Always short / always long |
| `\acp{key}` | Plural |
| `\Ac{key}` | Capitalised, for the start of a sentence |

**Headers.** Each front matter part sets its header with `\headermark{Name}` in `main.tex`. Sections set their own header text.

**Appendix.** Put appendix sections in `chapters/appendix.tex`. They are lettered automatically and the header reads "APPENDIX A", "APPENDIX B", and so on.

**Colours.** Links are coloured with the KU red (RGB 144, 26, 30), set in `config/references.tex`.

## Requirements

A recent TeX distribution (TeX Live or MiKTeX) with `biber` and these packages: `biblatex`, `acro`, `cleveref`, `hyperref`, `titlesec`, `tocloft`, `fancyhdr`, `geometry`, `babel`, `csquotes`, `xcolor` and the TeX Gyre fonts. They are included in a full installation.

## License

MIT License. See `LICENSE`.