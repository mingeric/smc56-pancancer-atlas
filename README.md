# SMC5/6 Pan-Cancer Atlas — Agent Skill

> 中文速览：一个端到端的 Agent Skill，驱动 SMC5/6 复合体**十基因（含 EID3）**泛癌多组学与单细胞图谱研究——从数据审计、供体级统计、40+ 个发表级图件面板的重建，到自然、自信的结果 / 讨论写作与受控覆盖。**科学有效性优先，绝不虚构数值或面板。**

`smc56-pancancer-atlas` is an end-to-end, data-grounded [Agent Skill](https://www.anthropic.com/news/skills) for studying the **SMC5/6 complex across ten genes in pan-cancer multi-omics and single-cell data**. It operates on the user's real local data and treats the audit → recover → compute → render → integrate → validate → write → overwrite → report sequence as an executable contract, not a proposal. If a data source is unavailable, it completes everything that is possible, logs the exact blocker, and never fabricates values or panels.

The complete specification lives in **[`SKILL.md`](SKILL.md)** (reproduced verbatim from the original). This file is the repository overview.

## What it drives

| Stage | Deliverable |
|---|---|
| Dataset audit | Panel-by-panel source manifest; verified cell / donor / study counts (the `391,963 cells / 132 donors / 13 studies` figure is an **audit target to verify**, not an assumed truth) |
| Gene landscape | Ten-gene detection, within-study normalized expression, pseudobulk, circular UMAP / DotPlot / ridge / heatmap atlases |
| Modules & co-expression | Fixed C1–C4 combinations, exploratory C5–C8, M1–M4 / W1–W3 signatures with explicitly documented scoring |
| EID3 | A dedicated biological question vs. NSMCE4A: co-detection categories, W1↔W2 balance, dropout-aware pseudobulk, replication |
| Pan-cancer inference | Donor-aware pseudobulk / hierarchical models, effect sizes + 95% CIs + BH FDR, leave-one-study-out robustness |
| Mechanistic & clinical extensions | DNA-repair / replication-stress / chromatin / immune associations; GTEx, TCGA, proteomics, CNA, survival, drug sensitivity — **only where data permit** |
| Figures | 6–7 manuscript main figures from 40 candidate panels; 600 dpi PNG + vector PDF/SVG, print-readable multi-page layouts |
| Writing | Natural, assertive, evidence-based Results / Discussion / Methods / figure legends |
| Controlled overwrite | Atomic replacement only after validation; previous trusted artifacts archived; every replacement logged |

## The ten genes

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
| `EID3` | proposed NSMCE4A alternative-subunit context; analyzed separately |

Official symbols, identifiers, aliases, assay platform and annotation build must be validated; the `NSMCE4B` / `EID3` annotation is resolved explicitly.

## Non-negotiable scientific guardrails

- **C1 = SMC5 + SMC6**, **C2 = SMC6 + NSMCE4A**, **C3 = SLF1 + SLF2**, **C4 = SIMC1 + SLF2** — IDs and memberships never change.
- These ten genes are **not** described as ten obligatory co-assembled subunits.
- RNA co-detection is never equated with physical assembly, competition, or measured protein activity.
- Patient-level inference is **donor-aware**: 391k cells are never treated as independent replicates.
- `CBS` and `AB` are **expression-proxy indices**, not demonstrated mechanism or therapeutic guidance.
- A 3D UMAP is labelled as an embedding, never as measured 3D tissue space.
- Missing data are never filled with synthetic panels; every blocker is logged, and any reconstructed equation is marked as a **new operational definition**, not a transcription of the original.
- Machine learning splits by donor/study to avoid leakage; survival needs validation; drug sensitivity is never phrased as a treatment recommendation.

## Figure architecture

- **Figure 1 (A–T):** ten genes, canonical and alternative modules — the exhaustive single-cell atlas.
- **Figure 2 (A–T):** pan-cancer differences, function, and evidence.
- **Figures 3–7 (as data permit):** normal-tissue baseline → tumor deviation; bulk RNA + proteomics convergence; immune / stromal / spatial context; prognosis and drug sensitivity; optional comparative mechanistic synthesis.

Production standard: white background, restrained low-saturation colorblind-safe palette, **≥8 pt at print size**, no clipping, valid colorbars, one takeaway per panel, high-resolution **600 dpi** PNG plus vector PDF/SVG. The skill explicitly warns against squeezing 20 complex panels into a ~183 mm single page and requires multi-page, readable editorial layouts instead. Supplements carry QC, sensitivity analyses, and full statistical tables.

> **Print-size note from the author's convention:** the de-facto double-column print-width gate is **183 mm**, checked as `image_width_px / 300 * 25.4 ≤ 183` (height ≤ 247 mm). Composite 2-column PNGs are for review only; standalone vector sources are the formal deliverable.

## Usage

`SKILL.md` follows the Agent-Skill convention: a YAML frontmatter (`name` / `description`) plus a Markdown specification. Drop it into any Agent-Skill directory that reads this format, or load it directly as a workflow/system prompt. Keep the YAML frontmatter intact so the skill remains discoverable.

```bash
git clone https://github.com/mingeric/smc56-pancancer-atlas.git
mkdir -p ~/.workbuddy/skills/smc56-pancancer-atlas/
cp smc56-pancancer-atlas/SKILL.md ~/.workbuddy/skills/smc56-pancancer-atlas/SKILL.md
```

The skill **executes against your local research data**; it defines the workflow, formula conventions, and quality gates, and does not bundle any dataset. Generated outputs follow the `SMC56_FINAL/` project tree described in §10 of `SKILL.md`.

## Repository layout

```text
SKILL.md      # complete skill specification (verbatim original, 239 lines)
README.md     # this overview
LICENSE       # MIT
.gitignore    # keeps generated research outputs out of version control
```

## License

MIT — see [`LICENSE`](LICENSE). Copyright (c) 2026 mingeric.

If you use this skill in a publication, please cite the repository and acknowledge the underlying data sources (TCGA, GTEx, CPTAC, DepMap, ICGC, GDSC, CCLE, etc.) according to their own terms.
