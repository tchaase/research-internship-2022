# Resources

In the following, the different platforms, packages and tools that were used will be briefly described. Firstly, I will give an overview of how the data was accessed. Then the data-set and the documentation of it will briefly be outlined. Then I will shortly mention the Git-Hub-Repo, the OSF site and the Zotero library, Lastly, I will mention a few packages and pipelines used and explain why they are helpful.

## Data management 

All the data is available on [OpenNeuro](https://openneuro.org/datasets/ds003707/versions/1.0.0). The data was downloaded locally using [Data-Lad](https://www.datalad.org/)

```{toggle}
Data-Lad is free and open source. It is used in the command line and allows to manage data-sets. The major upside of data-lad is that it allows keeping track of changes within the data. Data-Lad allows version control of data, and therefore aids in project and data management. his means that if the dataset were to be updated, one could easily fetch those updates. 

The data-set was *installed* using the following command:
        datalad install https://github.com/OpenNeuroDatasets/ds003707.git

After the installation of the data-set, one must use [datalad get](http://docs.datalad.org/en/stable/generated/man/datalad-get.html) to actually download the other files. The example below shows how to get all anatomical images for subject 1!
`datalad get ds003707/sub-01/anat/*
```

Then, after several attempts to [preprocess](../code/preprocessing.ipynb) the data, the data was uploaded to [Brain-Fife](https://brainlife.io/project/63a02e876881d56fbfdeddfd). Here, the preprocessing of the data was done, as preprocessing on my own device using [docker](https://docs.docker.com/get-started/overview/) was not successful. 

### Evaluation of the documentation
The data-set that was thankfully provided by {cite:t}`wanjia_abrupt_2021`. Overall, the data-set was complete. There were no major files missing and the data was provided in the [BIDS](https://bids.neuroimaging.io/) structure. However, a few files were missing and the documentation regarding the description of variables, as well as hints towards successful preprocessing were not sufficient. 

**Missing files**: The lack of a `.tsv file` containing participant information prevented the use of this information as covariates.

**Insufficient documentation**: The naming of variables within the event files and their correspondence to images/objects was difficult to understand based solely on the files contained within the dataset (i.e. the `.json` could have contained more descriptions). There were however some issues with the preprocessing. Although the individual steps were outlined within the paper, the data could not be processed. As the functional and T2w images were partial, the preprocessing pipelines often failed. However, this may also be caused by my specific device. More information regarding the computing environment as well as how the preprocessing pipelines were run would have helped. 

**Code documentation**: The code documentation was insufficient, as the analysis steps outlined within the code were not clearly commented.


## Git-Hub Repro

The repository for this project is available [here](https://github.com/tchaase/research-internship-2022). The repository has the following content

- [/content](https://github.com/tchaase/research-internship-2022/tree/main/content): Contains the analyses and markdown files. 
    - [/content/code](https://github.com/tchaase/research-internship-2022/tree/main/content/code): Contains the `.ipynb`, which contain the analyses. 
    - [/content/markdown](https://github.com/tchaase/research-internship-2022/tree/main/content/markdown): Contains the `.md`.
    - Additionally, this folder contains the files for the jupyter book (`_toc`, `_config`, `con.py`)
    - [/content/static](https://github.com/tchaase/research-internship-2022/tree/main/content/static): This folder contains images etc.
- [/data](https://github.com/tchaase/research-internship-2022/tree/main/data): If any necessary data is added to this project, it will be added to this folder. Currently empty. 
- [/open_lab_notebook](https://github.com/tchaase/research-internship-2022/tree/main/open_lab_notebook): Contains documentation of the project. 


## Zotero 

The exported library is accessible [here](https://github.com/tchaase/research-internship-2022/blob/main/content/references.bib) and displayed below!

<iframe src="https://bibbase.org/show?bib=https%3A%2F%2Fraw.githubusercontent.com%2Ftchaase%2Fresearch-internship-2022%2Fmain%2Fcontent%2Freferences.bib&commas=true&msg=embed"  frameborder="0" width="700" height="370"></iframe>

## OSF-page

Other ressources for this project are available on the projects repository on [OSF](https://osf.io/xwsm7/?view_only=7fa6bfda3b174b0e96083a1fcd466b32). 

## Open-Lab Notebook

Documentation about the projects progress is available [here](https://github.com/tchaase/research-internship-2022/tree/main/open_lab_notebook).

## Computational Environment

Firstly, the file [requirements.txt](https://raw.githubusercontent.com/tchaase/research-internship-2022/main/requirements.txt) within the root folder of this project contains the required packages for the jupyter-book rendering.

The [environment.yml](https://raw.githubusercontent.com/tchaase/research-internship-2022/main/content/code/environment.yml) within the `/content/code/` folder contains the conda-environment specifications for the computational environment used for all analyses processes. 

**How to use these files?**
```{toggle}
I assume that you already have access to the `Windows Subsytem for Linux`. If anything doesn't work also consult the [docs](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html). 

**Installation of conda.**
1. Open a new terminal and type the following lines (separately) into the terminal, pressing `Enter` after each one:

        wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
        bash Miniconda3-latest-Linux-x86_64.sh
    - This command downloads the latest version of Miniconda3 for Linux from the Anaconda repository.". 
1. A license agreement will be displayed and the bottom of the terminal will read `--More--`.
   Press `Enter` or the space bar until you are prompted with "Do you accept the license terms? [yes|no]."
   Type `yes` and then press `Enter`
1. The installation script will inform you that it is going to install into a default directory (e.g., `/home/$USER/miniconda3`).
   Leave this default and press `Enter`.
1. When you are asked "Do you wish the installer to initialize Miniconda3 by running conda init? [yes|no]," type `yes` and press `Enter`. Exit the terminal once the installation has finished.
1. Re-open the Ubuntu application.
   Type `which python` into the terminal and it should return a path (e.g., `/home/$USER/miniconda3/bin/python`).
   - If you do not see a path like this then please try typing `conda init`, closing your terminal, and repeating this step.
     If your issue is still not resolved skip the following step and contact an instructor on the #help-installation channel on the BHS Slack.
1. Type the following to remove the installation script that was downloaded:

        rm ./Miniconda3-latest-Linux-x86_64.sh

**Python packages**

Open a terminal and type the following commands:

        conda config --append channels conda-forge
        conda config --set channel_priority strict
        conda create env ---name yourname -f environment.yml 

Special thanks to [Peer Herholz](https://github.com/PeerHerholz) for allowing me to shamlessly copy and paste his introduction!

And lastly of course don't forget to...
        conda activate yourname
```

## Packages and Pipelines Used
  
<br>

**fMRI-prep**

The data was preprocessed using [fMRI-prep](https://github.com/nipreps/fmriprep) (20.2.3). Traditionally, data-sets are preprocessed using various protocols or decision-criteria which may differ from one scientist to the next. {cite:p}`esteban_fmriprep_2019` introduces fmri-prep as a tool that saves time, but more importantly negates the interindividual differences between scientists when preprocessing data. Thus "**fMRI-prep** adresses the reproducibility concerns of the established protocols for fMRI preprocessing" {cite:p}`esteban_fmriprep_2019`.

The data was attempted to be preprocessed via docker on my device...
```{toggle}
I tried to preprocess the data on my device using [docker](https://www.docker.com/). Outlining the advantages of using containers would far exceed the goal of this section, but in short: Docker is a type of software container. It's open source. When using docker, everything required will be within a `container`, thereby the application will run in isolation from things that could influence the computations but are not necessary. If someone else were to use the same `docker image` we should get very much comparable results - much more comparable then if we ran them with all our differing depedencies etc. This [article](https://www.freecodecamp.org/news/a-beginner-friendly-introduction-to-containers-vms-and-docker-79a9e3e119b/#.3giab6wvo) greatly helped me to understand what docker is and what the upsides of it are. 
```
...but was preprocessed on [brain-life](https://brainlife.io/project/63a02e876881d56fbfdeddfd)! 

Also consult this article {cite:t}`esteban_analysis_2020`, in which the sub-work-flows are outlined etc. 
 
 <br>
 
**MRI-QC**

The data was attempted to be quality controlled via [MRI-QC](https://github.com/nipreps/mriqc)(20.2.3; . In parallel to fMRI-prep, this was first attempted via docker. The data was quality controlled via brainlife. 

Sadly, `brainlife` does not provide the group report files, thus they cannot be linked here. Given the limited availability of data, standard procedure to exclude participants was ignored to progress this project. 
 
 <br>
 
**pybids**

The structure of the data-set was explored using [pybids](https://github.com/bids-standard/pybids). This tool is simply amazing to explore a BIDS data-sets...
 
```{note} 
**What does BIDS stand for?**

BIDS refers to the [brain imaging data strucuture](https://bids.neuroimaging.io/). When we do experiments using various neuroimaging methods, the resulting files can be very hard to keep track of. Imagine you had to pick a project up where someone else left it behind and you had no idea what the file `13032020_03_1244.dcm` means. With BIDS, both a structure of the files is suggested. Thus you will know which file you can expect where. Furthermore the file formats etc. is specified. Thus if the data-set you were given was in the BIDS structure, you would have very little troubles understanding what is already available and what you need to do! Also refer a description of this provided by {cite:t}`gorgolewski_brain_2016` .
```

...as within a BIDS data-set one knows which information is expected to be where, this allows convenient functions to explore such data-sets. This is something pybids enables. Also refer to {cite:t}`yarkoni_pybids_2019` .
 
 <br>
 
**nilearn**

The analyses within the [linear_model](../code/linear_model.ipynb) notebook were largely performed using [nilearn](https://nilearn.github.io/stable/index.html). 

The primary reason to use nilearn is that it also enables later machine learning techniques to analyze to MRI data. It is also possible to analyze functional connectivity with nilearn or do multi-voxel pattern analyses! And of course this is a open-source python package with stellar documentation!