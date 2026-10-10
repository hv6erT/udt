# udt — Universal Document Template

A LaTeX package for lab reports and longer texts (scripts, course
papers, notes). One package with two modes, replacing the former
`urt.sty` (reports) and `udt.sty` (longer texts).

> **Status:** 0.6.0 — both modes working, interface may still change
> before 1.0.0. Changes and migration notes from `urt.sty` / the old
> `udt.sty`: see `CHANGELOG.md`.

## Usage

```latex
\documentclass[a4paper, polish, 11pt]{scrartcl}
\usepackage[report]{udt}   % or [script]
```

| mode     | purpose                          |
|----------|----------------------------------|
| `report` | lab report, two-column layout    |
| `script` | longer text: TOC, bibliography (default) |

Language (babel) comes from the class options; Polish and English
strings are provided. Option `chem` adds `mhchem` and chemistry macros.
Option `full` switches on all variants — environments of conditional
content declared with `\newvariant` and switched on one by one with
`\showvariant` (one source, several versions of a document).
The full interface is documented in the header of `udt.sty`.

## Build

`pdflatex → biber → pdflatex → pdflatex`

## Examples

`examples/` — every change to the package must leave all examples
compiling without errors.

## License

LaTeX Project Public License 1.3c or later — see `LICENSE`.
Modified versions must be distributed under a different name.
