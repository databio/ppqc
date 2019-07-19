# Peppro QC PEP


Get samples using geofetch

```
geofetch -i sra_accessions.txt -n ppqc
```

Grab the metadata here:
```
rsync -r rivi:/project/shefflab/data/sra_meta/ppqc .
```

Run in looper:
```
PROCESSED=/project/shefflab/processed looper run ppqc/ppqc_config.yaml --selector-attribute sample_
name --selector-include GSM3309957 --compute singularity_local
```