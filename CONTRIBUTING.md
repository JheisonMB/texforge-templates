# Contributing to texforge-templates

Thanks for wanting to contribute a template! This guide explains how to create and submit one.

## Template Structure

Every template is a directory with this layout:

```
my-template/
├── template.toml     ← required: metadata and variable declarations
├── main.tex          ← required: entry point
├── sections/         ← optional: additional .tex files
├── bib/              ← optional: bibliography files
└── assets/           ← optional: images, fonts, etc.
```

### `template.toml`

```toml
[metadata]
nombre = "my-template"
descripcion = "Short description of the template"
idioma = "es"           # es | en
tipo = "article"        # article | thesis | letter | report

[variables]
requeridas = ["titulo", "autor"]
opcionales = ["dedicatoria"]

[compatibilidad]
mermaid = false
graphviz = false
bibliografia = "bibtex"  # bibtex | biblatex | none
```

### Variable slots in `.tex` files

Use `{{variable}}` syntax for values that come from `project.toml`:

```latex
\title{{{titulo}}}
\author{{{autor}}}
```

## Compatibility Requirements

Templates must work with [tectonic](https://tectonic-typesetting.github.io/) as the LaTeX engine. Tectonic resolves packages automatically, but **avoid packages that require external binaries**:

| ❌ Incompatible | ✅ Alternative |
|---|---|
| `minted` (needs `pygmentize`) | `listings` |
| `gnuplottex` (needs `gnuplot`) | TikZ |
| `svg` (needs `inkscape`) | Embed as PNG/PDF |

Test your template with `texforge template validate ./my-template` before submitting.

## Submitting a Template

1. Fork this repository
2. Create your template directory following the structure above
3. Add an entry to `registry.toml`:

```toml
[[templates]]
nombre = "my-template"
descripcion = "Short description"
version = "0.1.0"
```

4. Open a pull request with a brief description of the template's use case

## Questions

Open an issue or check the main CLI repo: [github.com/JheisonMB/texforge](https://github.com/JheisonMB/texforge)
