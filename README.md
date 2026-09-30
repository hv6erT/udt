# udt

Pakiet LaTeX-a do sprawozdań laboratoryjnych i dłuższych prac tekstowych
(skrypty, prace zaliczeniowe, notatki). Następca `urt.sty`
(sprawozdania) i dotychczasowego `udt.sty` (prace) — jeden pakiet
zamiast dwóch.

> **Stan:** wersja wyjściowa — `udt.sty` w postaci używanej w skrypcie
> o ogniwach. Scalanie z `urt.sty` w toku (zob. `CHANGELOG.md`).

## Użycie

```latex
\documentclass[a4paper, polish, 11pt]{scrartcl}
\usepackage{udt}
```

Pełny opis pól strony tytułowej, struktury dokumentu i makr —
w nagłówku `udt.sty`.

## Kompilacja

`pdflatex → biber → pdflatex → pdflatex`

## Przykłady

Katalog `przyklady/` — każda zmiana pakietu powinna zostawiać
wszystkie przykłady składającymi się bez błędów.
