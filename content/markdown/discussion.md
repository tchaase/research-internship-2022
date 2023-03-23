# Discussion

This section covers two topics. 

1. Can I answer my question that was formulated and developed in the [introduction](data_set.md)?
2. Secondly, how was this whole project? Did I learn much? What were the biggest issues I ran into?

Firstly, let's summarize what has been done within this project so far and then evaluate if it meets the goals I initially outlined.

I have preprocessed the data, but I had to deviate from my original plan and not use docker for the preprocessing. This was outlined in a [a notebook on preprocessing](../code/preprocessing.ipynb). Then, I explored both the tasks and some MRI images in the [data exploration](../code/data_exploration.ipynb). After that, I set up a general linear model, but I only ran it for one participant and initiated group-level analyses, which I did not complete due to a lack of memory. What does this mean for the research questions?

## Answering the research question
As of now, I am in no position to answer the research question. As I did not manage to run a group-level model at this point, I do not know if the chosen contrasts and the two conditions of previously seen scenes and previously not encountered scenes (and objects) differ in the brain activity between them. Thus, confirmatory statistics have not been performed yet, therefore I cannot make conclusions in relation to differences in brain activity. 

Furthermore, no machine learning model was run yet. The main question that I wanted to answer within this project was if machine models can be used to predict if an image was seen before. I did not perform the corresponding analyses yet. Thus, this goal was not reached.

I also mentioned that I am interested in hippocampal subfields. I did not run any analyses regarding the topic of hippocampal subfields yet. 

All in all, unfortunately *no research question was therefore answered*. In the future, I need to firstly figure out how I can run the group-level models with enough memory. I am thinking about upgrading the memory on my device and then running the analyses again.

Still, this project was *far from a failure*. Given that my main motivation was to learn how to analyse MRI data, I want to outline how this goal was reached in the next section and point towards areas where I want to learn more about. 

## What did I learn?

I want to take the opportunity to briefly reflect on my progress within the research internship. 

When starting this project, I did have experience running scripts to analyze MRI data from a previous seminar on fMRI. I did not know what the individual steps meant, what they referred to, and why one would change certain variables (for example, in the [FirstLevelModel](https://nilearn.github.io/dev/modules/generated/nilearn.glm.first_level.FirstLevelModel.html)). After this project, I still do not have all the answers, but I did pick up various things that I want to mention:

**Docker**: Within this project, I had the opportunity to work with Docker to run preprocessing / quality controle pipelines. In the beginning, Docker seemed like something I could never understand as it seemed incredibly complicated. After getting firsthand experiences with it, I realized that I am able to grasp what Docker is about and use to aid my goal - that is being able to analyze MRI data while adhering to the standards of the Open-Science movement.  However, I need more experience using this in the future and need to read further resources to gain more insight than a basic understanding of Docker. In particular, I do understand what the individual steps of for example MRI-QC are about, but still as I lack experience with the quality measures as I did not analyze a vast amount of data yet, I don't know how to interpret all of them. 

**Preprocessing of fMRI data**: My data was previously not preprocessed. When choosing the dataset, I was not aware that the scans were partial scans and that this may cause issues for the preprocessing pipelines. I did not know that multi-run MRI data might require vast computational resources to be preprocessed. I did not know how to begin preprocessing the data. After this project, I am at a point where I could be given a dataset and preprocess it myself using various resources. Preprocessing was the area that I required most time for, but also what I learned most about. 

**Machine learning**: The research internship involved a lot of content sessions on what machine learning is, what it can do, and where the limits are. Even though I did not get to apply it for this project, it was largely demystified for me. I got to know some of the underlying math, and I am looking forward to using it as a tool in the future. Thus, I did not gain any actual experience with using it as of writing this, but I did gain knowledge on it. It was furthermore a nice experience working with a group engaged in the topic and reading about machine learning continuesly as papers and articles worth reading were mentioned by our supervisors. Here are two I enjoyed in particular! 

1. One blog post from {cite:t}`mineault_2022_2023` that gave a nice overview over what neuroAI is all about. (The blog post is directly accessible [here](https://xcorr.net/2023/01/01/2022-in-review-neuroai-comes-of-age/)).
2. An article published in the Journal of Neuroscience on the interface of neuroscience and ANNs by {cite:t}`cohen_recent_2022`, which is accessible [here](https://www.jneurosci.org/content/42/45/8514?rss=1).

**Projet management**: I want to explicitly mention that one valuable skill gained from this research internship is handling, organizing, and analyzing data in a way that others are able to perform the same analyses and gain the same insights. My data was organized with the BIDS structure, and along the way, I tried to make my data as **f**indable, **a**ccessible, **i**nteroperable, and **r**eusable as I am able to. I linked all the resources used and used an openly accessible data set. The analyses and the data exploration and all parts of this project are accessible on GitHub. With the provided environments and the tips on how to use this environment, everything should be interoperable. Lastly, by using data previously published, I am reusing data and therefore adhering to the `FAIR` principle {cite:p}`wilkinson_fair_2016`.

### What would I have done differently?

With every step of this project, I had doubts if I was able to perform the analyses, preprocess the data, etc. From an outsider's perspective, a lot of the steps seemed insurmountable and as if they would require vast knowledge in programming. Although some coding knowledge was required, the documentation for all functions was stellar, and whenever I started working on a step, it was very much doable. However, some steps - such as preprocessing - did require a lot of time. If I were to restart this module now, I would choose data that is already preprocessed so I can spend more time on analyses. I also overestimated my device and its memory. I thought I could analyze multi-run data easily, which my device could not handle. Therefore, I would have chosen a simpler dataset.

But most importantly, I would have skipped the doubting part and just read the resources I am now aware of that I did try to link throughout the documentation of this project. To summarize: I did learn a lot, and the project required a decent amount of time. I failed to answer my research question that I set for myself, but I did learn a lot along the way. Most things I learned, I picked up by working with the data myself, which was more enjoyable than all previous modules where one would learn by listening to someone else speaking. Thus, I evaluate this research internship positively.



<center><img src="https://media.giphy.com/media/XCXOOR22U4RtwBTnve/giphy.gif" alt="logo" title="Github" width="400" height="280" /></center>
<center><sub><sup><sub><sup><sup>https://media.giphy.com/media/XCXOOR22U4RtwBTnve/giphy.gif </sup></sup></sub></sup></sub></center>


```{toggle}
Here is another very [helpful ressource](https://youtu.be/dQw4w9WgXcQ) that explains the phenomom of `Rick Rolling`.
```