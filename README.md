# Peppro QC PEP


## Get source samples using geofetch
```
geofetch -i sra_accessions.txt -n ppqc
```

## Grab the source sample metadata here:
```
wget -r http://big.databio.org/peppro/sra_meta/ppqc/ .
```

## Get RNA-seq spike-in samples here:
```
wget http://big.databio.org/peppro/fastq/K562_[1-9]0pct_RNArc_r2.fastq.gz .
```

## Validate the configuration file with [`eido`](https://github.com/pepkit/eido) like so:
```
eido -p peppro_paper.yaml -s http://schema.databio.org/pipelines/ProseqPEP.yaml
```

## Create user-specific environment variables
 - `$CODE`: this is a path to the parent directory where scripts and code are stored
    - For example:`CODE=/scratch/userid/src/`
 - `$DATA`: this is a path to the parent directory where input files are stored
    - For example:`DATA=/project/shefflab/data/`
 - `$PROCESSED`: this is a path to the parent directory to where output should be written
    - For example:`PROCESSED=/project/shefflab/processed/`

## Run in looper:
```
looper run ppqc/peppro_paper.yaml
```

The `peppro_paper.yaml` file is the working PEP for these samples.
The `peppro_paper.csv` file is the working annotation file for these samples.


