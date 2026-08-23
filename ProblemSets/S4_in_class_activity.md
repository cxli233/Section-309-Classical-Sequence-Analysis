# Session 4 in-class activities 
## Q1 
Imagine your lab performed a genetic screen to study plant development. 
Arabidopsis seeds were treated with a mutagen called EMS, which induces random point mutations. 
Your lab recovered mutants that are smaller than wildtype plants and lacked post-embryonic growth. 
You mapped the mutation to a causal gene and sequenced its coding sequence.
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
>mutant_CDS
ATGGAGCCGCCACAGCATCAGCATCATCATCATTAAGCCGACCAAGAAAGCGGCAACAA
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
1. Identify the mutation in the coding sequence using [pairwise sequence alignment with EMBL](https://www.ebi.ac.uk/jdispatcher/psa).
2. Translate the WT and mutant coding sequence to protein using an online tool such as [expasy translate](https://web.expasy.org/translate/).  
How did the mutation affect the protein? 
3. Perform a BLAST search using the wildtype sequence against the Arabidopsis database.
Does it make sense that the mutation in this gene affected plant growth?   

## Q2 
Imagine you are working on the biotechnology for cheesemaking.
You are curious as to why the camel chymosin has superior milk clotting activity relative to cow, sheep, or goat chymosins.

1. Go to uniprot and gather the protein sequences of chymosin from these species and create a fasta file. 
2. Perform a [multiple sequence alignment with EMBL](https://www.ebi.ac.uk/jdispatcher/msa). 
3. When the result becomes available, click on the `Result Viewer` tab, then click `Send to MView`. 
Can you identify amino acid(s) that are distinct in camel chymosin, which may explain its superior activity? 

## Q3
Pick a protein involved in your research
(or a project you would like to have or found interesting in a previous course or problem set).

1. Search for its sequence if you don't have it already. 
2. Do a BLAST search on a database relevant to your research and download sequences of top 5-10 hits to create a fasta file.
3. Run a multiple sequence alignment. 
4. Write at least one sentence about the MSA result. What is scientifically relevant/interesting?
