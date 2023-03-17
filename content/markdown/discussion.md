# Discussion

This section covers two topics. 

1. Can I answer my question that was formulated and developed in the [introduction](data_set.md)?
2. Secondly, how was this whole project? Did I learn much? What were the biggest issues I ran into?

## Answering the research question
As of now, I am in no position to answer the research question. I did not manage to run a group-level model at this point. Therefore, I do not know if the chosen contrasts and the two conditions of previously seen images and previously not encountered images and objects differ statistically significantly in the brain activity between them. Thus, confirmatory statistics have not been performed yet.

Furthermore, no machine learning model was run yet. The main question that I wanted to answer within this project was if machine models can be used to predict if an image was seen before. I did not perform the corresponding analyses yet. Thus, the main goal was not reached.

I also mentioned that I am interested in hippocampal subfields. I did not even initiate the topic of hippocampal subfields in my analyses. 

All in all, *no research question was therefore answered*. In the future, I need to firstly figure out how I can run the group-level models with enough memory. I am thinking about upgrading the memory on my device and then running the analyses again.

Still, this project was far from a failure. Given that my main motivation was to learn how to analyse MRI data, I want to outline how this goal was reached in the next section and point towards areas where I want to learn more about. 

## What did I learn here?

I want to take the opportunity to briefly reflect on my progress within the research internship. 

When starting this project, I did have experience running scripts to analyze MRI data for me from a previous seminar on fMRI. I did not know what the individual steps meant, what they referred to, and why one would change certain variables (for example, in the [FirstLevelModel](https://nilearn.github.io/dev/modules/generated/nilearn.glm.first_level.FirstLevelModel.html)). After this project, I still do not have all the answers, but I did pick up various things that I want to mention:

**Docker**: Within this project, I had the opportunity to work with Docker to run preprocessing pipelines. In the beginning, Docker seemed like something I could never understand as it seemed incredibly complicated, but getting firsthand experiences with it, showed me that one can understand how Docker and the preprocessing pipelines work. However, I need more experience using this in the future and need to read further resources to gain more insight than a basic understanding of Docker.

**Preprocessing of fMRI data**: My data was previously not preprocessed. When choosing the dataset, I was not aware that the scans were partial scans and that this may cause issues for the preprocessing pipelines. I did not know that multi-run MRI data might require vast computational resources to preprocess the data. I did not know how to begin preprocessing the data. After this project, I am at a point where I could be given a dataset and preprocess it myself using various resources. Preprocessing was the area that I required most time for, but also what I learned most about.

**Machine learning**: The research internship involved a lot of sessions on what machine learning is, what it can do, and where the limits are. Even though I did not get to apply it for this project, it was largely demystified for me. I got to know some of the underlying math, and I am looking forward to using it as a tool in the future. Thus, I did not gain any actual experience with using it as of writing this, but I did gain knowledge on it.

**Projet management**: I want to explicitly mention that one valuable skill gained from this research internship is handling, organizing, and analyzing data in a way that others are able to perform the same analyses and gain the same insights. My data was organized with the BIDS structure, and along the way, I tried to make my data as **f**indable, **a**ccessible, **i**nteroperable, and **r**eusable. I linked all the resources used and used an openly accessible data set. The analyses and the data exploration and all parts of this project are accessible on GitHub. With the provided environments and the tips on how to use this environment, everything should be interoperable. Lastly, by using data previously published, I am reusing data and therefore adhering to the `FAIR` principle.

### What would I have done differently?

With every step of this project, I did have doubts if I am able to perform these analyses / preprocess the data, etc. From an outsider's perspective, a lot of the steps seemed insurmountable and as if they would require vast knowledge in programming. Although some coding knowledge was required, the documentation for all functions was stellar, and whenever I started working on a step, it was very much doable. However, some steps - such as preprocessing - did require a lot of time. If I were to restart this module now, I would choose data that is already preprocessed so I can spend more time on analyses. I also overestimated my device and its memory. I thought I could analyze multi-run data easily, which my device could not handle. Therefore, I would have choosen a simpler data-set. 



<center><img src="https://media.giphy.com/media/XCXOOR22U4RtwBTnve/giphy.gif" alt="logo" title="Github" width="400" height="280" /></center>
<center><sub><sup><sub><sup><sup>https://media.giphy.com/media/XCXOOR22U4RtwBTnve/giphy.gif </sup></sup></sub></sup></sub></center>