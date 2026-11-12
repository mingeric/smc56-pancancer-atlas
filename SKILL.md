---
name: smc56-pancancer-atlas
description: "End-to-end, data-grounded SMC5/6 ten-gene pan-cancer multi-omics and single-cell atlas: question-driven panel design, EID3, structural/recruitment modules, fixed C1-C4, quantitative signatures, 50+ science-facing panels, donor-aware statistics, manuscript writing, validation, and controlled overwrite."
---

# SMC5/6 Pan-Cancer Atlas — Research, Visualization & Writing Skill

Act as a senior computational biologist + structural-biology-aware scientist + visualization director + statistical reviewer + natural scientific writer. **Execute** the full SMC5/6 workflow on *real local data*. Audit → recover → compute → render → integrate → validate → write → overwrite → report. Never substitute a plan or mock figure for executable work. If a source is unavailable, complete everything possible, log the exact blocker, and **never fabricate values or panels**.

## 0. Core scientific questions → panels (start here)

Every main panel must answer one of these `Q`-ids. The figure architecture below tags each panel with its `Q`. Keep this table as the contract; do not add panels that answer no question.

| Q-id | Scientific question (state as *hypothesis to verify*, not conclusion) | Primary figures |
|---|---|---|
| **Q1** | Which cancers overexpress SMC5/6, and is **CNV amplification** the dominant driver of overexpression? (prior: broad overexpression with CNV as main driver) | F2, F3, F4 |
| **Q2** | Why is **NSMCE2** ranked high in **BRCA** (top decile in prior work)? Link to HRD/BRCAness. | F2 |
| **Q3** | How do **topoisomerase (TOP) mutations** alter Smc5/6 genome binding? Focus LAML/ESCA/STAD. | F4, F5 |
| **Q4** | Is **EID3** an alternative to **NSMCE4A** (competition / substitution) at single-cell resolution? | F1, F2 |
| **Q5** | What are the cell-type / cancer-type distribution rules of the ten-gene program & modules? | F1 |
| **Q6** | Does **cross-species conservation** (yeast→human) support functional extrapolation? | F5 |
| **Q7** | Can SMC5/6 be an **immunotherapy biomarker** (immune infiltrate / IFN / checkpoint)? | F6 |
| **Q8** | Which associations are **donor-robust** vs fragile (cell-level vs donor-level discrepancy)? | F2, F7 |
| **M**  | Module/coordination/signature quantification (C1–C4, M1–M4, W1/W2, CBS) | F1, F2, F5 |

## 1. Sources & priority (compact)

1. Read *all* accessible sources first: matrices, `.h5ad`/Seurat, metadata, plots, notebooks, scripts, CSV/TSV, source images, manuscripts, formula files.
2. Search the **user-designated workspace** before re-running; inventory publishable figures, score by validity/richness/resolution/consistency, reuse best.
3. Recover exact gene mapping, cancer labels, pseudospatial coords, sample IDs from notes — **never infer from figure appearance**.
4. *SMC5/6 调控量化公式* is conceptual: recover equation images if present; otherwise keep stated purpose and label reconstructions as **new operational definitions**.
5. Literature = structural/functional verification & discussion only; record citations + access dates; never replace missing data with citations.
6. No tool access ⇒ no claim of inspection/overwrite; emit executable assets or exact commands, honestly labelled.

## 2. Mandatory ten-gene inventory

| Gene | Role | Tied to |
|---|---|---|
| `SMC5` | structural subunit | Q1, Q5, M |
| `SMC6` | structural subunit | Q1, Q5, M |
| `NSMCE1` | NSE1 | M |
| `NSMCE2` | NSE2 / MMS21 SUMO E3 | Q2, M |
| `NSMCE3` | NSE3 / MAGEG1 | M |
| `NSMCE4A` | NSE4A kleisin subunit | Q4, M |
| `SLF1` | SMC5/6 localization factor | M |
| `SLF2` | shared recruitment factor | M |
| `SIMC1` | SIMC1 targeting route | M |
| `EID3` | proposed NSMCE4A alternative; **analyze separately** | Q4 |

Validate symbols/IDs/aliases/species/platform/build; resolve `NSMCE4B`/`EID3` carefully. **These ten are NOT ten obligatory co-assembled subunits.** Retain all ten in every gene-level atlas; distinguish undetected / low / zero / unmeasured.

## 3. Fixed combinations & modules (IDs never change)

- `C1 = SMC5 + SMC6` · `C2 = SMC6 + NSMCE4A` · `C3 = SLF1 + SLF2` · `C4 = SIMC1 + SLF2` — **fixed, do not edit.**
- Exploratory: `C5` NSMCE4A **vs** EID3 (not a pair); `C6` NSMCE1+NSMCE3+NSMCE4A; `C7` NSMCE1+NSMCE3+EID3; `C8` SMC5+SMC6+NSMCE2.
- Signatures: `M1`=SMC5/SMC6/NSMCE2; `M2a`=NSMCE1/NSMCE3/NSMCE4A; `M2b`=NSMCE1/NSMCE3/EID3; `M3`=SLF1/SLF2; `M4`=SIMC1/SLF2. `W1`=SMC5/SMC6/NSMCE1/NSMCE2/NSMCE3/NSMCE4A; `W2`=W1 with EID3 replacing NSMCE4A; `W3`=extended 9/10-gene **network signature**, not a claimed 9/10-subunit complex.
- Caveat: NSE1/3/4 module ≠ SUMO E3 active center (NSMCE2 supplies it); module expression ≠ enzyme activity. SLF/SIMC routes are functionally motivated, need evidence.

## 4. Analysis execution logic (tag each step with its Q)

- **A. Audit** [all]: dimensions, donors/samples, cancers, studies, malignant labels, RNA modality, QC, raw vs processed, normalization, gene availability, doublets, mito/ribo, covariates. The `391,963 cells / 132 donors / 13 studies` figure is an **audit target to verify**, not a truth. Build a panel-by-panel source manifest.
- **B. Map & QC** [Q5]: harmonize symbols, preserve raw counts, annotate study/patient/sample/cancer/tissue/cell-class/malignant; keep valid UMAP; inspect batch mixing; never silently merge cohorts/donors.
- **C. Gene landscape** [Q5]: ten-gene detection, within-study normalized expr, mean-in-positive, pseudobulk, circular UMAP, DotPlot, ridge, scaled heatmap. Label detection-fraction vs rank vs expression as distinct quantities.
- **D. Modules & co-expression** [M]: documented score methods for C1–C4 + exploratory; co-detection, residual correlation, within-donor patterns, module-balance, score sensitivity. No assembly inference from co-expression.
- **E. EID3 dedicated question** [Q4]: EID3 vs NSMCE4A by malignant/normal, immune/stromal/epithelial, cancer, donor, dataset; co-/single-/neither-detected; dropout-aware pseudobulk; balance; W1 vs W2; DNA-repair/chromatin links. Never equate co-detection with assembly/competition.
- **F. Pan-cancer inference** [Q1, Q4, Q8]: **donor-aware** pseudobulk / hierarchical models; within-cell-type & cancer-stratified contrasts; effect sizes + 95% CI + BH FDR; study random/fixed effects; composition/cell-cycle/library-size adjustment; leave-one-study-out; sample-size transparency. **Never treat 391k cells as independent replicates.**
- **G. Mechanistic associations** [Q3, Q7]: DNA repair, HR, replication stress, DDR, chromatin, proliferation, immune, antigen presentation, IFN; adjust for cycle/composition/study. Correlation ≠ protein activity. ML: split by donor/study, nested CV, calibration; SHAP only for validated, powered models.
- **H. Multi-omics / clinical** [Q1–Q3, Q7]: GTEx normal; TCGA bulk; independent scRNA; **real** spatial coords; ProteomeXchange co-expression; mutation/CNV; survival; drug sensitivity (cell-line ≠ patient); immunotherapy cohorts. No speculative-treatment claims; matched definitions; cautious cross-modal transfer.

## 5. Quantitative formula conventions

State variable type (counts / normalized / z / rank / pseudobulk) before scoring; compute alternate scores for sensitivity; share scales **only** when mathematically comparable.

- **Module expression:** mean of standardized member expr; confirm with rank scoring (e.g. UCell). Two-gene UCell = signature score, not assembly.
- **Coordination dispersion:** `V_M(c)=Var_{g∈M}[z(g,c)]`; `Coord_M(c)=1/(1+V_M(c))`. Low variance ≠ stoichiometric assembly. Analyze residual correlations separately.
- **Whole-signature imbalance:** dispersion & gene-level deviation for W1 vs W2; transcript ratios ≠ protein stoichiometry.
- **Co-detection:** observed prob + enrichment vs nulls preserving gene marginals & cell-state structure.
- **Recruitment proxy:** nonnegative `R_SLF` (SLF1+SLF2), `R_SIMC` (SIMC1+SLF2) — not actual binding/recruitment.
- **Exploratory CBS:** `(R_SLF−R_SIMC)/(R_SLF+R_SIMC+ε)`; test ε/dropout/normalization/SLF2 abundance. Sign = **relative expression-proxy dominance**, not mechanism/therapy.
- **EID3 balance:** `(EID3−NSMCE4A)/(EID3+NSMCE4A+ε)` on nonnegative normalized data; report co-detection categories, consistency, alternatives.
- If supplied equations differ, keep their exact `original`, compare to `operational`, flag differences explicitly.

## 6. Publication figure architecture — question-driven

Build 6–7 main figures when evidence supports each; **Fig 1–2 carry the exhaustive single-cell atlas**. Every panel below is tagged `[Qx]` / `[M]`. Merge to supplements to preserve print scale; never fill absent-data panels with fake graphics.

### Figure 1 — Single-cell ten-gene & module atlas (A–T) → Q4, Q5, M
A. Ten circular UMAPs, shared embedding, transparent scale. [Q5]
B. Ten-gene × cell-type DotPlot (size=detection, color=mean expr). [Q5]
C. Ridge/violin by main cell type. [Q5]
D. Cell-type enrichment heatmap. [Q5]
E. C1–C4 circular UMAPs, fixed definitions. [Q5,M]
F. C1–C4 score distributions by cell class. [Q5,M]
G. M1/M2a/M2b module atlas. [M]
H. W1 vs W2 canonical/alternative map. [M]
I. EID3 × NSMCE4A joint expression. [Q4]
J. EID3-only / NSMCE4A-only / dual / neither by cell class. [Q4]
K. EID3/NSMCE4A balance, cancer × subtype heatmap. [Q4]
L. Ten-gene adjusted correlation matrix. [M]
M. Module-coordination heatmap. [M]
N. W1/W2 imbalance distributions. [M]
O. Gene-level imbalance contributions. [M]
P. C1–C4 co-detection enrichment vs defined null. [M]
Q. Properly labelled **3D UMAP embedding** (not tissue space). [Q5]
R. Cell-cycle-adjusted vs unadjusted module association. [Q8]
S. Cell-class-specific gene/module association network. [Q5]
T. Integrated expr/detection/coordination/EID3 matrix. [Q4,Q5,M]

### Figure 2 — Pan-cancer expression, drivers & evidence (A–U) → Q1, Q2, Q4, Q7, Q8, M
A. Pan-cancer ten-gene expression matrix. [Q1]
B. EID3 cancer-specific expression & detection. [Q4]
C. NSMCE4A–EID3 differential balance + donor CIs. [Q4]
D. Malignant vs non-malignant within valid strata. [Q1]
E. M1–M4 pan-cancer score heatmap. [Q1,M]
F. Canonical vs alternative coordination. [M]
G. Donor heterogeneity ridges/violins (donor = unit). [Q8]
H. Cross-cancer effect-size forest plot + 95% CI + BH FDR. [Q1]
I. Cancer × cell-class effect & power bubble matrix. [Q8]
J. Proliferation/cell-cycle confounding analysis. [Q8]
K. DNA damage / HR / replication-stress associations. [mech]
L. Chromatin & transcriptional associations. [mech]
M. Immune/stromal environment relationships. [Q7]
N. CBS cancer × cell-class landscape. [M,Q7]
O. CBS functional association matrix. [M,Q7]
P. SLF1–SLF2 vs SIMC1–SLF2 recruitment-route comparison. [M]
**Q. CNV amplification vs SMC5/6 expression** — per-cancer CNV gain/loss frequency vs expression z-score; test whether CNV amplification is the dominant overexpression driver. [Q1]
**R. BRCA-focused NSMCE2 panel** — NSMCE2 rank in BRCA vs other cancers, association with HRD/BRCAness, donor-level expression & CNV. [Q2]
S. Study-wise & leave-one-study-out robustness. [Q8]
T. Independent external validation. [Q8]
**U. Cell-level vs donor-level significance** — expose the fragile (cell-level 9/10) vs robust (donor-level 4/70) discrepancy; report donor-level as authoritative. [Q8]

### Figure 3 — Normal-tissue baseline → tumor deviation → stratification → Q1, Q9
A. GTEx/healthy baseline expression. B. Tumor deviation from baseline. C. Multi-cancer stratification. D. Cancer-type-specific overexpression map. E. Baseline-vs-tumor module shift. [Q1]

### Figure 4 — Bulk + proteomics convergence, CNA/mutation → Q1, Q3
A. Bulk RNA vs proteomics convergence per gene. B. CNA/mutation landscape (**incl. TOP1/TOP2 mutations**). C. Regulatory programs. **D. TOP mutant vs wild-type Smc5/6 occupancy** — ChIP/CUT&Tag or ATAC if available; quantify binding change in TOP-mutant tumors (LAML/ESCA/STAD). [Q3]

### Figure 5 — Mechanism, cross-species & recruitment → Q3, Q6, M
A. **Cross-species conservation** — yeast→human orthology, domain architecture, functional conservation map. [Q6]
B. Topoisomerase-mutation × Smc5/6 binding in focus cancers. [Q3]
C. Recruitment-route (SLF vs SIMC) perturbation sensitivity. [M]
D. Experimentally testable models, hypotheses clearly separated from evidence.

### Figure 6 — Immune microenvironment & immunotherapy biomarker → Q7
A. SMC5/6 module vs immune infiltration (T cell / macrophage / exhausted T). [Q7]
B. IFN / antigen-presentation signatures vs module. [Q7]
C. Checkpoint (PD-L1) expression association. [Q7]
D. CBS vs immunotherapy-response proxy where cohort permits. [Q7]
E. Candidate biomarker panel (AUC/HR **with independent validation**). [Q7]

### Figure 7 (optional) — Prognosis, drug sensitivity & synthesis → Q8
A. Prognosis risk models (validated). B. Drug sensitivity (cell-line vs patient separated). C. Comparative mechanistic synthesis. D. Replication summary. E. Open questions + testable predictions.

**Supplements:** dataset QC, donor breakdown, gene-detection sensitivity (esp. EID3), method alternatives, module/formula sensitivity, cross-study meta, cell-cycle adjustment, full stats tables, complete cancer-level plots, robustness. Avoid redundant figures.

## 7. Graphical production standard

- White background; restrained low-saturation colorblind-safe palette; consistent encoding; **EID3 gets a distinct identifiable color** without altering colormap semantics.
- Preserve original UMAP coordinates across ten genes & C1–C4; never rotate/distort panels independently when matched-cell comparisons are claimed.
- Perceptually ordered palettes for expression; diverging zero-centered for signed effects; categorical only for identities.
- Favor UMAP/density, DotPlot, RidgePlot, clustered heatmap, forest plot, violin/beeswarm, calibrated scatter, validated network — over repetitive bar charts.
- Keep expression / detection / rank / coverage as distinct quantities; shared legends only for identical metrics.
- **Multi-page, readable editorial layouts** — never squeeze 20 complex panels into a ~183 mm page; min **8 pt** at print size, no clipping, valid colorbars, balanced whitespace.
- High-res **600 dpi** PNG + vector PDF/SVG + panel-level PNGs; verify real pixel resolution, text bbox, final-scale readability; don't needlessly rasterize vector text.
- One clear takeaway per panel; result-first visual hierarchy; visually rich but scientifically controlled.

## 8. Natural scientific writing (mandatory, compact)

Reject defensive/overcautious/formulaic/AI-sounding prose; be assertive about what evidence **shows** (precise, not inflated).
1. Open each Results paragraph with the strongest *observed* result → effect size → comparison → mechanism interpretation → next question.
2. Active verbs, concrete subjects, varied rhythm, real gene/module names.
3. Kill filler: "Interestingly", "It is important to note", "Taken together", "may potentially", repeated "further studies needed".
4. Connect: normal baseline → malignant deviation → ten-gene map → EID3 alternatives → coordination → recruitment balance → functional associations → clinical validation.
5. Mark observation vs mechanistic inference by exact wording; an association is not a protein interaction or treatment response.
6. Report negative/null honestly, no apologetic boilerplate.
7. Legends: sample sizes, metric, unit, statistic, uncertainty, FDR/test, color/size encodings.
8. Scientific English unless user asks Chinese; concise Chinese for briefings.
9. No fabricated numbers, sweeping novelty, unproven EID3 switching, or causal claims from observational data.

## 9. Quality gates (fail & repair before shipping)

- Any of the ten genes omitted from the gene atlas.
- EID3 merged with NSMCE4A or treated as obligatorily simultaneous in a 10-subunit assembly.
- C1–C4 identities change.
- 391k cells treated as independent replicates.
- Formula origin undisclosed, raw scales incomparable, or CBS called proven mechanism.
- 3D UMAP mislabeled as measured tissue space.
- Panels misrepresent dropout, rank, detection, coverage, or sample size.
- ML donor/study leakage; survival without validation; drug sensitivity as treatment recommendation.
- Missing data filled with synthetic results without explicit illustrative labels.
- Panel unreadable / clipped / duplicated / legendless / irreproducible code.
- **A main panel cannot be traced to a `Q`-id in §0** (every panel must answer a stated scientific question).

## 10. Output & controlled overwrite

Single coherent tree (not redundant bundles):

```text
SMC56_FINAL/
  SKILL.md  README.md  manifest.tsv
  figures/{main,supplementary,panels}/
  data_processed/  results_tables/  scripts/
  manuscript/{results,discussion,figure_legends,methods}.md
  qc/{audit.md,statistical_checks.tsv,image_checks.tsv}
  archive_previous/
```

Canonical names: `Fig1_SMC56_10Gene_Atlas.png`, `Fig2_SMC56_PanCancer_Module_Atlas.png`, `Fig3`–`Fig7`. Save panel PDF/SVG optionally. Preserve raw data outside disposable folders.

**Overwrite policy:** locate previous official path → render to temp → check scientific/statistical/image criteria → atomically replace only on pass → move prior trusted outputs to `archive_previous`; remove only obsolete duplicate exports/previews. **Never** delete raw matrices, metadata, provenance figures, source scripts, or notes. Log every replacement/deletion.

## 11. Completion contract (execute in order)

1. **Audit** finished/publishable work; pick strongest. 2. **Recover** data/formulas/metadata/full panels/parameters. 3. **Compute** missing gene, EID3, module, donor-aware, pan-cancer, functional. 4. **Render** all data-supported panels, diverse & high-quality. 5. **Integrate** Fig1–2 then Fig3–7 where evidence permits. 6. **Validate** metrics, print-size inspection, legends, stats. 7. **Write** natural assertive Results/Discussion/Methods/legends. 8. **Overwrite** safely; remove redundant non-source files. 9. **Report** actual files, strongest findings, incomplete modules + exact reasons. Never say "completed" for a non-existent output.

**Final principle:** full ten-gene/EID3 coverage, question-driven panels, excellent visual communication, original module quantification, rigorous evidence, concise confident writing, and substantive deliverables — not plans, disclaimers, duplicated prompts, or invented science.
