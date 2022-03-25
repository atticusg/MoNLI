# Monotonicity NLI dataset (MoNLI)

## Description

This repository contains the MoNLI dataset, with the original splits used in the paper.

The files are in JSONL format, where each line is a dictionary with the following structure:

* `'sentence1'` (str): premise sentence
* `'sentence2'` (str): hypothesis sentence
* `'gold_label'` (str): either "entailment" or "neutral"
* `'sentence1_lex'` (str): the target lexical item in the premise
* `'sentence2_lex'` (str): the target lexical item in the hypothesis
* `'depth'` (int): the distance between `'sentence1_lex'` and `'sentence2_lex'` in the WordNet graph

## Dataset loading


```
import json

def load_split(filename):
    dataset = []
    with open(filename) as f:
        for line in f:
            d = json.loads(line)
            dataset.append(d)
    return dataset
```

## Citation

```
@inproceedings{geiger-etal-2020-neural,
	address = {Online},
	author = {Geiger, Atticus and Richardson, Kyle and Potts, Christopher},
	booktitle = {Proceedings of the Third BlackboxNLP Workshop on Analyzing and Interpreting Neural Networks for NLP},
	doi = {10.18653/v1/2020.blackboxnlp-1.16},
	month = nov,
	pages = {163--173},
	publisher = {Association for Computational Linguistics},
	title = {Neural Natural Language Inference Models Partially Embed Theories of Lexical Entailment and Negation},
	url = {https://www.aclweb.org/anthology/2020.blackboxnlp-1.16},
	year = {2020}}
```
