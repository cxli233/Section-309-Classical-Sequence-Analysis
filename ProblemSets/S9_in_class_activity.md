# Session 9 in-class activities 
## Q1 (an example and tutorial)

## 1. Creating folders on the cluster 
Log into MSU HPCC via OnDemand. 
Create a folder in your scratch space called "309_S9" and enter it. 
Create a folder called Data, a folder called Results, and a folder called Scripts. 
Upload "Genes_of_interest.csv" from the 309 course Data folder to the Data folder you just created. 

Go to [data repository site](https://datadryad.org/dataset/doi:10.5061/dryad.d2547d851).
Click on the triangle next to "Feb 22, 2023 version files" to view a list of files on the repository. 
Download:

* Genome sequence: cro_v3.asm.fa  
* Gene model annotations: cro_v3.gene_models.gff3   

Upload them to the Data folder that you created earlier. 
Now go to a development node.  
```
interact --mem=48G -t 2:00:00 
cd /mnt/scratch/USER/309_S9 # Replace USER with your MSU NetID 
```
This may take a few minutes for the session to start. 

## 2. Find promoter genomic coordinates from the gene list using R in CLI 
### Setting up your R environment 
If you haven't installed tidyverse in R on the cluster,
you will need to do it now. 
```
ml purge 
ml R/4.3.2-gfbf-2023a-ICER # Make sure you load the right version from HPCC 
R # Enter R 
install.packages("tidyverse") 
# This will take ~20-30 min. 
library(tidyverse)
```
When installing packages, choose CRAN mirror 1 or 64 when prompted. 
You only need to install packages once. 
These packages will let you do data wrangling in R. 

### Parsing gene and promoter coordinates
```
gff3 <- read_delim("Data/cro_v3.gene_models.gff3", col_names = F, delim = "\t", comment = "#")
gff3_nice <- gff3 |> 
  filter(X3 == "gene") |> 
  mutate(geneID = str_remove_all(X9, "ID=|;.+")) |> 
  mutate(start = X4 - 1) |> 
  mutate(end = X5) |> 
  select(X1, start, end, X7, geneID) |> 
  mutate(start_new = case_when(
    X7 == "+" ~ start - 500,
    T ~ end - 100
  )) |> 
  mutate(end_new = case_when(
    X7 == "+" ~ start + 100,
    T ~ end + 500
  )) |> 
  select(X1, start_new, end_new, geneID) |> 
  filter(str_detect(X1, "Chr"))
```

What happened here: 

1. Load "cro_v3.gene_models.gff3" from the Data folder.
2. Parse gene ID (from column 9 of the gff file).
3. Convert 1-based coordinates of gff to 0-based coordinates of bed. 
4. Create new start and end coordinates based on which strand (+ or -) the gene is on. 
5. Define core promoter as up 500 and down 100 from the start of the gene. 
6. Remove extra columns and genes not placed on chromosomes. 

Run `dim(gff3_nice)`. How many genes are in this genome annotation? 

### Filter for genes of interest and write out coordinates as a bed file.  
```
GOI <- read_csv("Data/Genes_of_interest.csv") 
gff3_nice |> 
  right_join(GOI |> 
               mutate(geneID = str_replace_all(gene_ID, "-", "_")),
             by = "geneID") |>
  select(X1, start_new, end_new, geneID) |>
  filter(is.na(X1) == F) |> 
  write_delim("Results/GOI_promoters.bed", col_names = F, delim = "\t")
quit() 
```
What happened here: 

1. Read "Genes_of_interest.csv" from the Data folder.
2. Join the promoter coordinates to the genes of interest, only keeping our genes of interest.
3. Remove extra columns.
4. Write the resulting object as GOI_promoters.bed file in the Results folder without headers. 

Type `n` when prompted when you quit R. 
 
## 3. Bedtools get fasta
You will use Bedtools to extract the DNA sequence from your genomic coordinates. 
```
ml purge
ml BEDTools/2.31.0-GCC-12.3.0 
cd Results 
bedtools getfasta -fi ../Data/cro_v3.asm.fa -bed GOI_promoters.bed > GOI_promoters.fasta 
```
The promoter sequences are in a fasta file in the Results folder. 

## 4. Motif enrichment with MEME
We can then use the fasta file of promoter sequences to run a motif enrichment analysis using MEME. 
```
ml purge
ml MEME/5.5.4-gompi-2022b 
meme GOI_promoters.fasta \
-o GOI_promoters.meme \
-dna \
-revcomp \
-mod anr \
-nmotifs 15 \
-minw 4 \
-maxw 8 \
-evt 0.05
```
This will take ~20 min. 
Your results will be in the Results folder called GOI_promoters.meme. 
You can download the GOI_promoters.meme folder to your machine, unzip it, and view the results. 
How many DNA motifs were discovered as enriched in these promoters? 

## Q2
Go to the [ChimeraX website](https://www.rbvi.ucsf.edu/chimerax/download.html).
Download the software. The website should automatically detect your operation system. 

