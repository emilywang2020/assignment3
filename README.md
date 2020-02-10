# assignment3
**Input:**

sys.argv[1]: comma seperated list of refseq IDs or filenames for query sequences in fasta

sys.argv[2]: human(taxid=9606), ecoli(taxid=562), or wuhan viral genome (taxid=2697049)

sys.argv[3]: e-value threshold. optional. If not specified, the value will be 10.

sys.argv[4]: output filename


**Output:**

All of the results will be written to an output file named by the filename from sys.argv[4].


**Process:**

1. Read in the command line arguments as specified above. The first command line argument should look like this:
chimps.fasta,human.fasta for filenames and NG_046857.1,NG_390429.2 .There should be no space in between and the file name should follow the convention of filename.fasta.

2. The input filenames must end with either .fasta or .fsa to indicate that they are fasta files. 

3. The above result is then parsed by comma. 

3. According to different taxid in argument 2, different databases are chosen for the blasting the query. The names of the databases are  humangenomedatabase, ecolidatabase, and wuhansequencedatabase.  

4. According to the input, different approaches will be conducted to get the fasta files. If input is a list of refseq IDs, a NCBI api will be used to acquire the corresponding fasta files. The contents of these fasta files will be concated to an input file for blasting. 
If the input is a list of filenames, then the file will be blast against the database directly. 

5. The result of using blast should contain query sequence ID, E-value, Percent positive mathes, and query sequence alignment.

6. All the result is written to the output file. 

7. It is assumed that blastn.exe and all other databases required to perform blast are in the same directory as main.py. 
