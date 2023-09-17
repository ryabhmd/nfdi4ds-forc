# Field of Research Classification (FoRC)
<p align="center">
  <img src="https://github.com/ryabhmd/nfdi4ds-forc/assets/77779090/c9a3abec-0742-4c39-86da-5df76ce253a5" />

</p>

This is a repository for the dataset of the **Field of Research Classification (FoRC)** shared task, as part of the [NFDI for Data Science and Artificial Intelligence](https://www.nfdi4datascience.de/) project. Additionally, it is used for my master's thesis at Osnabrück University's Institute of Cognitive Science. 

## Overview

This repository is for constructing a dataset that can be used for the task of classifying scholarly papers into fields of research (FoR). The labels (i.e. FoR) are derived from the [Open Research Knowledge Graph (ORKG) research fields taxonomy](https://orkg.org/fields). The dataset is constructed based on two different sources, the ORKG, and [arXiv](https://www.kaggle.com/datasets/Cornell-University/arxiv?resource=download). Abstracts are added from [Crossref API](https://www.crossref.org/), [Semantic Scholar Academic Graph (S2AG) API](https://www.semanticscholar.org/product/api), and [OpenAlex](https://openalex.org/). 

## Pipeline

The dataset construction pipeline consists of:
1. Querying the ORKG rdfDump to get scholarly papers that contain the research field property (https://orkg.org/property/P30) and getting their metadata.
2. Obtaining abstracts from from Crossref API, S2AG API, and OpenAlex.
3. Sampling the arXiv snapshot with a random threshold (default is 50K) while keeping the original distribution.
4. Merging the two datasets and preprocessing.

## How to run

Before running the code, the following datasets need to be installed:
- 
Navigate to the repository directory and run the following commands:

### Requirements

```commandline
pip install -r requirements.txt
```

### Dataset construction

```commandline
python data_processing/process_merged_data.py
```


This will create a dataset at ```data_processing/data/merged_data.csv```. 
