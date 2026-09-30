# udt — Universal Document Template

A LaTeX package for lab reports and longer texts (scripts, course
papers, notes). One package with two modes, replacing the former
`urt.sty` (reports) and `udt.sty` (longer texts).

> **Status:** baseline — `udt.sty` as used in the electrochemical
> cells script. Merge with `urt.sty` in progress (see `CHANGELOG.md`).

## Usage

```latex
\documentclass[a4paper, polish, 11pt]{scrartcl}
\usepackage[report]{udt}   % or [script]
```

| mode     | purpose                          |
|----------|----------------------------------|
| `report` | lab report, two-column layout    |
| `script` | longer text: TOC, bibliography   |

## Build

`pdflatex → biber → pdflatex → pdflatex`

## Examples

`examples/` — every change to the package must leave all examples
compiling without errors.
