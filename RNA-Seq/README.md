

## How to Prepare Environment


### ✅ Install Anaconda
Download and install Anaconda from the official website:
🔗 [https://www.anaconda.com/download](https://www.anaconda.com/download)

Choose your operating system (Windows, macOS, or Linux) and follow the installer steps.

### ✅ Install R and RStudio

#### 1️⃣ Install R (required for RStudio)

You can install **R** using either system package manager or Conda.  
RStudio requires r-base.
```
# Using apt-get (Linux)
sudo apt-get update
sudo apt-get install r-base

# Using conda
conda install r::r-base
```

#### 2️⃣ Install RStudio Desktop

Download RStudio Desktop from the official Posit website:

🔗 [https://posit.co/download/rstudio-desktop/](https://posit.co/download/rstudio-desktop/)

Install the downloaded file for your operating system.

---

### Prepare conda environment

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
