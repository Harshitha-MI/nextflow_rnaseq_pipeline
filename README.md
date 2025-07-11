# RNA-seq Analysis Pipeline (Nextflow)

This repository contains a modular RNA-seq preprocessing pipeline written in [Nextflow](https://www.nextflow.io/).  
The workflow automates quality control, trimming, genome indexing, and read alignment for RNA-seq data.

---

## 🧪 Current Workflow Status

✅ Step 1: Adapter trimming with **Trim Galore**  
✅ Step 2: Quality control with **FastQC + MultiQC** (combined in a single QC step)  
✅ Step 3: STAR genome indexing (tested locally)  
⏳ Step 4: STAR alignment (pending; planned to run on EC2 instance)  
🔜 Step 5: Read quantification using **FeatureCounts**

> 💡 I successfully tested the pipeline up to the STAR genome indexing step on my local machine.  
> However, I did not get any successful alignments locally, likely due to computational limitations.  
> I plan to run the STAR alignment step on an AWS EC2 instance for improved performance.

---

## 🛠️ Setup Instructions

Clone the repository and install all dependencies using Conda:

```bash
git clone https://github.com/Harshitha-MI/nextflow_rnaseq_pipeline.git
cd nextflow_rnaseq_pipeline
conda env create -f environment.yml
conda activate rnaseq_env
```

---

## 📥 Sample Data (Optional)

To test this pipeline, you can download example RNA-seq data from the [Johns Hopkins RNA-seq protocol](ftp://ftp.ccb.jhu.edu/pub/RNAseq_protocol/):

```bash
wget -c ftp://ftp.ccb.jhu.edu/pub/RNAseq_protocol/chrX_data.tar.gz
tar xvfz chrX_data.tar.gz
```

> This archive contains FASTQ files and reference genome files (`chrX.fa`, `chrX.gtf`) which can be used as input for testing the pipeline.

---

## 📁 Repository Structure

```
nextflow_rnaseq_pipeline/
├── rnaseq.nf              # Main Nextflow pipeline script
├── environment.yml        # Conda environment file
└── README.md              # This file
```

---

## 🧬 Dependencies

- [Nextflow](https://www.nextflow.io/)
- Trim Galore
- FastQC
- MultiQC
- STAR
- FeatureCounts (planned)
- SAMtools

> All tools above can be installed automatically using the included `environment.yml` file.

---

## 🧑‍💻 Author

**Sai Harshitha Muddamsetty**  
[LinkedIn](https://www.linkedin.com/in/harshitha-muddamsetty) | [GitHub](https://github.com/Harshitha-MI)
