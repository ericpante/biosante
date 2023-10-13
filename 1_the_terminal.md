# introduction to the terminal and the shell 

## getting started and basic commands

to ease your work, consider installing `brew` and `fish`.

work in class - getting acquainted with the following commands:
- nagivating across folders: `pwd`, `ls`, `cd`, `mkdir`, `rmdir`, `rm`
- creating a file: `touch`, redirecting standard output with `>`
- understanding and changing file permissions (`chmod`)
- working with archives: `tar` and tarballs

## getting data

have a look at the NIH Small Read Archive: https://www.ncbi.nlm.nih.gov/sra/?term=SRR1754715 
SRR1754715 is a `fastq` file from SRA (RADseq Pedicularis sect. Cyathophora). you can get the data manually through the SRA interface but we are going to do it through the terminal. 

We will use the SRA tool kit. Here is the HowTos: https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump and https://github.com/ncbi/sra-tools/wiki/08.-prefetch-and-fasterq-dump

1. Get the toolkit: 
```
wget --output-document sratoolkit.tar.gz https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-ubuntu64.tar.gz
```
2. Extract the tookit from tarball
```
tar -vxzf sratoolkit.tar.gz
```
3. Add the toolkit to the `$PATH` (for this session only)
```
export PATH=$PATH:$PWD/sratoolkit.3.0.0-xxx/bin # xxx: replace by your version.
```
4. Test it. 
```
which fastq-dump
```

Now we can use the kit to get multiple SRR data files. 
```
prefetch ACCESSION ## or --option-file SRR_Acc_List.txt for a list
fastq-dump ACCESSION ACCESSION ACCESSION ACCESSION ...
```

## looking at raw genomic data through `fastq`

## looking at genomic data through `vcf`

