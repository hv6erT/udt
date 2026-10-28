# udt — Universal Document Template

A LaTeX package for lab reports and longer texts (scripts, course
papers, notes, lecture summaries). Two modes in two files sharing a
common core; successor of `urt.sty` (reports) and the former
`udt.sty`.

> **Status:** 0.10.1 — interface may still change before 1.0.0.
> Changes and migration notes: see `CHANGELOG.md`.

## Files

| file             | purpose                                              |
|------------------|------------------------------------------------------|
| `udt-report.sty` | report mode: header bar, two-column body — lab reports, lecture summaries |
| `udt-script.sty` | script mode: title block, TOC, bibliography — scripts, notes, papers |
| `udt-core.sty`   | common part, loaded by both modes (not loaded directly) |

A document needs `udt-core.sty` and the mode file it uses.

## Usage

```latex
\documentclass[a4paper, polish, 11pt]{scrartcl}
\usepackage{udt-report}   % or {udt-script}; options: plain, chem, full
```

Language (babel) comes from the class options; Polish and English
strings are provided. Option `plain` draws theorem-like environments
without coloured blocks; `chem` adds `mhchem` and chemistry macros;
`full` switches on all variants — environments of conditional
content declared with `\newvariant` and switched on one by one with
`\showvariant` (one source, several versions of a document).

In report mode `\doctype{...}` sets the kind of document shown
above the title (default “Sprawozdanie z ćwiczenia”), e.g.
`\doctype{Streszczenie wykładu}` for lecture summaries.

The full interface is documented in the headers of the `.sty` files.

## Build

`pdflatex → biber → pdflatex → pdflatex`

## Examples

`examples/report.tex`, `examples/notes.tex` (report mode as a lecture
summary), `examples/script.tex`. Every change to the package must
leave all examples compiling without errors.

## License

LaTeX Project Public License 1.3c or later — see `LICENSE`.
Modified versions must be distributed under a different name.
