# Structure-aware screening

This directory contains information about the conducted structure-aware screening. 

The raw results of the screening are stored in __results.tsv__.


The command for creating a local Foldseek ProstT5 database of all the proteins in 5167 phage genomes:


```
foldseek createdb 5167_cds.faa allproteins_prostt5_db --prostt5-model prostt5_weights
```


The command for creating a local Foldseek database of 22 representative DT-helix AF models:
```
foldseek createdb foldseek_22db DT_22db
```




The command for running the structure-aware screening:

```
foldseek search \     
    DT_22db \
    allproteins_prostt5_db \
    resultDB \
    tmp \        
    -e 1e-3 \        
    --max-seqs 1000       
```

The command for converting the screening results to tsv format:

```
foldseek convertalis \
    DT_22db \
    allproteins_prostt5_db \
    resultDB \
    results.tsv
```
