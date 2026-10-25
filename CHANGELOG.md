# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
versioning: [SemVer](https://semver.org/).

## [Unreleased]

### Added
- License: LPPL 1.3c (`LICENSE`, notice in `udt.sty`).

### Planned
- Release 1.0.0 after the first real report and script are written
  with the package.

## [0.9.0] — 2026-10-25

### Added
- Several authors: `\author{A \and B}` together with
  `\studentid{1 \and 2}`, the IDs paired with the authors in order.
  The title block (report and script) sets the authors on one line,
  separated by a thin vertical rule; the PDF metadata lists them
  all.

## [0.8.0] — 2026-10-15

### Added
- Option `plain`: theorem-like environments without coloured blocks
  (plain amsthm look, as in the package from the “Ogniwa
  elektrochemiczne” project); `aside` becomes smaller type set off
  by space, with a bold heading.

## [0.7.5] — 2026-10-15

### Fixed
- Footnotes inside blocks (theorems, definitions, facts, examples,
  remarks, asides, variant blocks) go to the foot of the page and
  are numbered together with the other footnotes, instead of
  staying at the bottom of the box numbered a, b, ... (package
  footnotehyper, savenotes around every block).

## [0.7.4] — 2026-10-14

### Fixed
- The grey bar of a proof that continues on a new page no longer
  runs through floats at the top of that page, nor through
  footnotes and floats at its bottom: the output routine marks
  the top and bottom of the main text of every page. Pages made
  only of floats get no bar.

## [0.7.3] — 2026-10-11

### Changed
- The proof name („Dowód.”) stands on a line of its own; the proof
  starts on the next line, also when it starts with a list.

## [0.7.2] — 2026-10-11

### Fixed
- Footnotes in a proof go to the foot of the page. The proof is no
  longer a box: its grey bar is drawn at shipout from positions
  saved in the `.aux` file (zref-savepos), so it appears after the
  second run.
- Blocks inside a proof (e.g. shown variant content) break across
  pages like anywhere else.

## [0.7.1] — 2026-10-10

### Changed
- Shown variant content is marked by a square bracket instead of a
  curly brace. When the block breaks across pages the bracket stays
  open at the break: the first part has only the top tick, the last
  part only the bottom tick.

## [0.7.0] — 2026-10-10

### Added
- Unnumbered starred twins of all theorem-like environments
  (`definition*`, `theorem*`, `lemma*`, `fact*`, `corollary*`,
  `law*`, `example*`, `remark*`), drawn like the numbered ones.
  Meant for content of variants (e.g. `extended`), so that numbers
  stay the same in every version of a document.

## [0.6.1] — 2026-10-10

### Changed
- The brace marking shown variant content is more pronounced
  (amplitude 6pt, line 0.8pt, indent 12pt); at the old size a tall
  brace read as a straight rule.
- Documented: inside another box (e.g. a proof) a variant block
  cannot break across pages — split long content into several blocks.

## [0.6.0] — 2026-10-10

### Changed
- Variants no longer use the comment package. A variant that is off
  takes its body as an argument and typesets nothing; one that is on
  is an ordinary environment. `\begin{…}` and `\end{…}` may now be
  indented (e.g. inside lists) — with the comment package an indented
  `\end` was not recognised, which broke the document under MiKTeX.
- No temporary `.cut` files any more.

### Notes
- Hidden variant content must have balanced braces and must not
  contain verbatim material (`\verb`, `verbatim`); shown content has
  no such restriction.

## [0.5.2] — 2026-10-10

### Changed
- Shown variant content is marked by a curly brace on the left instead
  of a rule, so it cannot be mistaken for the proof rule (also in
  greyscale print). A block broken across pages gets a brace on each
  page.

## [0.5.1] — 2026-10-10

### Changed
- Shown variant content is set off by a thin dark rule on the left
  (0.8 pt, colour `udtVariantColor`) and an 8 pt indent; the block
  breaks across pages. Figures and tables inside it are placed where
  written (`[H]`), since a float cannot leave a box.

## [0.5.0] — 2026-10-10

### Added
- Variants (conditional content): one source, several versions of a
  document. `\newvariant{a, b}` declares environments `a`, `b`;
  `\showvariant{a}` switches a variant on; content of a variant that
  is off is skipped as if it were not in the source (comment package,
  so figures and `verbatim` inside are safe). Both commands go in the
  preamble, in any order; the decision is taken at
  `\begin{document}`.
- Package option `full`: switches on all variants. A job name ending
  in `-ext` does the same, so `pdflatex name` and
  `pdflatex -jobname=name-ext name` give `name.pdf` and
  `name-ext.pdf` from one source.
- Predefined variant `extended`.
- Error for a variant name that clashes with an existing command or
  environment; warning for `\showvariant` of an undeclared variant.

### Notes
- `\begin{…}` and `\end{…}` of a variant must stand on lines of
  their own (comment package).
- The comment package's temporary file is `<jobname>.cut` (one per
  job, so both versions can be built side by side).
- Hidden content takes no numbers; a `\ref` from outside to a label
  inside hidden content gives “??”.

## [0.4.0] — 2026-09-30

### Added
- Coloured blocks (tcolorbox, bar on the left) for all theorem-like
  environments; proof gets a thin grey bar.
- New environments: `lemma`, `corollary` (with `fact`, green),
  `example`, `remark`; unnumbered `aside` for side information
  (history, curiosities) — smaller type, grey, skippable.
- Named colours for physical quantities, for text and TikZ:
  `udtPos`, `udtVel`, `udtAcc`, `udtForce`, `udtMom`, `udtAxis`.

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
