# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
versioning: [SemVer](https://semver.org/).

## [Unreleased]

### Added
- License: LPPL 1.3c (`LICENSE`, notice in `udt.sty`).

### Planned
- Release 1.0.0 after the first real report and script are written
  with the package.

## [0.3.0] — 2026-09-30

### Added
- Package options `report` and `script` (default: `script`).
- Mode `report` (from `urt.sty`): header bar with exercise, title in
  capitals, author, supervisor and dates; running head “Report on
  exercise N”; `\begincolumns` opens the two-column body (closed
  automatically); unnumbered sections; `preface` and `abstract`
  without headings, full width.
- Figures and tables in `report` default to `[H]`, so a plain
  `figure`/`table` works inside columns; `figure*`/`table*` span both.
- Examples `examples/report.tex` and `examples/script.tex`.

### Fixed (relative to `urt.sty`)
- Equations in `report` are numbered (1), (2), … — no more empty “()”;
  `\cref` gives “równanie (1)”.
- Sections in `report` stay unnumbered; reference them by name with
  `\nameref` instead of the former `\cref` that gave “??”.
- Theorem-like environments in `report` are numbered 1, 2, … (not 0.1).

## [0.2.0] — 2026-09-30

### Changed
- English interface. Title fields: `\author`, `\title`, `\subtitle`,
  `\date` (submission; default `\today`), `\institution`, `\course`,
  `\group`, `\studentid`, `\supervisor`, `\place`, and for reports
  `\exercise`, `\experimentdate`. Environments `abstract`, `preface`;
  theorem-like `theorem`, `law`, `definition`, `fact` (shared
  counter) and `proof`.
- Language taken from the class options (babel). Typeset strings,
  cleveref names and the siunitx locale follow the language; Polish
  and English provided, English is the fallback.
- Math core without `physics` (unmaintained since 2012, `\qty` clash
  with siunitx): `derivative`, `fixdif`, `physics2` modules `ab`,
  `ab.legacy`, `braket`, `nabla.legacy`, `op.legacy`, `qtext.legacy`,
  `diagmat`, `xmat`. Aliases: `\dv`, `\dd`, `\vb`, `\va`, `\vu`
  (starred: italic), `\vdot`, `\cross`.
- Chemistry (`mhchem`, `\std`, `\Eo`, `\redox`) only with option `chem`.
- `\title` and `\author` go into the PDF metadata.

### Removed
- `wzor` (boxed formula) and with it `tcolorbox`.
- `inputenc` (UTF-8 is the LaTeX default since 2018).

### Fixed
- Empty optional title fields are really skipped (the former
  `\ifx\@field\empty` test was always false for `\newcommand` macros).

### Migration notes
- `\qty(…)` → `\ab(…)`; `\qty` is now siunitx's quantity command.
- `\mqty` is gone — use `pmatrix` and friends.
- `\bra{a}\ket{b}` no longer merges into ⟨a|b⟩ — write `\braket{a}{b}`.
- `\div` is divergence; the ÷ sign is `\divsymbol`.

## Baseline — 2026-09-07
- `udt.sty` from the “Ogniwa elektrochemiczne” project.
