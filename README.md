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

2. The above result is then parsed by comma. 

3. According to different taxid in argument 2, different databases are chosen for the blasting the query. The names of the databases are  different blast argument will be produced. The result of using blast should contain query sequence ID, E-value, Percent positive mathes, and query sequence alignment. 

4. The blast query is built from the instructions on NCBI's website. 

5. All the queries are blast against the locally created databases that contain the corresponding sequences of human, ecoli, and wuhan virus. 

6. All the result is written to the output file. 

7. It is assumed that blastn.exe and all other databases required to perform blast are in the same directory as main.py. 
