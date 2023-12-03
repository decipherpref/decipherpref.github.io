---
layout: about
title: Home
permalink: /
subtitle:

news: false # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---

## DecipherPref

Human preference judgments are pivotal in guiding large language models (LLMs) to produce outputs that align with human values. Human evaluations are also used in summarization tasks to compare outputs from various systems, complementing existing automatic metrics. Despite their significance, however, there has been limited research probing these pairwise or $k$-wise comparisons. The collective impact and relative importance of factors such as output length, informativeness, fluency, and factual consistency are still not well understood. It is also unclear if there are other hidden factors influencing human judgments. In this paper, we conduct an in-depth examination of a collection of pairwise human judgments released by OpenAI. Utilizing the Bradley-Terry-Luce (BTL) model, we reveal the inherent preferences embedded in these human judgments. We find that the most favored factors vary across tasks and genres, whereas the least favored factors tend to be consistent, e.g., outputs are too brief, contain excessive off-focus content or hallucinated facts. Our findings have implications on the construction of balanced datasets in human preference evaluations, which is a crucial step in shaping the behaviors of future LLMs.

## Acknowledgement

Please cite the following paper in work that makes use of this dataset:

[DecipherPref: Analyzing Influential Factors in Human Preference Judgments via GPT-4](https://arxiv.org/abs/2305.14702)\
Yebowen Hu, Kaiqiang Song, Sangwoo Cho, Xiaoyang Wang, Hassan Foroosh, Fei Liu\
Main conference of Empirical Methods in Natural Language Processing (EMNLP 2023), Singapore

## Bibtex
```
@misc{hu2023decipherpref,
      title={DecipherPref: Analyzing Influential Factors in Human Preference Judgments via GPT-4}, 
      author={Yebowen Hu and Kaiqiang Song and Sangwoo Cho and Xiaoyang Wang and Hassan Foroosh and Fei Liu},
      year={2023},
      eprint={2305.14702},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```