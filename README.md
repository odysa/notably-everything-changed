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

## November 7 naming update

`naming-update.html` reports the separate 100-paper title/abstract audit,
weighted to 5,698 ACL main-conference long papers. Two native inline SVG
charts and HTML tables distinguish unknown-attribution ranges from approximate
sampling intervals. `assets/naming/evidence.json` contains aggregate estimates
and source hashes; no source paper prose or private paths are included.

Data and local-link checks passed. The browser access host was unavailable,
so this revision has no new desktop/mobile screenshot verification. The page
uses responsive CSS and includes readable table equivalents for both charts.

## One combined blog (November 7)

The full original study, conference census and naming audit now live in
`index.html`, with one section menu. The earlier abbreviated census section
was replaced by the complete census chapter, rather than duplicated.
`census-update.html` and `naming-update.html` forward old links to the relevant
chapter, including known deep links, and offer a plain link without JavaScript.
Native naming SVGs, evidence tables and downloads remain available in place.

Merge checks verify one H1, unique IDs, local links, unchanged original
interactive scripts, JavaScript syntax, key values and caveats. Browser control
remains unavailable, so no new visual rendering pass is claimed.

## November 10 fact check and enrichment

The homepage now leads with the approximate combined scale of the two main
writing datasets and uses scope-based dataset labels. The 1,413 recorded
abstract matches are against the discovery download list, not necessarily its
9,472 analysed papers: the previous direct-subtraction interpretation is
withdrawn, and no exact unique total is claimed. The evidence JSON field name
has been corrected accordingly; underlying numerical study outputs are intact.

Added a study/question map, official-abstract naming examples, raw name-pattern
counts with denominators, and a narrowly qualified account of the completed
outside-CS follow-up. The new aggregate JSON files are under assets/factcheck/.
Naming shares use approximate whole percentages, avoiding double rounding of
the frozen four-decimal table. Main-contribution filtering, sampling uncertainty,
placebo scope and nonrandom missingness are explicit. External source links were
checked; historical data arrays remain unchanged. Browser control is still
unavailable, so no new desktop/mobile screenshot verification is claimed.
