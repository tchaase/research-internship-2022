# Ressources

In the following, the different plattforms, packages and tools that were used will be briefly outlined. Firstly, I will give an overview of how the data was accessed. Then the data-set and the documentation of it will briefly be outlined. Then I will shortly mention the Git-Hub-Repo, the OSF site and the Zotero library and lastly I will mention a few packages / pipelines used and try to explain why the are helpful! 

## Data management 

All the data is available on [OpenNeuro](https://openneuro.org/datasets/ds003707/versions/1.0.0). The data was downloaded locally using [Data-Lad](https://www.datalad.org/)

**What is data-lad?**
```{toggle}
Data-lad is free and open source. It is used in the command line and allows to manage data-sets. The major upside of data-lad is that it allows keeping track of changes within the data. Data-lad allows version control of data, and therefore aids in project and data management. If the data-set were to be updated, I could have easily fetched those updates. 

The data-set was *installed* using the following command:
`datalad install https://github.com/OpenNeuroDatasets/ds003707.git`

After the installation of the data-set, one must use [datalad get](http://docs.datalad.org/en/stable/generated/man/datalad-get.html) to actually download the other files. The example below shows how to get all anatomical images for subject 1!
`datalad get ds003707/sub-01/anat/*
```

Then, after several attempts to [preprocess](./code/prepocessing.ipynb) the data, the data was uploaded to [brain-life](https://brainlife.io/project/63a02e876881d56fbfdeddfd). Here, the preprocessing of the data was done, as preprocessing on my own device using [docker](https://docs.docker.com/get-started/overview/) was not successful. 

### Evaluation of the documentation
The data-set that was thankfully published by {cite:t}`wanjia_abrupt_2021` was complete. There were no major files missing and the data was provided in the [BIDS](https://bids.neuroimaging.io/)-structure. However, a few files were missing and the documentation regarding the description of variable, as well as hints towards successful preprocessing were not sufficient. 

**Missing files**: A `.tsv` file containing participant information was missing. Therefore, participant information couldn't be used as covariates. 

**Insufficient documentation**: Naming of the variables within the event files and their correspondence to images/objects was hard to understand solely with the files contained within the data-set (i.e. the `.json` could have contained more descriptions). There were however some issues with the preprocessing. Although the individual steps were outlined within the paper, the data could not be processed. As the functional and T2w images were partial, the preprocessing pipelines often failed. However, this may also be caused by my specific device. More information regarding the computing environment as well as how the preprocessing pipelines were run would have helped. 

**Code documentation**: Lastly, the analyses steps outlined within the code that was thankfully available (!) were hard to understand given that the code was not commented.


## Git-Hub Repro

The repository for this projet is available [here](https://github.com/tchaase/research-internship-2022) 
The analyses were carried out within the [code](https://github.com/tchaase/research-internship-2022/tree/main/content/code) section.  


## Zotero & OSF-page

Other ressources regarding this project can be accessed via the [Open-Science-Framework Repository](https://osf.io/xwsm7/?view_only=7fa6bfda3b174b0e96083a1fcd466b32). 

## Open-Lab Notebook

Documentation about the projects progress is available [here](https://github.com/tchaase/research-internship-2022/tree/main/open_lab_notebook).

## Computational Environment

Firstly, the file [requirements.txt](https://raw.githubusercontent.com/tchaase/research-internship-2022/main/requirements.txt) within the root folder of this project contains the required packages for the jupyter-book rendering.

The `environment.yml` within the [code](https://raw.githubusercontent.com/tchaase/research-internship-2022/main/content/code/environment.yml) folder contains the conda-environment specifications for the computational environment used for all analyses processes. 

## Packages and Pipelines used

**fMRI-prep**

The data was preprocessed using [fMRI-prep](https://github.com/nipreps/fmriprep) (20.2.3). Traditionally, data-sets are preprocessed using various protocols or decision-criteria which may differ from one scientist to the next. {cite:p}`esteban_fmriprep_2019` introduces fmri-prep as a tool that saves time, but more importantly negates the interindividual differences between scientists when preprocessing data. Thus "**fMRI-prep** adresses the reproducibility concerns of the established protocols for fMRI preprocessing" {cite:p}`esteban_fmriprep_2019`.

The data was attempted to be preprocessed via docker on my device...
```{toggle}
I tried to preprocess the data on my device using [docker](https://www.docker.com/). Outlining the advantages of using containers would far exceed the goal of this section, but in short: Docker is a type of software container. It's open source. When using docker, everything required will be within a `container`, thereby the application will run in isolation from things that could influence the computations but are not necessary. If someone else were to use the same `docker image` we should get very much comparable results - much more comparable then if we ran them with all our differing depedencies etc. This [article](https://www.freecodecamp.org/news/a-beginner-friendly-introduction-to-containers-vms-and-docker-79a9e3e119b/#.3giab6wvo) greatly helped me to understand what docker is and what the upsides of it are. 
```
...but was preprocessed on [brain-life](https://brainlife.io/projects)! 

Also consult this article {cite:t}`esteban_analysis_2020`, in which the sub-work-flows are outlined etc. 

**MRI-QC**

The data was attempted to be quality controlled via ...unfortunately there were no group reports. Given the limited availability of data, standard procedure to exclude participants was ignored to progress this project. However,...

**pybids**

The structure of the data-set was explored using the...


**nilearn**

The analyses within the [linear_model](./code/linear_model.ipynb)-notebook were largely performed using...