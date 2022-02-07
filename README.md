# iSarcasmEval Dataset
 This repository contanst the datasets used for [iSarcasmEval shared-task ](https://sites.google.com/view/semeval2022-isarcasmeval/home)  (Task 6 at SemEval 2022).

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

- SubTask A: F1-score for the sarcastic class.

- SubTask B: Macro-F1 score

- SubTask C: Accuracy	

## Citation
Please use the following citation if you use any of iSarcasmEval datasets:
```
@inproceedings{abufarha-etal-2022-semeval,
title = "SemEval 2022: iSarcasmEval - Intended Sarcasm Detection in English and Arabic",
    author = "Abu Farha, Ibrahim  and
    Oprea, Silviu  and
    Wilson, Steve", and
    Magdy, Walid",
    booktitle = "Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022)",
    month = july,
    year = "2022",
    }

```