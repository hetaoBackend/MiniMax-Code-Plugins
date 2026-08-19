---
name: rgraph
description: Use when the user already has an RNA-seq count or expression matrix and needs downstream analysis or figures (normalize, PCA, DESeq2/edgeR/limma, volcano, heatmap, GO/KEGG, GSEA, WGCNA). Drive the rgraph MCP tools with local Rscript; do not redraw in Python.
---

# rgraph

Use the `rgraph` MCP tools. Prefer R-rendered png+pdf over matplotlib copies.

## Typical order

1. `rgraph_env` — confirm Rscript and packages
2. `rgraph_normalize` / `rgraph_pca` / `rgraph_correlation` as needed
3. `rgraph_diff` — default significance metric is **padj**, not raw p-value
4. `rgraph_volcano`, `rgraph_heatmap`, `rgraph_enrich`, `rgraph_gsea`, `rgraph_wgcna` as requested

Required table columns are in the Plugin README (`sample_name`/`group`, `gene_id`, counts).

If Rscript is missing, return the generated `.R` script and the command to run it. If a package is missing, return the install hint from the tool. Do not pretend the figure was drawn.
