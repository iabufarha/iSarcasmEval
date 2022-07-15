# iSarcasmEval Dataset
 This repository contains the datasets used for [iSarcasmEval shared-task ](https://sites.google.com/view/semeval2022-isarcasmeval/home)  (Task 6 at SemEval 2022). The full details are available in the overview paper [SemEval-2022 Task 6: iSarcasmEval, Intended Sarcasm Detection in English and Arabic](https://aclanthology.org/2022.semeval-1.111/).

## The data
- We introduce a new data collection method where the sarcasm labels for texts are provided by the authors themselves, thus eliminating labelling proxies (in the form of predefined tags, or third-party annotators). 

- We use this method to collect two datasets, one in English and one in Arabic.

- Within each dataset, for each sarcastic text, we also ask its author to rephrase the text to convey the same intended message without using sarcasm. 

- Finally, we ask linguistic experts to further label each text into one of the categories of ironic speech defined by Leggitt and Gibbs (2000): sarcasm, irony, satire,understatement, overstatement, and rhetorical question. 

- For the Arabic dataset, we also include the dialect label of the text.

As such, each text in the datasets has the following information attached to it:

1. a label specifying its sarcastic nature (sarcastic or non-sarcastic), provided by its author;

2. a rephrase provided by its author that conveys the same message non-sarcastically; 

3. a label specifying the category of ironic speech that it reflects, provided by a linguistic expert (English only); and

4. a label specifying the dialect (Arabic only).

## Task Details
Using these two datasets we formulate three sub-tasks for each language:

- SubTask A: Given a text, determine whether it is sarcastic or non-sarcastic;

- SubTask B (English only): A binary multi-label classification task. Given a text, determine which ironic speech category it belongs to, if any;

- SubTask C: Given a sarcastic text and its non-sarcastic rephrase, i.e. two texts that convey the  same  meaning,  determine  which  is  the sarcastic one.

### Metrics:

For all the sub-tasks, precision, recall, accuracy and macro-F1 will be reported. The main metrics are:

- SubTask A: F1-score for the sarcastic class. This metric should not be confused with the regular macro-F1. Please use the following code snippet:
```
from sklearn.metrics import f1_score, precision_score, recall_score

f1_sarcastic = f1_score(truths,submitted, average = "binary", pos_label = 1)

OR

p_score_sarcastic = precision_score(truths,submitted, average = "binary", pos_label = 1)
r_score_sarcastic = recall_score(truths,submitted, average = "binary", pos_label = 1)
f1_sarcastic=(2*p_score_sarcastic*r_score_sarcastic)/(p_score_sarcastic+r_score_sarcastic)

```

- SubTask B: Macro-F1 score

- SubTask C: Accuracy	

## Citation
Please use the following citation if you use any of iSarcasmEval datasets:
```
@inproceedings{abu-farha-etal-2022-semeval,
    title = "{S}em{E}val-2022 Task 6: i{S}arcasm{E}val, Intended Sarcasm Detection in {E}nglish and {A}rabic",
    author = "Abu Farha, Ibrahim  and
      Oprea, Silviu Vlad  and
      Wilson, Steven  and
      Magdy, Walid",
    booktitle = "Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022)",
    month = jul,
    year = "2022",
    address = "Seattle, United States",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.semeval-1.111",
    pages = "802--814",
    abstract = "iSarcasmEval is the first shared task to target intended sarcasm detection: the data for this task was provided and labelled by the authors of the texts themselves. Such an approach minimises the downfalls of other methods to collect sarcasm data, which rely on distant supervision or third-party annotations. The shared task contains two languages, English and Arabic, and three subtasks: sarcasm detection, sarcasm category classification, and pairwise sarcasm identification given a sarcastic sentence and its non-sarcastic rephrase. The task received submissions from 60 different teams, with the sarcasm detection task being the most popular. Most of the participating teams utilised pre-trained language models. In this paper, we provide an overview of the task, data, and participating teams.",
}


```
