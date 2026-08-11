# CAMPS — Minor Thesis Part B (s4139514)

**Mitigating Evaluative Epistemic Filtering in LLM-Driven Essay Scoring: A Culturally-Aware Multi-Perspective Scoring (CAMPS) Framework**

| | |
|---|---|
| Student | Bao Nguyen (s4139514), Master of AI, RMIT Vietnam |
| Supervisor | Dr Ginel Dorleon |
| Course | COSC2993 Minor Thesis/Project Part B (coordinator: Dr Thuy Nguyen) |
| Due | **Tue 15 Sep 2026, 17:00** (Canvas, PDF, max 50 A4 pages, 1.5-spaced) |
| Overleaf | https://www.overleaf.com/read/cyydsxmvcnbr#336650 (synced with this repo via GitHub) |

## What the thesis does
LLM essay evaluators trained on predominantly Western text penalise valid non-Western rhetorical styles ("evaluative epistemic filtering"). CAMPS mitigates this at inference time with a panel of five culturally-calibrated evaluator agents plus a meta-adjudicator; inter-agent disagreement (Bias Divergence Score, BDS) flags culturally contested essays for human review. Two research questions, four hypotheses (H1 existence/generality, H2 mitigation, H3 detection, H4 fairness–accuracy cost), three experiments on ICNALE (N=240 manifest; GRA 140×80 raters as human ground truth).

## Repo layout
- `s4139514-Minor_Thesis_Part_B.tex` — root file (**set as Main document in Overleaf**)
- `01-…13-….tex` — numbered to mirror PDF order (cover → bibliography)
- `figures/` — exported figure PDFs + TikZ sources
- `tables/` — Chapter 4 results tables, **auto-generated** by `../Code/src/make_tables.py` from experiment logs (placeholders until experiments run; never edit by hand)
- `main.bib` — verified-only bibliography (every entry checked against DOI/primary source before inclusion)
- `mitthesis.cls` — template from Dr Ginel (do not restructure)

## Build
`pdflatex → bibtex → pdflatex ×2` on the root file. Expected: **0 errors**. Output must be named `s4139514-Minor_Thesis_Part_B.pdf`.

## Status (Week 7 — 12 Aug 2026)
- ✅ Ch1 Introduction — complete (RQ↔H mapping, theoretical framing)
- ✅ Ch2 Literature Review — complete (~25 verified sources, thematic, search method stated)
- ✅ Ch3 Methodology — complete (framework, 5-lens panel, data, E1–E3, alternatives, ethics, metrics)
- ⬜ Ch4 Results & Discussion — skeleton + auto-tables wired; fills as E1–E3 run
- ⬜ Ch5 Conclusion — skeleton (answers H1–H4 in Week 9)
- ✅ Dataset: ICNALE WE 2.6 / WEP 0.7 / GRA 2.1 acquired; manifest frozen (N=240, seed 4139514)
- ✅ Pipeline: `../Code/` (4 providers, t=0, cached, resumable; metrics unit-tested)
- Supervisor review round 1 (7 comments) — resolved

## Plan to submission
| Week | Dates | Milestone |
|---|---|---|
| 7 | 10–16 Aug | Smoke test + **E1** (baseline vs k=3, 4 models) |
| 8 | 17–23 Aug | **E2** (k=5 ± adjudicator, weight sweep) after CRI prompt sign-off |
| 8–9 | 23–30 Aug | **E3** (BDS ROC vs GRA dispersion); **hard experiment cutoff 30 Aug** |
| 9–10 | 31 Aug–6 Sep | Ch4 results prose, Ch5, abstract/summary results; full draft to Dr Ginel **Fri 5 Sep** |
| 10–11 | 7–14 Sep | Revision, page-budget trim, reference audit, Turnitin self-check |
| 12 | **Tue 15 Sep** | Submit + oral presentation prep |

## Conventions
- Australian English (-ise, fulfilment, artefact); calibrated claims; past tense; n with every %, bootstrap CIs over p-values
- Unwritten sections keep lorem + `%% TODO (Week N)`; no invented numbers — pilot figures only as "reported in Part A"
- Commit after every editing session (this repo syncs to Overleaf); **never** commit essay texts or API keys — corpus data lives only in `../Code/data/` (gitignored there)
- AI assistance logged for the course integrity disclosure

## Related repositories and folders
- **Experiment code:** https://github.com/mikenk2010/vs4139514-Final-Thesis-CAMPS-Code — the CAMPS pipeline (sampling, 4-provider runner, metrics, table generation). Local working copy: `../Code/`. Corpus data stays local-only (gitignored) per the ICNALE licence.
- `../CAMPS-Project/` — working plan, meeting minutes, literature notes, admin (OneDrive-mirrored, not on GitHub)
