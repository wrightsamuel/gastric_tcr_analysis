# Differential T cell clonal dynamics underlie outcomes to frontline chemoimmunotherapy in advanced gastric cancer

*The addition of aPD-1 to 5-FU/platinum in advanced gastric cancer (GC) yields variable responses. To understand cooperativity between chemotherapy and immunotherapy, we previously reported a phase II trial sequentially adding pembrolizumab to 5-FU/platinum. In this study, we use single-cell RNA- and TCR-sequencing to analyze 66,813 T cells from primary tumor biopsies pre-treatment, post-chemotherapy, and post-immunotherapy in 33 patients. We observed greater abundance, persistence, and recruitment of T cells with transcriptionally predicted tumor-reactivity in patients with prolonged progression-free survival (slow progressors). Increased B cell abundance and predicted B cell to T cell interactions supported T cell memory and co-stimulation, providing a mechanism for increased abundance and persistence of progenitor-exhausted and tumor-reactive T cells in slow progressors. T cell clones emerging in the tumor after immunotherapy were in the blood before treatment only in slow progressors. Our study thus highlights pre-treatment and early chemotherapy-induced T cell dynamics and B cell to T cell interactions that may drive durable response to chemoimmunotherapy in GC.*

Corresponding authors:

Arnav Mehta, MD, PhD 
Massachusetts General Hospital Cancer Center
55 Fruit St
Boston, MA 02114
amehta@broadinstitute.org

Samuel J. Klempner, MD
Massachusetts General Hospital Cancer Center
55 Fruit St
Boston, MA 02114
sklempner@mgb.org

Ryan Park, MD
MD Anderson Cancer Center
6565 MD Anderson Blvd
Houston, TX 77030
rpark@mdanderson.org

## Data availability

Pre-print is available on medRxiv: https://www.medrxiv.org/content/10.1101/2025.08.26.25334455v1

Processed paired scRNA/TCR-seq samples as well as PBMC bulk TCR-seq samples are available in the Gene Expression Omnibus (GEO) under accession numbers GSE315928 and GSE315929, respectively. 

These scRNA/TCR-seq samples contain pre-annotated samples that can be read in as AnnData objects and concatenated to be used as a main data object for analysis. For the blood-tumor comparisons, the bulk TCR-seq files can be read in and concatenated for use as well.

Full scRNA-seq data from the patient cohort are deposited in the European Nucleotide Archive (ENA) under accession PRJEB60680 and these data will be provided upon reasonable written request for academic use and within the limitations of the clinical trial informed consent and general data protection regulations.

Annotations (annot.csv) and T cell UMAP coordinates (umap.csv) for full scRNA-seq data are available in the misc_data folder. For particular analyses, it is necessary to use a cell_counts_by_sample.csv object, which can be found in the misc_data folder as well. For particular analyses, the TR scores for each cell are needed, which are calculated per-cell in the tcells_UCell_TRsig_scored.csv file, which are included for simplicity but are calculated using the 11122024_tr_spectra_score.ipynb notebook in the supp_only folder. The 11122024_tr_spectra_score.ipynb notebook uses supplementary tables from the Spectra paper (Kunes RZ, et al. Nat Biotechnol. 2024 Jul;42(7):1084-1095. doi: 10.1038/s41587-023-01940-3.), which can be accessed publicly by downloaded the supplementary tables .xlsx file from the publication. B cell UMAP coordinates are available in the misc_data folder as well under b_cell_umap.csv.

Environment/package versions used for analysis are available in the python38.yml in this repository.

## Figure 1

Fig. 1A: Diagram summarizing cohort and sample collection

Fig. 1B-C: Use 20260328_umap_heatmap.ipynb and read in full scRNA-seq data with annotations and UMAP coordinates as adata object in second cell, and subset to only the following cell type annotations: 'CD8 Cytotoxic T Cell', 'CD8 HSP T cell', 'CD8 Tem Cell', 'GZMK+ CD8 T progenitor ex Cell', 'NK', 'NKT', 'T naive/early memory Cell', 'Tactiv Cell', 'Tc17', 'Terminal CD8 Tex Cell', 'Th17', 'Th17/Tc17', 'Tprolif Cell', 'Treg', 'gd T Cell'.

Fig. 1D-E: Use 20251123_milo.ipynb and read in full scRNA-seq data with annotations as adata_tnk object appearing in second cell (adata_tcr object in third cell is not necessary). Do not run the fifth as this was used for sensitivity analysis and does not reflect correct progression assignments.

## Figure 2

Fig. 2A: Use 20251123_stickplot.ipynb and read in scRNA/TCR-seq data as adata_filt object. Do not run the third cell as this was used for sensitivity analysis and does not reflect correct progression assignments.

Fig. 2B: Use 20251123_all_timepoints_shared_stacked_barplot.ipynb and read in scRNA/TCR-seq data as adata object. Do not run the fourth cell as this was used for sensitivity analysis and does not reflect correct progression assignments. Figure 2B will be the figure entitled "Phenotypic Distribution of All Time Points Shared Clones, Subsampled", in which all the bars have a height of 1.

Fig. 2C-F: Use 20251123_alluvial_plots.ipynb and read in scRNA/TCR-seq data as adata object. Do not run the second line down of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments. Figures are plotted in reverse order (2F appears first, followed by 2E, etc), and some manual editing needs to be done because the plots are reversed due to how the function for plotting the alluvial plots was written. The alluvial.py function needs to be downloaded from the following Github page: https://github.com/vinsburg/alluvial_diagram to run this script.

Fig. 2G: Use 20251123_tpex_expression_heatmap.ipynb and read in scRNA/TCR-seq data as adata object. Do not run the second line down of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments.

## Figure 3

Fig. 3A: Use 04042025_tr_score_umap.ipynb and read in the scRNA/TCR-seq data as the adata object and the full scRNA-seq data as the adata_t object. You will also need to use the tcells_UCell_TRsig_scored.csv object to obtain the tumor-reactivity scores for each cell and the UMAP coordinates.

Fig. 3B, E-J: Use 20251124_initial_tr_analysis.ipynb and read in the scRNA/TCR-seq data as the adata object. You do not need the adata_t object. You will need to use the tcells_UCell_TRsig_scored.csv object. 

Fig. 3C-D: Use 20251124_tr_pheno_dists.ipynb and read in the scRNA/TCR-seq data as the adata object. Do not run the second line down of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments. You do not need the adata_t object. You will need the tcells_UCell_TRsig_scored.csv object and the alluvial.py function.

## Figure 4

Fig. 4A-C: Use 20251127_blood_tcr_analysis.ipynb and read in the scRNA/TCR-seq data as the adata object. Do not run the second line down of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments. Load in beta CDR3 sequences from the blood TCR files. You will also need the beta CDR3 sequences from non-naive/early memory cells in the tumor in a file called single_cell_sequences_wo_t_naive_early_memory.csv, which is produced towards the bottom of the 20251124_initial_tr_analysis.ipynb notebook.

## Figure 5

Fig. 5A: Use 20251126_b_cell_props.ipynb and read in full scRNA-seq data as adata object and scRNA/TCR-seq data as adata_t object. Do not run the second line down of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments. Relabel B cell subtypes 'Activated B Cell', 'Atypical Memory B Cell', 'EIF6+ B Cell', 'GC/Proliferative B Cell', 'Naive B Cell', 'Resting Memory B Cell' as 'B'.

Fig. 5B-C: Use 20260328_b_cell_umap.ipynb and read in full scRNA-seq data as adata object. Subset cells to only include 'Activated B Cell', 'Atypical Memory B Cell', 'EIF6+ B Cell', 'GC/Proliferative B Cell', 'Naive B Cell', 'Resting Memory B Cell', and load in B cell UMAP coordinates.

Fig. 5D: 20251127_bt_interactions.ipynb and read in full scRNA-seq data as adata object and scRNA/TCR-seq data as adata_t object. Do not run the second line of the second cell as this was used for sensitivity analysis and does not reflect correct progression assignments. Create an alternate label for B cell subtypes where 'Activated B Cell', 'Atypical Memory B Cell', 'EIF6+ B Cell', 'GC/Proliferative B Cell', 'Naive B Cell', 'Resting Memory B Cell' as 'B', but keep the subtype annotations because in some cases T cell-B cell interactions are compared on the basis of the cell type as a whole and other times within specific subtypes.

# Figure 6

Figure summarizing findings and interpretations from study.

## Further questions

Any questions regarding analysis code can be directed toward the corresponding authors.
