# Session 5 in-class activities 
## Q1
Head to the [https://phylogeny.fr/ online tool](https://phylogeny.fr/) 
and use "WOX11_12_pep.fasta" in the Data folder to run a one-click analysis. Explore the available parameters. 
When the results become available, explore the outputs. 
Also explore the options for tree visualization and results files available for download. 

1. Which alignment tool did the web server use? Which tree making tool did the web server use? 
2. Examine the phylogeny. Are there nodes that are not well supported? What is the bootstrap value? 

## Q2 
1. Translate the following coding sequence to protein. 
```
>WT_CDS
ATGGAGCCGCCACAGCATCAGCATCATCATCATCAAGCCGACCAAGAAAGCGGCAACAA
CAACAACAACAAGTCCGGCTCTGGTGGTTACACGTGTCGCCAGACCAGCACGAGGTGGA
CACCGACGACGGAGCAAATCAAAATCCTCAAAGAACTTTACTACAACAATGCAATCCGG
TCACCAACAGCCGATCAGATCCAGAAGATCACTGCAAGGCTGAGACAGTTCGGAAAGAT
TGAGGGCAAGAACGTCTTTTACTGGTTCCAGAACCATAAGGCTCGTGAGCGTCAGAAGA
AGAGATTCAACGGAACAAACATGACCACACCATCTTCATCACCCAACTCGGTTATGATG
GCGGCTAACGATCATTATCATCCTCTACTTCACCATCATCACGGTGTTCCCATGCAGAG
ACCTGCTAATTCCGTCAACGTTAAACTTAACCAAGACCATCATCTCTATCATCATAACA
AGCCATATCCCAGCTTCAATAACGGGAATTTAAATCATGCAAGCTCAGGTACTGAATGT
GGTGTTGTTAATGCTTCTAATGGCTACATGAGTAGCCATGTCTATGGATCTATGGAACA
AGACTGTTCTATGAATTACAACAACGTAGGTGGAGGATGGGCAAACATGGATCATCATT
ACTCATCTGCACCTTACAACTTCTTCGATAGAGCAAAGCCTCTGTTTGGTCTAGAAGGT
CATCAAGAAGAAGAAGAATGTGGTGGCGATGCTTATCTGGAACATCGACGTACGCTTCC
TCTCTTCCCTATGCACGGTGAAGATCACATCAACGGTGGTAGTGGTGCCATCTGGAAGT
ATGGCCAATCGGAAGTTCGCCCTTGCGCTTCTCTTGAGCTACGTCTGAACTAG
```
2. Head to the [shoot web server](https://shoot.bio/) and produce a gene tree.
What is its most closely related ortholog among the species and proteins available at `shoot.bio`? 

## Q3
Imagine you are working on the biotechnology for cheesemaking.
You want to find proteins that are highly similar to camel chymosin 
and explore their potential application in cheesemaking. 

1. Go to uniprot and acquire the protein sequence of camel chymosin. 
2. Perform a BLAST at NCBI using camel chymosin as the query. 
3. Take the top 5 hits with the highest score and download their sequences, 
excluding camel chymosin itself and cow, sheep, or goat chymosins.
4. Create a fasta file containing camel chymosin, the top 5 hits, as well as cow, sheep, and goat chymosins. 
5. Head to the [https://phylogeny.fr/ online tool](https://phylogeny.fr/) and do a one-click analysis. 
6. Can you find proteins that are more closely related to camel chymosin than to homologs of other animals? 

## Q4 
Pick a protein involved in your research
(or a project you would like to have or found interesting in a previous course or problem set).
Repeat Q2 and Q3, but with your protein of choice. 
Write at least one sentence about the results. What is scientifically relevant/interesting?

## Q5
Preparing for the next session on command line interface: 

* Mac users: Find the Terminal on your machine. Open it and type `ls` and hit enter. What does it show you? 
Then type `pwd` and hit enter. What does it show you? 
* PC users: Download [MobaXterm](https://mobaxterm.mobatek.net/download-home-edition.html). 
You can download the portable edition and unzip it. Move the folder to somewhere you can remember. 
Open `MobaXterm_Personal_26.4.exe` and click `Start local terminal`. 
Type `ls` and hit enter. What does it show you? Then type `pwd` and hit enter. What does it show you? 