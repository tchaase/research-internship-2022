# Ressources

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
The data-set that was thankfully published by {cite:t}`wanjia_abrupt_2021` was comlplete. There were no major files missing and the data was provided in the [BIDS](https://bids.neuroimaging.io/)-structure. However, a few files were missing and the documentation regarding the description of variable, as well as hints towards successful preprocessing were not sufficient. 

**Missing files**: A `.tsv` file containing participant information was missing. Therefore, participant information couldn't be used as covariates. 

**Insufficient documentation**: Naming of the variables within the event files and their correspondance to images/objects was hard to understand solely with the files contained within the data-set (i.e. the `.json` could have contained more descriptions). There were however some issues with the preprocessing. Although the individual steps were outlined within the paper, the data could not be processed. As the functional and T2w images were partial, the preprocessing pipelines oftenly failed. However, this may also be caused by my specific device. More information regarding the computing environment as well as how the preprocessing pipelines were run would have helped. 

**Code documentation**: Lastly, the analyses steps outlined within the code that was thankfully available (!) were hard to understand given that the code was not commented.


## Git-Hub Repro

research-internship-2022 \
├─content                       - React components reusable across scenes \
└───code                        - Contains all the `.ipynb` \
    └──data_exploration.ipynb        - Exploration of the MRI and event files \
    └──preprocessing.ipynb           - Contains documentation on the preprocessing steps that failed.  \
    └──linear_model.ipynb            - Here the GLM is developed.    \
    └──environment.yml               - This is the environment for the `.ipynb` above! \
└───markdown                    - Contains all the markdowns for the jupyter book.  \
    └── data_set.md                   - Contains the introduction and development of the research-question.  \ 
    └──discussion.md                 - This is the markdown for the discussion section. \
    └──documentation.md              - The current notebook. \
    └──references.md                 - Within this notebook, the references are embedded.  \ 
└───static                      - Contains all the static for the jupyter book. \  
└───config.yml                 - Specifies the configuration of the jupyter book \ 
└───toc.yml                    - Contains the table of content. \  
└───con.py                      - Configuration file for the Sphinx documentation builder. \ 
└───index.md                    - The front page of the jupyter book. \ 
└───references.bib              - Contains all the references exported from Zotero. \ 
├─open_lab_notebook             - Contains the documentation for this project \ 
├─licence \
├─requirements.txt              - Specifies the requirements for the jupyter book.     \                   




## Zotero

## Open-Lab Notebook

## Computational Environment

## Did I work FAIR?
