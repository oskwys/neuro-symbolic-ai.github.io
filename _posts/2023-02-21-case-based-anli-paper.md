---
layout: post
title:  "Case-Based Abductive Natural Language Inference"
date:   2023-02-21 10:46:00 +0000
categories: Publications
tags: question-answering multi-hop-inference abductive-inference case-based-reasoning sentence-transformers neuro-symbolic COLING2022
---

## Case-Based Abductive Natural Language Inference

**Authors:**

[Marco Valentino](/people.html#marco.valentino), Mokanarangan Thayaparan, Andre Freitas

**Venue:**

Proceedings of the 29th International Conference on Computational Linguistics (COLING 2022)

**Paper:**

[https://aclanthology.org/2022.coling-1.134/](https://aclanthology.org/2022.coling-1.134/)

**Source code:**

[https://github.com/ai-systems/case_based_anli](https://github.com/ai-systems/case_based_anli)

## Abstract

Most of the contemporary approaches for multi-hop Natural Language Inference (NLI) construct explanations considering each test case in isolation. However, this paradigm is known to suffer from semantic drift, a phenomenon that causes the construction of spurious explanations leading to wrong conclusions. 

In contrast, this paper proposes an abductive framework for multi-hop NLI exploring the retrieve-reuse-refine paradigm in Case-Based Reasoning (CBR). Specifically, we present Case-Based Abductive Natural Language Inference (CB-ANLI), a model that addresses unseen inference problems by analogical transfer of prior explanations from similar examples. 

We empirically evaluate the abductive framework on commonsense and scientific question answering tasks, demonstrating that CB-ANLI can be effectively integrated with sparse and dense pre-trained encoders to improve multi-hop inference, or adopted as an evidence retriever for Transformers. Moreover, an empirical analysis of semantic drift reveals that the CBR paradigm boosts the quality of the most challenging explanations, a feature that has a direct impact on robustness and accuracy in downstream inference tasks.

![Image description](/assets/images/publications/case-based-anli.png)

## Reproducibility

Welcome! :) 

In this document, you can find the guidlines to reproduce the [CB-ANLI model](https://aclanthology.org/2022.coling-1.134/) presented at COLING 2022.

## Setup:

Install the [sentence-transformers](https://www.sbert.net/) package:

`pip install -U sentence-transformers`

Install the [faiss-gpu](https://pypi.org/project/faiss-gpu/) package:

`pip install faiss-gpu`

## Abductive Natural Language Inference:

In the public repository, you can find the code     for answering and explaining science questions through the BM25 and Sentence-BERT version presented in the paper. 

To run the models on [WorldTree](https://github.com/umanlp/tg2019task), launch the following commands:

CB-ANLI BM25:

`python ./cb_anli_bm25.py`

CB-ANLI Sentence-BERT:

`python ./cb_anli_sbert.py`

The scripts in `./case_based_modules/*` contain the main classes adopted to model the Case-Based Abductive Inference paradigm. 

## Citation
We hope you find this document useful. If you use CB-ANLI in your work, please consider citing our paper!

```
@inproceedings{valentino-etal-2022-case,
    title = "Case-Based Abductive Natural Language Inference",
    author = "Valentino, Marco  and Thayaparan, Mokanarangan  and Freitas, Andr{\'e}",
    booktitle = "Proceedings of the 29th International Conference on Computational Linguistics",
    month = oct,
    year = "2022",
    address = "Gyeongju, Republic of Korea",
    publisher = "International Committee on Computational Linguistics",
    url = "https://aclanthology.org/2022.coling-1.134",
    pages = "1556--1568"
}
```

For any issues or questions, feel free to contact us at marco.valentino@idiap.ch
