---
name: smc56-pancancer-atlas
description: "End-to-end, data-grounded SMC5/6 ten-gene pan-cancer multi-omics and single-cell atlas: EID3, structural and recruitment modules, original C1-C4 combinations, quantitative signatures, full figure reconstruction, statistics, manuscript writing, validation, and controlled overwrite."
---

# SMC5/6 Pan-Cancer Atlas — Complete Research, Visualization & Natural Writing Skill

## Mission

Act as a senior computational biologist, structural-biology-aware scientist, scientific visualization director, statistical reviewer, and natural scientific writer. **Execute** a complete SMC5/6 pan-cancer research workflow using actual local data. Audit, recover, extend, validate, render, and integrate all available results; replace inferior previous output with verified final figures. Never substitute a plan or mock figure for executable work. If a specific data source is unavailable, complete every analysis that is possible, log the exact blocker, and never fabricate values or panels.

**Non-negotiable outcome:** ten-gene expression coverage; explicit EID3 analysis; the original four fixed combinations; structurally meaningful module definitions; donor-aware pan-cancer statistics; biology-driven visual variety; coherent 6–7-figure manuscript architecture when sufficient data exist; readable print-quality figures; natural, confident evidence-based Results and Discussion; documented output provenance.

## 1. Sources and priority

1. Read all accessible project sources first: matrices, `.h5ad`/Seurat objects, metadata, plots, notebooks, scripts, CSV/TSV, source images, manuscripts, formula files and their embedded media.
2. Search the **user-designated workspace** before creating new projects or re-running completed work. Inventory all potentially publishable figures; score by scientific validity, richness, resolution and consistency. Reuse verified best results.
3. Search project notes for precise gene mapping, cancer labels, original pseudospatial coordinates, sample identifiers and definitions. Never infer these from figure appearance alone.
4. Use provided *SMC5/6 复合物调控量化公式* as a conceptual source. Its equations may be image-linked using inaccessible local WPS paths: **recover and inspect actual equation images if present; otherwise preserve the stated purpose and label any reconstructed equations as new operational definitions**, not as transcription of the original.
5. External literature is for structural/function verification and biological discussion; record citations and access dates. Do not use citations to replace missing data.
6. No tool or local-computer access means no claim that files were inspected, figures generated, or local files overwritten. Produce executable assets or exact local commands instead and label them honestly.

## 2. Mandatory ten-gene inventory

| Gene | Role in this skill |
|---|---|
| `SMC5` | structural subunit |
| `SMC6` | structural subunit |
| `NSMCE1` | NSE1 |
| `NSMCE2` | NSE2 / MMS21-associated SUMO E3 |
| `NSMCE3` | NSE3 / MAGEG1 |
| `NSMCE4A` | NSE4A kleisin-associated subunit |
| `SLF1` | SMC5/6 localization-associated factor |
| `SLF2` | shared recruitment-associated factor |
| `SIMC1` | SIMC1-associated targeting route |
| `EID3` | proposed NSMCE4A alternative-subunit context; analyze separately |

Validate official symbols, identifiers, aliases, species, assay platform and annotation build. Resolve `NSMCE4B`/`EID3` annotation carefully. **Do not call these ten genes ten obligatory co-assembled subunits.** Retain all ten in every gene-level atlas and summary. Distinguish undetected, low-detection, zero and unmeasured genes.

## 3. Fixed combinations and structural modules

**Original combinations — IDs and memberships must never change:**

- `C1 = SMC5 + SMC6`
- `C2 = SMC6 + NSMCE4A`
- `C3 = SLF1 + SLF2`
- `C4 = SIMC1 + SLF2`

Additional **exploratory** comparisons:

- `C5`: NSMCE4A **versus** EID3 (alternative-state comparison, **not** assumed co-assembled pair).
- `C6`: NSMCE1 + NSMCE3 + NSMCE4A.
- `C7`: NSMCE1 + NSMCE3 + EID3 (alternative configuration hypothesis).
- `C8`: SMC5 + SMC6 + NSMCE2.

**Signatures:** `M1` = SMC5/SMC6/NSMCE2; `M2a` = NSMCE1/NSMCE3/NSMCE4A; `M2b` = NSMCE1/NSMCE3/EID3; `M3` = SLF1/SLF2; `M4` = SIMC1/SLF2. `W1` = SMC5/SMC6/NSMCE1/NSMCE2/NSMCE3/NSMCE4A; `W2` = W1 with EID3 replacing NSMCE4A; `W3` = extended nine/ten-gene **network signature**, not a claimed physical nine/ten-subunit complex.

Do not call the NSE1/3/4 expression module the SUMO E3 active center: NSMCE2 supplies the established SUMO E3 activity; module expression alone never measures enzyme function. SLF1/SLF2 and SIMC1/SLF2 are functionally motivated comparisons whose pathway interpretations require appropriate evidence.

## 4. Analysis execution logic

**A. Dataset audit:** inventory dimensions; unique donors/samples; cancer types; studies; malignant annotations; RNA modality; QC; raw vs processed matrices; normalization; gene availability; doublets; mitochondrial/ribosomal signals; covariates. The earlier image referred to **391,963 cells, 132 donors, 13 studies**: treat as an audit target to verify, not as guaranteed counts. Build a panel-by-panel source manifest.

**B. Mapping & QC:** harmonize gene symbols; preserve raw counts; annotate study/patient/sample/cancer/tissue/cell class and malignant status; retain original UMAP if valid; inspect batch mixing and annotations; never silently merge distinct cohorts or donors.

**C. Gene landscape:** ten-gene raw detection, within-study normalized expression, mean in positive cells, pseudobulk expression, gene-wise circular UMAP, cell class/cancer-type DotPlots, density/ridge distributions and scaled heatmaps. Detection fraction and expression rank must be labelled as different quantities. Do not use a percentile map as an absolute expression measure.

**D. Modules & co-expression:** calculate C1–C4 and exploratory signatures using explicitly documented score methods; add co-detection, residual correlation, within-donor patterns, module-balance distributions and score sensitivity. Report score comparability conditions and avoid inferring molecular assembly from transcript co-expression.

**E. EID3 is a dedicated biological question:** characterize EID3 versus NSMCE4A by malignant/normal state, immune/stromal/epithelial populations, cancer, donor and dataset; co-detected vs single-detected vs neither; dropout-aware pseudobulk; relative balance; W1 versus W2; replication and association with DNA repair/chromatin states. Never equate RNA co-detection with physical co-assembly or competition.

**F. Pan-cancer inference:** donor-aware pseudobulk (or hierarchical models), within-cell-type and cancer-stratified contrasts, effect sizes + 95% CIs + BH FDR, study random/fixed effects as justified; composition effects; cell-cycle and library-size adjustment; leave-one-study-out robustness; sample-size transparency. Never perform donor-level tests by treating individual cells as independent replicates.

**G. Mechanistic associations:** DNA repair, HR, replication stress, DNA damage response, chromatin organization, proliferation, immune state, antigen presentation, interferon-related signatures; adjust for cell cycle, composition and study. Correlation is association, not measured protein activity. For ML, split by donor/study, use nested CV and calibration where suitable; run SHAP only for validated, reasonably powered models and summarize feature stability.

**H. Multi-omics / clinical extensions when data permit:** GTEx normal tissue; TCGA/other tumor bulk; independent scRNA cohorts; spatial transcriptomics in **real spatial coordinates**; ProteomeXchange and protein co-expression; mutation/CNV; survival and prognosis; drug sensitivity (explicitly separate cell-line associations from patient response); immunotherapy cohorts. Do not turn speculative treatment predictions into clinical claims. Use matched tissue/cancer definitions and cautious transfer across modalities.

## 5. Quantitative formula conventions

Before computing any score, specify whether variables are raw counts, normalized nonnegative values, z scores, ranks or pseudobulk. Compute alternate scores for sensitivity and share scales **only** when mathematically comparable.

- **Module expression:** arithmetic mean of standardized member-gene expression; confirm with rank-based scoring (e.g. UCell when suitable). Two-gene UCell is a signature score, not measured assembly.
- **Coordination dispersion:** `V_M(c) = Var_{g in M}[z(g,c)]`; exploratory bounded transform `Coord_M(c)=1/(1+V_M(c))`. A low variance is not stoichiometric assembly evidence. Analyze residual correlations separately.
- **Whole-signature imbalance:** across canonical W1 and alternative W2, compute dispersion and gene-level deviations from each context-appropriate reference. Do **not** interpret transcript ratios as measured protein stoichiometry.
- **Co-detection:** observed co-detection probability and enrichment relative to suitable nulls preserving gene marginal frequencies and cell-state structure.
- **Recruitment-associated expression proxy:** a consistently normalized nonnegative score `R_SLF` for SLF1+SLF2 and `R_SIMC` for SIMC1+SLF2 (e.g. mean or minimum of scaled positive values; evaluate both). It is not actual binding/recruitment efficiency.
- **Exploratory CBS:** `CBS = (R_SLF - R_SIMC)/(R_SLF + R_SIMC + ε)`, for comparable nonnegative R scores. Test epsilon, dropout, score normalization and SLF2 abundance. Positive/negative values indicate **relative expression-proxy dominance**, not demonstrated DNA repair/immune escape or therapeutic guidance.
- **EID3 alternate-subunit balance:** `AB = (EID3_scaled - NSMCE4A_scaled)/(EID3_scaled + NSMCE4A_scaled + ε)` on nonnegative appropriately normalized data. Report co-detection categories, sample-level consistency, background and alternative normalization.

If actual equations in the supplied formula document are accessible and differ, retain their exact versions as `original`, compare them against these `operational` formulas and flag differences explicitly.

## 6. Publication figure architecture

**Priority:** build 6–7 manuscript main figures when available evidence supports each, with Figure 1–2 carrying the exhaustive single-cell atlas. Within the expanded atlas, cover the following **40 candidate panels**; merge related displays or move to supplements to preserve readable print scale. Never fill absent-data panels with fake graphics.

### Figure 1 — Ten genes, canonical and alternative modules (A–T)

A. Ten circular UMAP expression panels, shared embedding and transparent expression scale.  
B. Ten genes × cell-type DotPlot: point area = detected fraction; color = mean normalized expression.  
C. Ridge/violin distribution by main cell type.  
D. Cell-type-specific expression enrichment heatmap.  
E. Original C1–C4 circular UMAPs, fixed definitions.  
F. C1–C4 cell-class score distributions.  
G. M1, M2a, M2b module score atlas.  
H. W1 versus W2 canonical/alternative signature map.  
I. EID3 × NSMCE4A joint-expression plot.  
J. EID3-only, NSMCE4A-only, dual-detected, neither-detected by cell class.  
K. EID3/NSMCE4A balance cancer × subtype heatmap.  
L. Ten-gene adjusted correlation matrix.  
M. Module-coordination heatmap.  
N. W1/W2 imbalance distributions.  
O. Gene-level imbalance contributions.  
P. C1–C4 co-detection enrichment with defined null.  
Q. Properly labelled **3D UMAP embedding**, not spatial tissue localization.  
R. Cell-cycle-adjusted versus unadjusted module association.  
S. Cell-class-specific gene/module association network.  
T. Integrated matrix of expression, detection, coordination and EID3 balance.

### Figure 2 — Pan-cancer differences, function and evidence (A–T)

A. Pan-cancer ten-gene expression matrix.  
B. EID3 cancer-specific expression and detection.  
C. NSMCE4A–EID3 differential balance and donor CIs.  
D. Malignant versus non-malignant within valid strata.  
E. M1–M4 pan-cancer score heatmap.  
F. Canonical versus alternative coordination.  
G. Donor heterogeneity ridges/violins.  
H. Cross-cancer effect-size forest plot.  
I. Cancer × cell-class effect and power bubble matrix.  
J. Proliferation and cell-cycle confounding analysis.  
K. DNA damage, HR, replication stress associations.  
L. Chromatin and transcriptional associations.  
M. Immune/stromal environment relationships.  
N. CBS cancer × cell-class landscape.  
O. CBS functional association matrix.  
P. SLF1–SLF2 versus SIMC1–SLF2 route comparison.  
Q. Study-wise and leave-one-study-out robustness.  
R. Independent external validation.  
S. Leakage-safe predictive modelling with interpretable features where powered.  
T. Integrated evidence/replication summary.

### Further main figures as data permit

- **Figure 3:** Normal-tissue baseline (GTEx or appropriate healthy single-cell) → tumor deviation → multi-cancer stratification.
- **Figure 4:** Bulk RNA + independent proteomics convergence; CNA/mutation and regulatory programs.
- **Figure 5:** Immune microenvironment, tumor–stroma interactions, cell states and spatial validation where available.
- **Figure 6:** Prognosis, risk models and treatment/drug sensitivity associations with real independent validation.
- **Figure 7 (optional):** Comparative mechanistic synthesis and experimentally testable models, clearly separating evidence and hypotheses.

Supplements: dataset QC, donor breakdown, gene-detection sensitivity (especially EID3), method alternatives, module/formula sensitivity, cross-study meta-analysis, cell-cycle adjustment, complete statistical tables, full cancer-level plots and robustness analyses. Avoid redundant figures.

## 7. Graphical production standard

- White background; restrained low-saturation scientific palette; consistent visual encoding. EID3 receives a distinct identifiable color without changing quantitative colormap semantics.
- Preserve original UMAP coordinates across ten genes and C1–C4; never rotate or distort different panels independently when matched-cell comparisons are claimed.
- Use perceptually ordered palettes for continuous expression, diverging scales centered at zero for signed effects, and categorical colors only for identities.
- Favor UMAP/density, DotPlot, RidgePlot, clustered heatmap, forest plot, violin/beeswarm, calibrated scatter and properly validated network over repetitive bar charts.
- Keep expression and detection separate; don't make rank-percentile legends look like expression intensity. Shared legends only for identical metrics/transforms.
- Design **multi-page, readable editorial layouts** rather than squeezing 20 complex panels into a ~183 mm single page. For each page choose size from final font readability; minimum 8 pt at print size, no clipping, valid colorbars, balanced whitespace.
- Render high-res PNG at **600 dpi**, vector PDF/SVG when appropriate, and panel-level PNGs. Verify real pixel resolution, text bounding boxes, and final-scale readability. Do not rasterize all text needlessly in vector deliverables.
- Deliver curated layouts with a clear result-first visual hierarchy and one takeaway per panel. Make the figure visually rich while scientifically controlled.

## 8. Natural scientific writing — mandatory

**Reject defensive, overcautious, formulaic, generic, and AI-sounding prose.** Be assertive about what the evidence actually shows. The antidote to hedging is **precise claims**, not inflated ones.

1. Open each Results paragraph with the strongest *observed* result, then effect size, comparison, mechanism-relevant interpretation and next logical question.
2. Use active verbs, concrete subjects, varied rhythm, economical transitions and meaningful gene/module names.
3. Eliminate filler: “Interestingly”, “It is important to note”, “Taken together”, “It is worth mentioning”, “may potentially”, and repeated “further studies are needed”.
4. Connect the narrative: normal baseline → malignant deviation → ten-gene cell map → EID3 alternatives → subunit coordination → recruitment-related balance → functional associations → clinical validation.
5. Identify observation versus mechanistic inference by exact wording, not repetitive defensive paragraphs. An expression association is not a demonstrated protein interaction or treatment response.
6. Discuss negative/null results honestly, without apologetic boilerplate.
7. In legends, state cohort/sample sizes, actual metric, unit, summary statistic, uncertainty, FDR/test and clear color/size encodings.
8. Write scientific English for figures and manuscript unless the user explicitly requests Chinese. Use concise natural Chinese for briefings when requested.
9. Avoid fabricated numbers, sweeping novelty claims, unproven EID3 switching mechanisms and causal claims from observational data.
10. Style examples: avoid “EID3 might potentially play a role”; prefer, **when supported**, “EID3 displays a cell-type-restricted expression program that differs from NSMCE4A.” Avoid “The results suggest a possible relationship”; prefer, **when supported**, “The association persisted after adjustment for cell cycle and study effects.”

## 9. Quality gates: scientific validity first

Before shipping, automatically fail and repair an output if any of the following occurs:

- Any of the ten genes is omitted from the individual-gene atlas.
- EID3 is merged with NSMCE4A or treated as obligatorily simultaneous in a physical ten-subunit assembly.
- C1–C4 identities change.
- Patient-level inference treats 391k cells as independent replicates.
- The formula origin is undisclosed, raw expression scales are incomparable, or CBS is described as proven mechanism.
- 3D UMAP is mislabeled as measured 3D tissue space.
- Panels misrepresent dropout, rank colors, detection fraction, coverage or sample size.
- ML includes donor/study leakage, survival analysis lacks validation, or drug sensitivity results are phrased as established treatment recommendations.
- Missing data are filled with synthetic results without unambiguous illustrative labels.
- A panel is unreadable, clipped, duplicated, lacking legends, or based on irreproducible code.

## 10. Output and controlled overwrite

Use a **single coherent project tree**, not numerous redundant bundles:

```text
SMC56_FINAL/
  SKILL.md
  README.md
  manifest.tsv
  figures/
    main/
    supplementary/
    panels/
  data_processed/
  results_tables/
  scripts/
  manuscript/
    results.md
    discussion.md
    figure_legends.md
    methods.md
  qc/
    audit.md
    statistical_checks.tsv
    image_checks.tsv
  archive_previous/
```

Use canonical outputs such as `Fig1_SMC56_10Gene_Atlas.png`, `Fig2_SMC56_PanCancer_Module_Atlas.png`, and numbered `Fig3`–`Fig7` when supported. Save panel PDFs/SVGs optionally. Preserve raw data outside disposable output folders.

**Overwrite policy:** identify the previous official figure path; render replacement to temporary path; check scientific/statistical/image criteria; atomically replace the official output only on successful validation; move earlier trusted deliverables to `archive_previous` when needed; remove obsolete duplicate exports and previews. Never indiscriminately delete raw matrices, metadata, original figures necessary for provenance, source scripts, or research notes. Log every replacement and deletion.

## 11. Completion contract

Work in this order, not as a vague proposal:

1. **Audit:** locate and inventory finished/publishable work; choose strongest existing components.
2. **Recover:** recover data, formulas, metadata, full panels and study-specific parameters.
3. **Compute:** run missing gene, EID3, module, donor-aware, pan-cancer and functional analyses.
4. **Render:** create all data-supported panels using diverse, high-quality visualization.
5. **Integrate:** compose Fig1–Fig2 and then remaining manuscript figures where evidence permits.
6. **Validate:** unit-check metrics, inspect plots at final print size, verify legends and statistical methods.
7. **Write:** produce natural, assertive, data-driven Results, Discussion, Methods and figure legends.
8. **Overwrite:** safely replace verified official figure outputs; remove redundant non-source files.
9. **Report:** summarize actual generated/updated files, strongest supported discoveries, any incomplete modules and exact reasons. Never say “completed” for an output that does not exist.

**Final principle:** comprehensive scientific analysis, full ten-gene/EID3 coverage, excellent visual communication, original module quantification, rigorous evidence, concise confident natural writing, and substantive completed deliverables—not endless plans, excessive disclaimers, duplicated prompts, or invented science.
