# lazzerinidenchilab-tails
### General Information

This is a repo containing the R code used to generate the manuscript from the Lazzerini Denchi Lab at the National Cancer Institute/NIH. The preprint describes the imaging-based TAILS screen for identifying novel regulators of the Alternative Lengthening of Telomeres (ALT) pathway. The R code heavily uses the [cellHTS2 package](https://bioconductor.riken.jp/packages/3.13/bioc/html/cellHTS2.html).

**Title:** [Identification of novel modulators of the ALT pathway through native FISH-based optical screen](http://biorxiv.org/lookup/doi/10.1101/2024.11.15.623791)

**Authors:** Azeroglu B, Khurana S, Wang SC, Tricola GM, Sharma S, Jubelin C, Cortolezzis Y, Pegoraro G, Miller KM, Stracker TH, Lazzerini Denchi E

**DOI:** 10.1101/2024.11.15.623791

### Project subfolder and file structure

The project repo contains the following subfolders and files:

- An `01_hts2_dataprep.qmd` script that includes the R and `cellHTS2` code used to prepare the data for the actual `cellHTS2` analysis. This script needs to be run before the `02_hts2_analysis.qmd` script.
- An `02_hts2_analysis.qmd` script that runs the `cellHTS2` analysis separately on each cellular feature calculated by Columbus.
- The `sgRNA_sequences_table`which generates a single table with all the sgRNA sequences used in the screen, which is saved as `sgRNA_sequences_table.csv` in the `knitr_output` subfolder.   
- The well-level results were obtained from the Columbus image analysis server, which is contained in the `columbus_output` subfolder. 
- The `reformat_metadata` subfolder contains library reformatting metadata output by the liquid handler and is used by the `02_hts2_analysis.qmd` script to generate the sgRNA oligos layouts for the imaging plates used in the screen. 
- A `Description.txt` file that contains details about the screen according to the `cellHTS2`
- A series of subfolders whose name starts with `hts2_output` containing the results of the `cellHTS2` analysis. Each of these subfolders contains data relative to one of the cellular features analyzed and output by Columbus.

The subfolder containing the primary sgRNA TAILS screen results relevant to this manuscript is:

- `spots_561_int_sum`: These are data relative to the sum of the intensity of the ssTelo channel spots detected by Columbus on a per cell basis. The per cell values are then averaged on a per well basis. This is the primary feature used to identify hits in the screen. The results can be found in the `Results_table.txt` file.

For information about this repo, please contact [Eros Lazzerini Denchi](mailto:eros.lazzerinidenchi@nih.gov) or [Gianluca Pegoraro](mailto:gianluca.pegoraro@nih.gov).
