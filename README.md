# SOIL_VIROME_ECOLOGY

Code accompanying the study:

**“The impact of organic, conventional and regenerative agriculture on soil virome ecology and carbon-cycling functions.”**

This repository contains scripts and workflows used to analyze soil viral metagenomes and assess how different agricultural management systems influence virome ecology and carbon-cycling–related functions.

---

## Overview

All analyses were performed using the **MOSAC** workflow (https://github.com/lauramilena3/MOSAIC). Detailed descriptions of the workflow steps, tools, and parameters are provided in the associated manuscript.

This repository primarily serves to:
- Document the computational workflow used in the study  
- Support reproducibility of virome and functional analyses  
- Provide summary analyses and visualization notebooks  

---

## Workflow Execution

The MOSAC workflow was executed using **Snakemake** with Conda environments enabled. The full workflow was run with the following command:

```bash
snakemake --use-conda -p runWorkflow \
  --config \
    input_dir=/home/lmf/DANIEL/VIRAL_METAGENOMES/00_RAW_DATA \
    kraken_db=/home/lmf/db/KRAKEN/kraken/ \
    ecc_memory=16000 \
    subassembly=True \
    assembly_stats=True \
    subsampling=True \
    min_votu_length=10000 \
    run_vcontact=True \
    imgvr_blast=True \
    run_DRAM=True \
    microbial_spacers=/home/lmf/DANIEL/MG-Assembly/ALL_MG_megahit_2000bp_derreplicated_minced_predicted_spacers.fa \
  -j 144 -k -n
```

Note: Paths and computational resources should be adjusted according to local system configuration.

## Summary and Visualization

A summary of the results and downstream analyses can be found in the Jupyter notebook:

- `soil_virome_summary.ipynb`

This notebook includes:
- Overview of virome composition
- Ecological analyses
- Carbon-cycling functional annotations
- Figures and summary statistics used in the manuscript

## Citation

If you use this code or workflow, please cite:

*The impact of organic, conventional and regenerative agriculture on soil virome ecology and carbon-cycling functions.*


