# TRAM: Benchmarking Temporal Reasoning for Large Language Models
This repository contains datasets and model descriptions used for [TRAM: Benchmarking Temporal Reasoning for Large Language Models](https://arxiv.org/abs/2310.00835).

## Datasets
TRAM encompasses ten temporal reasoning tasks, presented as multiple-choice questions (MCQs) across a range of time-related domains. For clarity, we ensure that each question has only one correct answer. TRAM incorporates existing natural language understanding datasets, human-crafted templates and questions, web sources, and program generation. Answers have been derived through a combination of expert annotations and programmatic generation. The benchmark includes **526,068** problems in total. For each dataset, we introduce a few-shot development set, with 5 questions per category, and a separate test set for evaluation. 
All datasets used for experiments can be downloaded in /datasets folder. Overview of ten tasks included in the benchmark:

| **Task** | **Data Size** | **# Problem Types** | **Metrics** | **Answer Type** | **Text Sources** |
|----------|---------------|---------------------|-------------|-----------------|------------------|
| &nbsp;  | &nbsp;  | &nbsp;  | &nbsp;  | &nbsp;  | **Foundational Temporal Understanding Tasks** |
| Ordering | 29,462 | 2 | Acc. | 3-Way MC | MCTACO<sup>[1]</sup>, Wikipedia, Misc. |
| Frequency | 4,658 | 6 | Acc. | 3-Way MC | MCTACO<sup>[1]</sup>, SQuAD<sup>[2]</sup>, Misc. |
| Duration | 7,232 | 7 | Acc. | 3-Way MC | Same |
| Typical Time | 13,018 | 4 | Acc.| 3-Way MC | Same |
| | | | | | **Temporal Interpretation and Computation Tasks** |
| Amb. Res. | 3,649 | 5 | Acc. | 3-Way MC | Misc. |
| Arithmetic | 15,629 | 9 | Acc. | 4-Way MC | Same |
| | | | | | **Advanced Temporal and Conceptual Understanding Tasks** |
| Relation | 102,462 | 1 | Acc./F1 | 3-Way MC | TempEval-3<sup>[3]</sup> |
| Temporal NLI | 282,144 | 1 | Acc./F1 | 3-Way MC | MNLI<sup>[4]</sup>, SNLI<sup>[5]</sup> |
| Causality | 600 | 2 | Acc. | 2-Way MC | COPA<sup>[6]</sup>, Misc. |
| Storytelling | 67,214 | 1 | Acc. | 2-Way MC | ROC<sup>[7]</sup>, SCT<sup>[8]</sup> |

<sub>[1] Zhou et al., 2019(https://aclanthology.org/D19-1332/), [2] Rajpurkar et al., 2016 (https://aclanthology.org/D16-1264/), [3] Uzzaman et al., 2013 (https://aclanthology.org/S13-2001/), [4] Williams et al., 2018 (https://aclanthology.org/N18-1101/), [5] Bowman et al., 2015 (https://aclanthology.org/D15-1075/), [6] Roemmele et al., 2011 (https://aaai.org/papers/02418-choice-of-plausible-alternatives-an-evaluation-of-commonsense-causal-reasoning/), [7] Mostafazadeh et al., 2016 (https://aclanthology.org/N16-1098/), [8] Mostafazadeh et al., 2017 (https://aclanthology.org/W17-0906/)</sub>

**Note:** The “Data Size" column aggregates totals from both the development and test sets. “K-Way MC" signifies a multiple-choice response format with K options. *Amb. Res.* denotes Ambiguity Resolution. *NLI* stands for natural language inference. “Same" indicates the text source is the same as the row above.

For more details, please refer to the paper.

## Models
We evaluate the performance of several well-known language models on the TRAM benchmark, which is organized into two main categories.
In the first category, we consider four popular large language models (LLMs): the open-source models [Llama-2-13b-chat](https://arxiv.org/pdf/2307.09288.pdf) and [Vicuna-13b-v1.1](https://lmsys.org/blog/2023-03-30-vicuna/), and the closed-source models [PaLM-bison-chat](https://arxiv.org/pdf/2305.10403.pdf), GPT-3.5-turbo, and [GPT-4](https://arxiv.org/pdf/2303.08774.pdf).
We evaluate each model using two prompting strategies: standard prompting (SP) and chain-of-thought (CoT) prompting. Under both strategies, the models undergo tests in zero-shot and 5-shot settings.
For all models, we apply greedy decoding (i.e., temperature = 0) for response generation. Each of these models is accessed using its corresponding API key.
In the second category, we consider minimal supervision as opposed to traditional fully supervised learning in order to establish baseline evaluations. Specifically, we employ four representative BERT-style models, including BERT-base, BERT-large, RoBERTa-base, and RoBERTa-large.
For the temporal NLI task, we employ the Sequence Classification variant of BERT and RoBERTa from Huggingface (i.e., BertForSequenceClassification and RobertaForSequenceClassification), given its suitability for the task's structure. However, for the other tasks, we utilize the Multiple Choice variant of BERT and RoBERTa from Huggingface (i.e., BertForMultipleChoice, RobertaForMultipleChoice).



