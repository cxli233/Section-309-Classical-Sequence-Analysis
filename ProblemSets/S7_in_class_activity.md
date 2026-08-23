# Session 7 in-class activities 
## Q1 (and demonstration) 

* Mac user: open Terminal
* PC user: open MaboXTerm.exe and click `Start local terminal` 

1. Navigate to your Desktop using `cd`. 
You might be in your `Home` directory. If that's the case, you will do `cd Desktop`. 
If you are already in your Desktop, you can use `ls` to check if the files listed are the same as what you can see on your Desktop. 
You can check where you are using `pwd`. 
Make a new folder called "CLI_hw" with `mkdir CLI_hw` and enter it with `cd CLI_hw`. 

2. Once you are inside "CLI_hw", create the following 3 new folders: Data, Scripts, and Results with `mkdir`.
Use `ls` to check if you have created the right folders. 
Copy "WOX11_12_pep.fasta" from the 309 course Data folder to your Data folder and enter your Data folder. 
Use `grep "^>" WOX11_12_pep.fasta` to search for the lines with sequence IDs.
Can you explain what this grep command is searching? 
The `wc -l` command allows you to count the number of lines. You can directly pipe the output of `grep` to `wc -l`.
Like this: 
```
grep "^>" WOX11_12_pep.fasta | wc -l 
```
How many sequences are in "WOX11_12_pep.fasta"? 

3. You can save the output of grep to a new file in the Results folder. 
```
grep "^>" WOX11_12_pep.fasta > ../Results/WOX11_12_seq_ids.txt
```
Can you explain what `> ../Results/WOX11_12_seq_ids.txt` is doing in the command? 
Which folder is `..` referring to here?  

4. Navigate to the Results folder. Print the entirely of "WOX11_12_seq_ids.txt" with `cat`. 

You can remove ">" from the file using `sed`. Like this: 
```
sed 's/>//g' WOX11_12_seq_ids.txt > WOX11_12_seq_ids2.txt
```
Use `cat` to view "WOX11_12_seq_ids2.txt". Which pattern is `sed` matching here? 
Which pattern is `sed` replacing here? 
If you were to do `sed 's/>/Seq_name:/g' WOX11_12_seq_ids.txt`, what would the result be? 

5. Copy "TT8_hits" from the 309 course Data folder to your Data folder and enter your Data folder.
How many rows does TT8_hits have? 
This is the BLASTP output file with 12 columns: 

   1.  qseqid      query or source (gene) sequence id
   2.  sseqid      subject or target (reference genome) sequence id
   3.  pident      percentage of identical positions
   4.  length      alignment length (sequence overlap)
   5.  mismatch    number of mismatches
   6.  gapopen     number of gap openings
   7.  qstart      start of alignment in query
   8.  qend        end of alignment in query
   9.  sstart      start of alignment in subject
   10.  send        end of alignment in subject
   11.  evalue      expect value
   12.  bitscore    score

Let's say we want to filter the BLAST hits for score > 100 and E-value < 1e-5. We can use `awk` for that.
Then save the result to a new file in the Results folder. 
```
awk '$12 > 100 && $11 < 1e-5' TT8_hits > ../Results/TT8_hits2 
```
Can you explain what is going on in the above command? 
How many BLAST hits do we have after filtering? 

## Q2
Copy "test.fasta" from the 309 course Data folder to your Data folder and enter your Data folder.
View the first 10 rows using `head`. 
This is a fasta file for protein sequences.
1. How many sequences are there in this file? 
2. Imagine you are using a tool that does not allow the "*" symbol at the end of the sequences.
Write a script to remove all "*" in the file and save the result to the Results folder. 
Write down your script here. 

## Q3 
Imagine you are working with a file that has 3 columns. 
You want to write a script to filter for column 1 >= 0, column 2 with the value "active",
or column 3 with the value > 60. What should the command be? 
