# Session 3 in-class activities 
## Q1 
Imagine you are working on the biotechnology for cheesemaking.
You isolated a protein from a camel's stomach that exhibited superior milk clotting activity.
You were able to determine its sequence experimentally:
```
>4AA9_1
AREPLTSYLDSQYFGKIYIGTPPQEFTVVFDTGSSDLWVPSIYCKSNVCKNHHRFDPRK
SSTFRNLGKPLSIHYGTGSMEGFLGYDTVTVSNIVDPNQTVGLSTEQPGEVFTYSEFDG
ILGLAYPSLASEYSVPVFDNMMDRHLVARDLFSVYMDRNGQGSMLTLGAIDPSYYTGSL
HWVPVTLQQYWQFTVDSVTINGVAVACVGGCQAILDTGTSVLFGPSSDILKIQMAIGAT
ENRYGEFDVNCGNLRSMPTVVFEINGRDYPLSPSAYTSKDQGFCTSGFQGDNNSELWIL
GDVFIREYYSVFDRANNRVGLAKAI
```
Go to NCBI and perform a BLAST search ([link](https://blast.ncbi.nlm.nih.gov/Blast.cgi)).
What kind of protein is this?
Based on the BLAST hits, does it make sense that this protein has milk clotting activity? 

## Q2
Imagine you are providing bioinformatic support for a colleague who tracks proteins using fluorescent protein tags.
Your colleague ordered a plasmid encoding a yellow fluorescent protein (YFP).
The problem is that there are multiple different proteins that are called YFP in the literature.
Your colleague wants to know exactly which YFP they are working with,
so that they can set their microscope to best match its excitation and emission spectra.
```
>YFP
MVSKGEELFTGVVPILVELDGDVNGHKFSVSGEGEGDATYGKLTLKFICTTGKLPVPWP
TLVTTFGYGLQCFARYPDHMKQHDFFKSAMPEGYVQERTIFFKDDGNYKTRAEVKFEGD
TLVNRIELKGIDFKEDGNILGHKLEYNYNSHNVYIMADKQKNGIKVNFKIRHNIEDGSV
QLADHYQQNTPIGDGPVLLPDNHYLSYQSALSKDPNEKRDHMVLLEFVTAAGITLGMDE
LYK
```
1. Find the BLAST tool on [FP Base](https://www.fpbase.org/) and perform a BLAST search. 
2. What is the accession number of the best hit? 
3. What are wavelengths for maximum excitation and emission, respectively? 

## Q3 
Imagine you are working on somatic embryogenesis in plants. 
Somatic embryogenesis is a technique to induce totipotent stem cell formation from somatic cells,
which has applications in plant genetic engineering. 

You identified a gene that was highly expressed in embryonic cells 
but undetectable in non-embryonic cells of rice plants.
```
>LOC_Os11g19060
ATGGCCTCCATCACCAACTGGCTCGGCTTCTCCTCCTCCTCCTTCTCCGGCGCCGGCGCC
GACCCCGTCCTGCCCCACCCGCCGCTGCAAGAGTGGGGGAGCGCTTATGAGGGCGGCGGC
ACGGTGGCGGCCGCCGGCGGGGAGGAGACGGCGGCGCCGAAGCTGGAGGACTTCCTCGGC
ATGCAGGTGCAGCAGGAGACGGCCGCCGCGGCGGCGGGGCACGGCCGTGGAGGCAGCTCG
TCGGTCGTTGGGCTGTCCATGATCAAGAACTGGCTACGCAGCCAGCCGCCGCCCGCGGTG
GTTGGGGGAGAAGACGCTATGATGGCGCTCGCGGTGTCGACGTCGGCGTCGCCGCCGGTG
GACGCGACGGTGCCGGCCTGCATTTCGCCGGATGGGATGGGGTCGAAGGCGGCCGACGGC
GGCGGCGCGGCCGAGGCGGCGGCGGCGGCGGCGGCGCAGAGGATGAAGGCGGCCATGGAC
ACGTTCGGGCAGCGGACGTCCATCTACCGGGGTGTCACCAAGCACAGGTGGACAGGAAGG
TATGAAGCCCATCTTTGGGATAACAGCTGCAGAAGAGAAGGTCAGACTCGCAAAGGCAGA
CAAGTCAATGCAGGAGGATATGATAAGGAAGAAAAAGCTGCTAGGGCTTATGATTTGGCT
GCCCTTAAATACTGGGGCACTACAACGACGACGAATTTTCCGGTAAGCAACTACGAAAAA
GAGTTGGATGAAATGAAGCACATGAATAGGCAGGAATTTGTTGCATCCCTTAGAAGAAAA
AGCAGTGGATTTTCACGTGGTGCTTCCATATATCGTGGTGTTACAAGACACCATCAGCAT
GGAAGGTGGCAAGCAAGGATAGGACGGGTGGCAGGAAACAAGGATCTGTATTTGGGCACA
TTTGGCACCCAAGAGGAAGCTGCAGAGGCATATGATATCGCTGCAATCAAATTCCGTGGT
CTCAATGCTGTGACAAACTTTGACATGAGCCGGTACGATGTCAAGAGCATCATTGAAAGC
AGCAATCTCCCAATTGGTACTGGAACCACCCGGCGATTGAAGGACTCCTCTGATCACACT
GATAATGTCATGGACATCAATGTCAATACCGAACCCAATAATGTGGTATCATCCCACTTC
ACCAATGGGGTTGGCAACTATGGTTCGCAGCATTATGGTTACAATGGATGGTCGCCAATT
AGCATGCAGCCGATCCCCTCGCAGTACGCCAACGGCCAGCCCAGGGCATGGTTGAAACAA
GAGCAGGACAGCTCTGTGGTTACAGCGGCGCAGAACCTGCACAATCTACATCATTTTAGT
TCCTTGGGCTACACCCACAACTTCTTCCAGCAATCTGATGTTCCAGACGTCACAGGTTTC
GTTGATGCGCCTTCGAGGTCCAGTGACTCATACTCCTTCAGGTACAATGGAACAAATGGC
TTTCATGGTCTCCCGGGTGGAATCAGCTATGCTATGCCGGTTGCGACAGCGGTGGACCAA
GGTCAGGGCATCCATGGCTATGGAGAAGATGGTGTGGCAGGCATTGACACCACACATGAC
CTGTATGGCAGCCGTAATGTGTACTACCTTTCCGAGGGTTCGCTTCTTGCCGATGTCGAA
AAAGAAGGCGACTATGGCCAATCTGTGGGGGGCAACAGCTGGGTTTTGCCGACACCGTAG
```
1. Look up this gene in the [rice genome database](https://rice.uga.edu/). What kind of information can you gather?
2. Perform a BLAST search in [the Arabidopsis database](https://www.arabidopsis.org/tools/blast/).
Identify the best hit in Arabidopsis. What kind of information can you gather?
Hint: Should you translate the DNA sequence to protein first?
3. What kind of conserved domain does this gene encode?
Based on all the information you gathered,
can you infer or speculate the biological and molecular function(s) of this protein?
Hint: Use [conserved domain search tool](https://www.ncbi.nlm.nih.gov/Structure/cdd/wrpsb.cgi). 

## Q4 
Pick a protein relevant to your research project
(or a project you would like to have or found interesting in a previous course or problem set). 

1.Perform a BLAST search at a database (or multiple databases) that are relevant to your research.
E.g., if it is a human gene, you might want to BLAST search against model organism databases, such as mouse & fly.
If it is a plant gene, you might want to BLAST search against Arabidopsis. 
2. Gather information on the human curated knowledge of your protein from the databases as well as any conserved domains.
Speculate the biological and molecular function(s) of your protein. 


