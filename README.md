# Crisis Event Social Media Summarization with GPT-3 and Neural Reranking

This repository maintain the code used in the experiments reported in the paper **[Crisis Event Social Media Summarization with GPT-3 and Neural Reranking](#)**, accepted for publication at the **20th Annual Global Conference on Information Systems for Crisis Response and Management ([ISCRAM 2023](https://www.unomaha.edu/college-of-information-science-and-technology/iscram2023/index.php))**

> **Abstract:** Managing emergency events, such as natural disasters, requires management teams to have an up-to-date view of what is happening throughout the event. In this paper, we demonstrate how a method using a state-of-the-art open-sourced search engine and a large language model can generate accurate and comprehensive summaries by retrieving information from social media and online news sources.  We evaluated our method on the TREC CrisisFACTS challenge dataset using automatic summarization metrics (e.g., Rouge-2 and BERTScore) and the manual evaluation performed by the challenge organizers. Our approach is the best in comprehensiveness despite presenting a high redundancy ratio in the generated summaries. In addition, since all pipeline components are few-shot, there is no need to collect training data, allowing us to deploy the system rapidly.

## Approach

We use BM25 + monoT5 for document retrieval and summarize the top-k documents using GPT-3 with a query-based multi-document summarization prompt to generate relevant facts from social media posts and online news sources guided by the user's interest.

![Pipeline](figures/CrisisViscondePipeline.png)

The figure below shows an example of generated fact.

![Example of generated fact](figures/fact_example.png)

## Results

We evaluated our method on the TREC CrisisFACTS challenge dataset using automatic summarization metrics (e.g., Rouge-2 and BERTScore) and the manual evaluation performed by the challenge organizers. Our approach is the best in comprehensiveness despite presenting a high redundancy ratio in the generated summaries. In addition, since all pipeline components are few-shot, there is no need to collect training data, allowing us to deploy the system rapidly.

![Results](figures/comprehensiveness_icsrouge2.png)

## Reproducing

For generating facts, run this notebook: [CrsisFACTS.ipynb](https://github.com/neuralmind-ai/visconde-crisis-summarization/blob/main/CrisisFACT.ipynb)

See CrisisFACTS utilities repository for getting evaluation code: [CrisisFACTS/utilities](https://github.com/crisisfacts/utilities)

## How to cite
```
@misc{pereira2022iscram,
  author = {Pereira, Jayr and Fidalgo, Robson and Lotufo, Roberto and Nogueira, Rodrigo},
  title = {Crisis Event Social Media Summarization with GPT-3 and Neural Reranking},
  year = {2022}
}
```