# Notably, Everything Changed

Interactive summary of the original 9,472-paper study across twelve CS venues and a new 21,306-paper census of ACL, EMNLP and NAACL main-conference papers. The original corrected statistical analysis covers 9,101 papers in its ten main venues. These samples overlap and are not added together.

Live page: https://odysa.github.io/notably-everything-changed/

Open research repository (paper source, analysis code, numeric measurements, and replication records): https://github.com/odysa/notably-everything-changed-analysis

The self-contained `index.html` embeds the original interactive figures and data; `assets/round4/` contains three figures for the newer census. `downloads/` contains the original study’s 12-page paper PDF, TeX source bundle, code and numeric-data reproduction bundle, selection protocol and checksums. A separate current-census numeric reproduction download and quickstart are now available; the census manuscript is still being prepared. The analysis bundle includes the separate CS replication's sampling catalog, selected source IDs, PDF hashes and numeric results. It contains no source PDFs, extracted paper prose or WildChat conversation text.

Quoted sentences are short excerpts from published papers, shown by venue and year only, as corpus-level examples. Nothing on the page is a claim about how any individual paper was written.

The opening game quotes paragraphs from ACL Anthology papers (CC BY 4.0), each credited with title, authors and link after the guess; PDF-extraction errors were corrected and run-in headings removed.

## October 24 census update

`census-update.html` explains the census trend, repeat-author and 2026 results,
with the three existing census figures and a link to aggregate evidence at
`assets/round4/census-evidence.json`. It contains no paper text or author IDs.
The outside-CS study is explicitly pending. Historical downloads remain
labelled as the original study. The homepage now distinguishes pooled venue
estimates and replication estimands.

Static checks cover unique IDs, local links/anchors, image alternative text,
inline JavaScript syntax and the aggregate cohort counts. Native Chrome
verification was unavailable (`cgWindowNotFound`); no new visual browser pass
is claimed.

## Current census reproduction

`downloads/census-reproduction.zip` contains the accepted 15-file numeric
supplement, with only its README updated for the public instructions. The
archive SHA-256 is
`aa1683a39924fb738b5548bbaf02a20f77a7d9d994afddb31e68705611589b7e`.
`downloads/census-quickstart.md` explains the tested Python/NumPy setup and
comparison tolerance. The source PDFs/prose are omitted; parser and figure
code are reference-only. The original-study downloads remain separately
labelled. The file-level checksums use standard SHA-256 format in
`downloads/census-contents.sha256`.
