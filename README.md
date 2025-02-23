To run the SnakeFile use:
snakemake --sdm conda

#The Project
This workflow has a rather simple purpose of looking for single nucleotide polymorphims in organisms. It does not take two samples of the same organism but instead simulates the polymorphisms by mutating the input sample.

#Dependencies
All dependencies are specified in .yaml files, that are loaded within the rules where they apply.

#Parameter Settings
The parameters of all function calls can be set in the config file.

#Selection of Data
You can select which sequences/datasets you want to work with by going to the config.yaml file and setting the samples with their id in the edirect sample section.
If you do not want to work with the entire sequence, but instead use a subset you can set the subset size in the config file as well.

#Fetch Data
The fetching is done using edirect with the nucore database. The data is downloaded in fasta format(can be changed) and stored in an .fna file in the data directory

#Emboss
The emboss package is used to introduce mutations into the downloaded sequence data.

#ART + Samtools
ART illumina is used to generate sequencing reads, which are then mapped using samtools

#PileUp and Varscan
In the last two steps, pileup and varscan are used to uncover the SNPs from the mapped reads.