# BENG 469 Lab (scATAC-seq) instructions
Guest Instructor: Haikuo Li, Ph.D., Yale University<br>
February 2025<br>


## Aims & Scope
In this lab section, you will:<br>
→	Analyze and visualize fragment inserts in snATAC-seq data<br>
→	Understand quality control procedures in snATAC-seq data analysis<br>
→	Get familiar with samtools<br>
→	Learn basic Python coding skills<br>
→	(Optional) Downstream snATAC-seq data analysis and data mining<br>


## Pre-lab tasks
### Preparation for the main task
#### Software downloading
Here, we will have a main lab task which is primarily based on Python.<br>
You may run Python with the Yale HPC (recommended), or with your labtop or other resources.<br>
You may run Python in Jupyter Notebook (recommended) or in the Linux Shell interface.<br>
<br>
•	Have ```pysam``` installed in your Python.<br>
•	Test by running these 3 commands in Python. Make sure they are all installed, and you shouldn’t see any error messages.<br>
```
import pysam
import collections
import matplotlib.pyplot as plt
```

We will also use samtools (https://www.htslib.org/), which is a package used in the Linux Shell interface. If you are using the Yale HPC, you may simply have samtools ready to be used by this Linux command:

```module load SAMtools``` (the current default version is 1.21-GCC-12.2.0 on HPC)<br>

•	If you are not using the Yale HPC, make sure samtools is installed. To check successful installation, you may run:<br>

```samtools --version```

<br>

#### Data downloading
•	We will download some BAM files provided by Cusanovich and Hill, et al. (database link: https://atlas.gs.washington.edu/mouse-atac/data/).
<br>•	First, we will analyze the Cerebellum BAM data (Cerebellum_62216.bam). Since the original BAM file is big (2.1G), we generated a 10% downsampled subset for you (Link: https://docs.google.com/uc?export=download&id=1bubrwts2I_J-woZTVwyzlkIuyMX9_3rL). You should download this subset and upload it to your own Linux workspace.
<br>•	Second, choose any tissue you like, other than the cerebellum, that is available in this database. Download its BAM file (Note: not the .bam.bai which is the index file) and make sure the .bam file is available in your own Linux workspace (you may use ```wget```).
<br>•	Do some online search and learn what a SAM/BAM file is.
<br>•	(Optional) For Python training purposes, download a small demo data from my GitHub (https://github.com/HaikuoLi/Yale_BENG469_teaching/blob/main/ATAC_meta.csv) and upload it to your workspace. You may skip this if you are good at Python already.

<br>

### Preparation for the minor task (optional)
If we have enough time for extra lab tasks, we will learn how to perform downstream snATAC-seq data analysis with SnapATAC2 or Signac, two popular analysis packages, following publicly available vignettes.<br>

•	If you prefer Python, have ```SnapATAC2``` installed.<br>
•	If you prefer R (RStudio), have ```Signac``` installed.<br>
