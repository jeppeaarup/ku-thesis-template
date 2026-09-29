# ku-thesis-template

A LaTeX thesis template for the University of Copenhagen (KU), with a title page that follows the KU design guide, IEEE references, an abbreviation list, running headers and an appendix.

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
| `ku-titlepage.sty` | Title page package (https://github.com/jeppeaarup/ku-titlepage)|
| `references.bib` | Your bibliography |

## Getting started

1. Clone or download the repository.
2. Edit `frontmatter/titlepage.tex` with your title, name, assignment type and supervisor.
3. Choose your faculty in `config/preamble.tex`:
   `\usepackage[science, titlepage]{ku-titlepage}`
   Options: `science`, `teo`, `sund`, `samf`, `jura`, `hum`.
4. Write your text in `chapters/` and add each file to `main.tex` with `\input{...}`.
5. Add your sources to `references.bib` and cite them with `\cite{key}`.
6. Add abbreviations in `config/acronyms.tex` and use them with `\ac{key}`.
7. Remove the placeholder text (`\lipsum`) from the abstract, preface and chapters.

## Quick reference

**Headers.** Each front matter part sets its header with `\headermark{Name}` in `main.tex`. Sections set their