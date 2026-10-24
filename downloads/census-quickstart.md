# Check the census numbers yourself

This download lets you recompute the main census results on your own computer in about half a minute. You don't need the papers themselves, a GPU or an account anywhere.

**Download:** `census-reproduction.zip` (6.2 MB; it unpacks to about 45 MB)
**SHA-256:** `aa1683a39924fb738b5548bbaf02a20f77a7d9d994afddb31e68705611589b7e`

## Three steps

1. Set up Python and numpy. We tested with **Python 3.12.12 and NumPy 2.5.4**; other versions may work, but we haven't tested them. A pinned setup:
   ```
   python3.12 -m venv venv
   venv/bin/pip install numpy==2.5.4
   ```
   (After entering `supplement`, step 3 uses `../venv/bin/python`; on Windows use `..\venv\Scripts\python.exe`.)
2. Unzip the file and go into the folder:
   ```
   unzip census-reproduction.zip
   cd supplement
   ```
3. Run the check:
   ```
   ../venv/bin/python reproduce.py
   ```
   It finishes in roughly 20–30 seconds on a laptop. If it prints `mismatches: 0` and exits with code 0, every reported numeric estimate and interval matched the published value within the check's tolerance (relative 1e-9, absolute 1e-12) (whole-number counts are compared the same way), and all verdicts and text labels matched exactly.

## What the check recomputes

Starting from one row of numbers per paper (21,306 analysed papers; no text), it reruns the published analysis code and compares its output with the frozen results file:

- **The trend comparison:** how far 2024–25 sits above the extended 2016–22 trend, for ACL and EMNLP, plus NAACL on its own, the placebo years, the before/after difference and the robustness checks (papers not about language models, long/main-track papers, dropping papers that overlap the first study, a trend fitted only through 2021).
- **The same-author comparison:** 762 repeat first authors, the 554-author pre-ChatGPT comparison, and the ORCID, last-author and per-author-cap variants.
- **The 2026 opener comparison:** ACL 2026 against ACL 2025.
- **One extra sensitivity:** the trend result after dropping both the overlapping papers and the 460 papers without a usable abstract.

The comparison includes the 95% intervals, because the package uses the same code and random seeds as the original run. Same code and seeds don't guarantee bit-identical floating-point results on every computer, which is why the check allows a tiny numeric tolerance; it was confirmed on the tested environment above.

## What it does not check

- **It checks the arithmetic; it can't independently confirm it.** The download reruns the original analysis code, so a match shows the published numbers follow from the released rows and code. It can't catch a mistake that is in the code itself. A separate team member reimplemented the analysis independently: every headline estimate matched, but seven interval endpoints in secondary checks fell outside that reimplementation's preset tolerance. Repeat runs with different random seeds are consistent with ordinary resampling noise, but don't prove the two methods are identical, and those seven endpoints are still reported as unresolved.
- **The grammar-parser check is included as a saved result, not recomputed.** `data/parse_results_frozen.json` holds the parser output reported in the article. Rerunning it needs the paper PDFs, the extracted text and spaCy; `code/parse_check.py` shows how it was done.
- **Turning PDFs into numbers is not included.** The per-paper rows are taken as given. The PDFs are public on the ACL Anthology, and `data/receipts.json` lists the SHA-256 of every PDF we downloaded, so you can confirm you have the same files. The extraction itself isn't packaged.
- **The figure script doesn't run from inside the folder.** `code/figures.py` is included for reference; it expects the project's original folder layout.
- **No other studies.** The first 9,472-paper study, the CVPR/ICML/NeurIPS, USENIX and arXiv replications, and the outside-CS study (which has no results yet) are not in this download.
- **Author privacy.** Author names are replaced with opaque ids. Paper ids are public, though, so anyone can look up the bylines; this isn't a privacy guarantee.

## What's inside

| Path | What it is |
|---|---|
| `reproduce.py` | The one-command check |
| `PROTOCOL.md` | The census analysis plan, written before the census text was extracted, with its log of later changes |
| `code/acl_run.py`, `scripts/review_round3/conference/conf_run.py` | The unchanged analysis code |
| `code/parse_check.py`, `code/figures.py` | Parser check and figure code (reference only; see above) |
| `data/paper_rows.json` | Numeric features for all 21,368 papers in the frame (21,306 analysed); no text |
| `data/authors_anon.json` | Opaque author ids for the same-author comparison |
| `data/overlap.json`, `data/abstractless_ids.json` | Papers shared with the first study, and the 460 without a usable abstract |
| `data/receipts.json` | SHA-256 of every downloaded PDF |
| `data/results_frozen.json`, `data/parse_results_frozen.json`, `data/supplementary_frozen.json` | The published results the check compares against |

These are observational counts of wording patterns in published papers. They describe groups of papers, not how any individual paper was written.
