# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
versioning: [SemVer](https://semver.org/).

## [Unreleased]

### Planned
- English interface: file names, comments, user commands.
- Merge with `urt.sty`: document type chosen by package option
  (`report` / `script`).
- Math core without `physics` (unmaintained since 2012, `\qty` clash
  with siunitx): `derivative` (derivatives), `fixdif` (differentials),
  selected `physics2` modules (`ab`, `ab.legacy`, `braket`,
  `nabla.legacy`, `op.legacy`, `qtext.legacy`, `diagmat`, `xmat`).
  Aliases for old habits: `\dv`→`\odv`, `\dd`, `\vb`, `\vu`, `\vdot`,
  `\cross` (the `bm-um.legacy` module needs unicode-math, so it is out
  under pdfLaTeX). `\qty(…)` → `\ab(…)`; `\mqty` is dropped.
- Version number in `\ProvidesPackage`.

### Known issues
- Optional title-page fields (`\uczelnia`, `\przedmiot`, `\kierunek`,
  `\podtytul`, `\album`, `\prowadzacy`, `\miejsce`) are never treated
  as empty: `\newcommand` makes `\long` macros, so `\ifx\@field\empty`
  is always false. Also present in `urt.sty`.
- (`urt.sty`) a numbered equation shows “()”; `\cref` to a section
  gives “??” with `secnumdepth = 0`.

## Baseline — 2026-09-07
- `udt.sty` from the “Ogniwa elektrochemiczne” project.
