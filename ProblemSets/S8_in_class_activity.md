# Session 8 in-class activities 
## Q1 (an example tutorial)
Imagine you are working on the genetic determinants of flavors in daikon radish. 
According to the literature, a major component of flavor is aliphatic glucosinolates. 
Daikon is in the same family as the model plant Arabidopsis, which shares the glucosinolate biosynthetic pathway. 
In addition, a major driver in aliphatic glucosinolate variation in Arabidopsis is the MAM1 gene.
You would like to perform a BLAST to identify MAM1 homologs in the daikon genome. 

1. Head to the [Arabidopsis database](https://www.arabidopsis.org/).
Search "MAM1" or "AT5G23010". Copy the protein sequence and create a fasta file called "AtMAM1.fasta".
Download the protein annotation of the Arabidopsis genome from [this page](https://www.arabidopsis.org/download/list?dir=Proteins%2FTAIR12_protein_lists).
The file name should be "TAIR12_pep.fasta". 
How many protein coding genes are annotated in the Arabidopsis genome? 

2. The daikon genome was published [here](https://academic.oup.com/dnaresearch/article/27/2/dsaa010/5840486). 
Copy "Rs_1.0.peptide.fa" from the 309 course Data folder to your Data folder and enter your Data folder. 
This is a fasta file containing all annotated proteins, provided by the authors of the paper mentioned above. 
How many protein coding genes are annotated in the daikon genome? 

3. Head to [OnDemand.hpcc.msu.edu](https://ondemand.hpcc.msu.edu/pun/sys/dashboard) and log in.
Using the `Files` tab, navigate to your scratch space. Create a new folder called "309_S8" and enter it. 
Upload AtMAM1.fasta, TAIR12_pep.fasta, and Rs_1.0.peptide.fa to the folder you just created. 

4. Click on "Development Nodes" and select one of them (doesn't matter which one). 
Start an interactive session with 48G RAM for 2 hrs, like this: 
```
interact --mem=48G -t 2:00:00
```
The session should start in a couple minutes. 

Navigate to your scratch space. 
```
cd /mnt/scratch/USER/309_S8/ 
```
Replace `USER` with your MSU NetID. 
Call `ls` command to verify your files are there. 

5. Load the BLAST tool. You can check if the cluster has it with `ml spider blast`.
Does the cluster have BLAST installed? What is the version number? 
Load BLAST to your session. 
```
ml BLAST+/2.14.1-gompi-2023a
```

6. To run BLAST, we need to make a BLAST database first. 
We have 2 species, so we will need to create a database for each of them. 
```
makeblastdb -in Rs_1.0.peptide.fa -dbtype prot  -parse_seqids # Radish
makeblastdb -in TAIR12_pep.fasta -dbtype prot  -parse_seqids # Arabidopsis 
```

7. Run BLASTP using AtMAM1 as a query against annotated radish proteins.  
```
blastp -query AtMAM1.fa \
-db Rs_1.0.peptide.fa \
-outfmt 6 \
-out AtMAM1_vs_Radish.txt
```
The BLASTP results are in "AtMAM1_vs_Radish.txt". 
How many hits did BLASTP return? 
Filter the results for score > 100 (12th column) and E value < 1e-5 (11th column).
Save the output to a new file called AtMAM1_vs_Radish_high_confidence.txt. 
What are the percent identity (3rd column) of the high confidence hits? 

## Q2
1. Run the following script to isolate the protein sequences of AtMAM1 homologs in radish. 
We are using a tool called `seqkt`. 
Read the [seqtk documentation page](https://github.com/lh3/seqtk) to learn more about it.
```
ml seqtk/1.4-GCC-12.3.0 
cut -f2 AtMAM1_vs_Radish_high_confidence.txt > Radish_MAM1_homolog_names.txt 
seqtk subseq Rs_1.0.peptide.fa Radish_MAM1_homolog_names.txt > Radish_MAM1_homologs.fa 
```
Check how many sequences there are in Radish_MAM1_homologs.fa. Is this what you would expect? 

2. Run a BLAST search, but this time using Radish_MAM1_homologs.fa as query and TAIR12_pep.fasta as database. 
Filter the results for score > 100 and E value < 1e-5. 
Save the output to a new file. Is AtMAM1 (AT5G23010) among the top hits? 
Besides AT5G23010, are there any other MAM1 homologs in the Arabidopsis genome? 

3. Can you explain what the following command does?
```
cut -f2 Radish_MAM1_vs_Ara_high_conf.txt | sed 's/\.[12]//g' | sort | uniq > AtMAM_homologs.txt
```

 