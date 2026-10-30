# How this repository was made (Bosnian-Podrinje Canton Goražde)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Bosansko-podrinjski kanton Goražde: Službene novine Bosansko-podrinjskog kantona Goražde (each issue as a PDF; izvor named as the site asks) | <https://bpkg.gov.ba/sluzbene-novine/7102/sluzbene-novine-bpk-gorazde> | 2026-10-30 | Official text, not protected: Zakon o autorskom i srodnim pravima BiH (Sl. glasnik BiH 63/10), čl. 8(1)(b) |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `o-poljoprivrednoj-savjetodavnoj-sluzbi-bosansko-podrinjskog` | Zakon o poljoprivrednoj savjetodavnoj službi Bosansko-podrinjskog kantona Goražde | 1 | 2023-12-12 to 2023-12-12 |
| `o-uredjenju-saobracaja-na-podrucju-bosansko-podrinjskog-kant` | Zakon o uređenju saobraćaja na području Bosansko-podrinjskog kantona Goražde | 1 | 2024-03-19 to 2024-03-19 |
| `o-pravobraniteljstvu-bosansko-podrinjskog-kantona-gorazde` | Zakon o pravobraniteljstvu Bosansko-podrinjskog kantona Goražde | 1 | 2025-12-06 to 2025-12-06 |
| `o-visokom-obrazovanju` | Закон о високом образовању | 1 | 2026-02-27 to 2026-02-27 |

The build made 4 commits:

| Commits | Kind |
| ---: | --- |
| 4 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `buducnost`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 4 laws in the record.
- 8 tags.

## Dates

Each commit is dated at noon (Europe/Sarajevo) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: A law takes effect on the day its own final article names, counted from its publication in the Službene novine Bosansko-podrinjskog kantona Goražde. https://bpkg.gov.ba/sluzbene-novine/7102/sluzbene-novine-bpk-gorazde

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `57623f84636c4cc9da40fc404f36e2a3bfd8da98d7603832f73e5daaa5b10513` (514599 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `900da0d33bfd1ef455267fb4dcef7961fd5acc9c`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

4 versions of 4 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Laws part 1: laws the Assembly of Bosnian-Podrinje Canton Goražde published in the Službene novine Bosansko-podrinjskog kantona Goražde from 2022-01-01 to 2026-09-14 (every issue on bpkg.gov.ba in that span, 64 issues; laws are checked against every later issue) that no later law in those issues amends, repeals or consolidates: a law is left out when any later amending law or consolidated text cites its gazette number next to a word of its subject, or any later law cites it next to words of repeal. Amending and budget laws are left out. Each is its text as enacted, dated the issue date plus the days its final article names, credited to the law; or, where the Legislative Committee of the Assembly has published an official consolidated text (prečišćeni tekst) that nothing later touches, that text, dated the day it was published (it applies from its publication, as its last article says). Amendments published after 2026-09-14, and decisions of the Constitutional Court, are not in the record.
- Each law is kept in the language and script of the gazette issue it was published in (the issues rotate between Bosnian, Croatian and Serbian; the Serbian issues are in Cyrillic).
- Units: uvod.md is the preamble (legal basis and adoption), naslov.md the title, clan-NNN.md each article with its heading (chapter headings stay with the article after them), potpis.md the signature block.
- Line-end hyphens: the gazette is set in two justified columns and breaks words at line ends with a hyphen ("Us-/tava"), but also breaks real compounds at their own hyphen ("Bosansko-/podrinjskog"). Rule: as "A-B" when "A-B" occurs unbroken more often than "AB"; when neither occurs, or both equally often, as "A-B" if B starts with a capital letter or a digit, or A ends in a digit, or the last part of A (6 letters or more) ends in "o" and B (4 letters or more) occurs at least twice as a whole word in those issues (a compound adjective such as "sigurnosno-/tehničkih"); otherwise as "AB". A dash after a space (" -") is never a break inside a word. The dictionary is every word printed inside a line in those issues (the first word of each line and the last word of a line ending in a hyphen are left out, since either may be a fragment), lowercased.
- Source: Službene novine Bosansko-podrinjskog kantona Goražde, published by Bosansko-podrinjski kanton Goražde at https://bpkg.gov.ba/sluzbene-novine/7102/sluzbene-novine-bpk-gorazde. The site forbids taking or distributing its content without naming the source ("Zabranjeno je svako neovlašteno preuzimanje i distribucija sadržaja bez navođenja izvora informacija"); the source is named here, in README.md and in LICENSE.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text is read from the gazette PDFs' text layer by a deterministic parser; no model output is legal text.
