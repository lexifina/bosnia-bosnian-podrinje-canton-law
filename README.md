# Bosnian-Podrinje Canton Goražde: law history in git

The law of Bosnian-Podrinje Canton Goražde (Bosansko-podrinjski kanton Goražde), one of the ten cantons of the Federation of Bosnia and Herzegovina, as a git history: one file per article, one commit per law, dated the day it took effect, with the law as the commit's author. `git log` lists every change to an article; checking out a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ba-05/`. The Federation's own law is in [lexifina/bosnia-federation-law](https://github.com/lexifina/bosnia-federation-law), the state's in [lexifina/bosnia-and-herzegovina-law](https://github.com/lexifina/bosnia-and-herzegovina-law).

Each law is kept in the language and script of the gazette issue it was published in: the issues rotate between Bosnian, Croatian and Serbian, and the Serbian issues are in Cyrillic.

## Source

**Izvor: Službene novine Bosansko-podrinjskog kantona Goražde**, published by Bosansko-podrinjski kanton Goražde, <https://bpkg.gov.ba/sluzbene-novine/7102/sluzbene-novine-bpk-gorazde>: every issue as a PDF with a text layer. The Canton's site asks that the source be named whenever its content is taken or distributed; please keep this attribution when reusing the texts.

## What this repository holds

Laws the Assembly of Bosnian-Podrinje Canton Goražde published in the Službene novine Bosansko-podrinjskog kantona Goražde from 2022 to September 2026 (all 64 issues on the site in that span) that no later law in those issues amends, repeals or consolidates, each as enacted, dated the day it took effect, which is therefore also its current text.

Not included yet: the Constitution of the Canton; laws that were later amended; amending, repealing and budget laws; laws before 2022.

## Dates

- Each law's commit is dated at **noon, Europe/Sarajevo, on the day it took effect**: the issue's date plus the days the law's own final article names (most often the eighth day after publication).
- Versions that take effect after the retrieval day would go on the `buducnost` branch, never merged into `main`.

## Files

`<law>/clan-001.md` is Član/Članak 1, `clan-005-a.md` Član 5a. `uvod.md` holds the preamble (the legal basis and the Assembly's adoption), `naslov.md` the title, `potpis.md` the signature block. Chapter headings stay in the file of the article they stand before. One paragraph per line.

## Line-end hyphens

The gazette is set in two justified columns and breaks words at line ends with a hyphen ("Us-/tava"), but it also breaks real compounds at their own hyphen ("Bosansko-/podrinjskog"). A line ending "A-" followed by "B" is joined as "AB" when "AB" occurs unbroken inside a line in the 64 issues more often than "A-B"; as "A-B" when "A-B" occurs unbroken more often; when neither occurs (or both equally often), as "A-B" if B starts with a capital letter or a digit, or A ends in a digit, or the last part of A (6 letters or more) ends in "o" and B (4 letters or more) occurs at least twice as a whole word in those issues (a compound adjective such as "sigurnosno-/tehničkih"); otherwise as "AB". The rule is recorded in each part's decisions.

## How it is checked

- Every version is read back from git on the day it took effect and on the day before; both must match `corpus.json`.
- The letters and digits of every law equal those of the gazette issue, read independently with a different PDF reader, from the first paragraph to the last article; the signature block's lines all occur in it.
- Whether a law was later amended or repealed is judged from every later law in the scanned issues (a law is left out when a later amending law cites its gazette number next to a word of its subject, or any later law cites it next to words of repeal). Decisions of the Constitutional Court are not checked.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## What "author" means

The author of a commit is the law that made it, named by its gazette number, with an e-mail address that cannot exist (`<key>@bpkg.gov.ba.invalid`). The committer is always Lexifina.

## Limits

This is not an official publication. The binding text is the one published in the Službene novine Bosansko-podrinjskog kantona Goražde. Only the laws listed in `data/versions.json` are included; amendments published after the last issue read are not in the record.
