# Historia zmian

Format: [Keep a Changelog](https://keepachangelog.com/pl/1.1.0/),
numeracja: [SemVer](https://semver.org/lang/pl/).

## [Niewydane]

### Planowane
- Scalenie z `urt.sty`: rodzaj dokumentu wybierany opcją pakietu
  (sprawozdanie / praca).
- Rdzeń matematyczny bez `physics` (nieutrzymywany od 2012, konflikt
  `\qty` z siunitx): `derivative` (pochodne), `fixdif` (różniczki),
  wybrane moduły `physics2` (`ab`, `ab.legacy`, `braket`, `nabla.legacy`,
  `op.legacy`, `qtext.legacy`, `diagmat`, `xmat`). Aliasy w `udt`
  dla dawnych nawyków: `\dv`→`\odv`, `\dd`, `\vb`, `\vu`, `\vdot`,
  `\cross` (moduł `bm-um.legacy` wymaga unicode-math, więc odpada
  przy pdfLaTeX-u). `\qty(…)` → `\ab(…)`; `\mqty` znika.
- Numer wersji w `\ProvidesPackage`.

### Znane usterki
- Pola opcjonalne strony tytułowej (`\uczelnia`, `\przedmiot`,
  `\kierunek`, `\podtytul`, `\album`, `\prowadzacy`, `\miejsce`) nigdy
  nie są traktowane jako puste: `\newcommand` tworzy makra `\long`,
  więc `\ifx\@pole\empty` zawsze daje fałsz. Dotyczy też `urt.sty`.
- (`urt.sty`) numerowane równanie wyświetla „()”, `\cref` do sekcji
  daje „??” przy `secnumdepth = 0`.

## Stan wyjściowy — 2026-09-07
- `udt.sty` z projektu „Ogniwa elektrochemiczne”.
