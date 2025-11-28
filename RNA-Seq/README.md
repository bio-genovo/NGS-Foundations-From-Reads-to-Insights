

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

## Data Collection
We will retrieve reads for SRR ID SRR849249 for the analysis.  

__Using fasterq-dump (faster, multithreaded):__
```
fasterq-dump SRR849249 --split-files --threads 8 --progress
```

__Using fastq-dump (with gzip):__
```
fastq-dump --split-files --gzip SRR849249
```
