# Peppro QC PEP


Get source samples using geofetch
```
geofetch -i sra_accessions.txt -n ppqc
```

Grab the source sample metadata here:
```
rsync -r rivi:/project/shefflab/data/sra_meta/ppqc .
```

Get RNA-seq spike-in samples here:
```
wget http://big.databio.org/peppro/fastq/K562_[1-9]0pct_RNArc_r2.fastq.gz .
```

Valide the configuration file with [`eido`](https://github.com/pepkit/eido) like so:
```
eido -p peppro_paper.yaml -s http://schema.databio.org/pipelines/ProseqPEP.yaml
```

Run in looper:
```
PROCESSED=/project/shefflab/processed DATA=/project/shefflab/data/ looper run ppqc/peppro_paper.yaml
```

The `peppro_paper.yaml` file is the working PEP for these samples.
The `peppro_paper.csv` file is the working annotation file for these samples.


