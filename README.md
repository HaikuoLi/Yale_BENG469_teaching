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
You may run Python with the Yale HPC (recommended) (https://beng469.ycrc.yale.edu/), or with your labtop or other resources.<br>
You may run Python in Jupyter Notebook (recommended) or in the Linux Shell interface.<br>
<br>
•	Have ```pysam```, ```pandas``` and ```matplotlib``` installed in your Python.<br>
  o	If you are using the Yale HPC, load the miniconda module, create a new conda environment containing python, pysam, pandas, matplotlib and jupyter. Unix scripts provided below:<br>
  ```
##you must enter a computation node to do anything. So, salloc
salloc

##this command makes sure you have no modules loading now
module purge

## now let's create a new miniconda environment
module load miniconda

conda create -n atac_class python jupyter jupyterlab pysam matplotlib pandas
#enter y when the system asks you. This takes 3-5 minutes

conda activate atac_class
#you shouldn't see any errors with this command

ycrc_conda_env.sh update
# now you can find this new miniconda environment on Yale HPC jupyter notebook
```
<br>
•	No matter whether you use the Yale HPC or not, test by running these 3 commands in Python. Make sure they are all installed, and you shouldn’t see any error messages.<br>

```
import pysam
import collections
import matplotlib.pyplot as plt
```

<br>
We will also use samtools (https://www.htslib.org/), which is a package used in the Linux Shell interface. If you are using the Yale HPC, you may simply have samtools ready to be used by this Unix command:

```module load SAMtools```<br>

•	If you are not using the Yale HPC, make sure samtools is installed. To check successful installation, you may run:<br>

```samtools --version```


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
