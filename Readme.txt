FastaRecordExtractor
Adam Jones (ajones@bio.tamu.edu)

This program takes a file with fasta records and allows you to extract
the records you want.  You need two files: one is the file with the fasta
records and the other is a file with a list of strings from the headers
of the file you want.  The format of this file is just to have a header
(or subset of the header) on each line.  Any fasta record in which any
of these sequences occurs will be retained.  Thus, if you used ">", all 
of the fasta files would be saved.  Your file could look something like the
following, with any number of lines:

>Locus_1_Transcript_1/1_Confidence_1.000_Length_706
>Locus_1054_Transcript_1/2_Confidence_1.000_Length_1655

If you used this file, you would retrieve only these two records.


Installation and Usage:


Windows: 

Put the executable (FastaRecordExtractor.exe) in the folder with 
your fasta file.  Double click on FastaRecordExtractor.exe to run
in interactive mode.  Input the name of the fasta file, your list of
records to retrieve, and a name for your output file.


Ubuntu (and maybe other forms of Linux):

Put the executable in the folder with your fasta file and list
of records to retrieve.  For help:

./FastaRecordExtractor -h

To run in interactive mode:

./FastaRecordExtractor

To run with arguments:

./FastaRecordExtractor -i fasta_file.fa -o output_fasta_file.fa -q list_of_headers.txt

You may need to alter file permissions for it to run:

chmod u+x FastaRecordExtractor



Other operating systems:

Compile the source code using the g++ compiler.

Here's one way to do it:

g++ FastaRecordExtractor.cpp -o FastaRecordExtractor


Arguments:

-i:	name of the input file (fasta_file.fa for example)
-o:	name of the output file (will be overwritten if it exists)
-q:	name of the query file (i.e., substrings or entire headers of the records you want)
