Python script that reads a FASTA file containing nucleotide sequences of human genes and their respective identifiers (accepts UniProt or ENSEMBL), then applies point mutations to the sequences according to COSMIC Mutation Data, generating a new sequence and identifier for each mutant. 

Usage:
    ./mutation_missense.py MUTATION_FILE [--basesize=BASESIZE] [--datafile=DATAFILE] [--output=OUTPUT]
        [--encoding=ENCODING] [-v --verbose] [-h --help]
    MUTATION_FILE
        The filename for the file containing the mutations to be applied.
        Must be in the format: "NAME;CODE;MUTATION"
        Mutations can be in the formats (where ** is the position, A and G are example nucleotides):
        - **A>G
        - c.**delA
        - ns**A>G
        - c.**_**insAAGG
    --basesize=BASESIZE
        The number of bases from each gene to be obtained and exported [default: 90]
    --datafile=DATAFILE
        The name of the file that contains all genes. [default: All_COSMIC_Genes.fasta]
    --encoding=ENCODING
        Encoding to use when reading files. [default: utf-8]
    --output=OUTPUT
        The output filename [default: mutated.csv]
    Example:
    ./mutation_missense.py mutations1.csv --basesize=90
