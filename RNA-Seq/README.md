

## How to Prepare Environment
```bash
# Update conda
conda update -n base -c defaults conda
# Build the environment
conda env create -f rnaseq_env.yml
```
__Verify Installation:__
```
# Activate environment
conda activate ngs
# Verify
fastqc --version
fastp --version
trimmomatic -version
samtools --version
STAR --version
```
