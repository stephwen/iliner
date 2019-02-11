# iLiner: a bioinformatics pipeline to perform identity-by-descent analysis

This repository contains the code for iLiner, a Python pipeline used to perform identity-by-descent (IBD) analysis using iLASH, as well as additionnal statistical calculations based on the output of iLASH.

## Requirements / Dependencies

* Python v.3.5.0 or higher
* iLASH
* ...

## Installation

~~iLiner is available as a pip package ans can be installed via:~~
```
git clone iliner
cd iliner
python iliner/iliner.py module [options]
```




## Functionnality

iLiner consists of 3 main modules performing different functions:

1. **iLASH module**: configures and runs iLASH 
2. **IBD depth module**: performs IBD depth calculation along the genome
3. **Stats module**: performs statistical analysis on the output of iLASH, stratified by population


***

## iLASH module

This module configures and runs the iLASH executable. 

### Usage with phased haplotype and sample files

```
Usage: iliner ilash [options]

 Options:

 -i, --ilash_path
 	Full path to the iLASH executable
 -s, --sample
 	Sample file in PLINK format (see https://www.cog-genomics.org/plink2/formats#sample)
 -hp, --haps
 	Phased haplotype file
 	(see http://mathgen.stats.ox.ac.uk/genetics_software/shapeit/shapeit.html#hapsample)
 -gm, --genetic_map
 	Genetic map file. The genetic map file should should share the same build as the sample file. 
 	(see http://mathgen.stats.ox.ac.uk/genetics_software/shapeit/shapeit.html#gmap)
 -op, --outfile_prefix
 	Output file prefix
 -ni, --no_indel
 	Optional argument, removes indels from the haplotype file.
```

### Usage with a phased VCF file
```
Usage: iliner ilash [options]

 Options:

 -i, --ilash_path
 	Full path to the iLASH executable
 -v, --vcf
 	Phased VCF file
 -gm, --genetic_map
 	Genetic map file. The genetic map file should should share the same build as the sample file. 
 	(see http://mathgen.stats.ox.ac.uk/genetics_software/shapeit/shapeit.html#gmap)
 -op, --outfile_prefix
 	Output file prefix
 -ni, --no_indel
 	Optional argument, removes indels from the haplotype file.
```

### Example usage with phased haplotype and sample files

```
TODO
```

### Example usage with a phased VCF file

```
TODO
```

## IBD depth module

This module performs IBD depth calculation along the genome and uses the output of the iLASH module.

### Usage 

```
Usage: iliner ibd_depth [options]

 Options:

 -mf, --mapfile
 	iLASH map file. 
 	Space-separated. 
 	Columns: Chromosome, rsID, GeneticPosition, PhysicalPosition
 -io, --ilash_output
 	iLASH output file. 
 	Tab-separated. 
 	Columns: Person1, Hap1, Person2, Hap2, Chr, Start, Stop, SNP1, SNP2, IBD_Sharing, Measure
 -op, --outfile_prefix
 	Output file prefix

```


## Stats module

This module performs performs statistical analysis on the output of iLASH, stratified by population.

### Usage 

```
Usage: iliner stats [options]

 Options:

 -pf, --population_file
 	Population file. 
 	Tab-separated. 
 	Columns: Sample id, Population
 -io, --ilash_output
 	iLASH output file. 
 	Tab-separated. 
 	Columns: Person1, Hap1, Person2, Hap2, Chr, Start, Stop, SNP1, SNP2, IBD_Sharing, Measure
 -op, --outfile_prefix
 	Output file prefix

```

