## Project Objective
Disasters often generate massive volumes of social media posts. However, distinguishing real, actionable disaster-related information from unrelated chatter remains a challenge.

This project seeks to solve the binary text classification problem of identifying whether a given tweet describes a real disaster (target = 1) or not (target = 0). This task is significant in the field of Natural Language Processing as it involves challenges such as short text classification, informal language, and handling noisy and ambiguous data — all of which are common in real-world NLP applications.


## Literature Review
**BERTweet** 
https://aclanthology.org/2020.emnlp-demos.2/
https://github.com/VinAIResearch/BERTweet

**DistilBERT**
https://arxiv.org/pdf/1910.01108

**BERT**
https://github.com/ycdeng4/ie7500_group7/blob/26eef2eea1f1998aadd88150ec9977cdf71d5a9f/BERT-paper.pdf

**Random Forest**
https://github.com/ycdeng4/ie7500_group7/blob/8d9e36f417ad6b71402aa8832bc6f861e4f04806/Improved%20Random%20Forest%20Paper.pdf

## Benchmarking based on our experiment

| Model | Accuracy | F1-Score | Computational Efficiency |
|---|---|---|---|
| BERTweet | 84% | 85% | ~ 7'00 |
| DistilBERT | 85.11% | 81.8% | ~ 7'00 |
| Random Forest | 79% | 79% | 10 sec. |
|BERT|84%||~ 80'00|
## Model Implementation

### Framework Selection (Channie)
Hugging Face

### Dataset Preparation (Vy)
In order to prepare the dataset for training, several data preprocessing tasks are applied. This stage involves converting all text to lowercase along with the removal of URLs, @ mentions, hashtag symbols, HTML entities, excess whitespace and punctuations. With regards to hashtags, only the symbols are removed while the text attached to the hashtags are kept since it contains important information for analysis.

### Model Development (all)

### Training & Fine-Tuning (Claire)
We modified the following training arguments set via TrainingArguments to improve accuracy:

•Learning rate: 1e-5 
•Epochs: 3 
Fixed parameter:
• Batch size: 16
• Weight decay: 0.01
• Logging and evaluation every epoch

Below is the testing result: 

| No. | Epoch | Learning Rate | Cleaned text | Accuracy | F1 Score |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | 3 | 2e-5 | N | 83% | 80.0% |
| 2 | 3 | 2e-5 | Y | 84% | 81.2% |
| 3 | 3 | 1e-5 | Y | 85% | 81.7% |
| 4 | 5 | 1e-5 | Y | 84% | 80.8% |
| 5 | 3 | 5e-6 | Y | 84% | 80.8% |
| 6 | 5 | 5e-6 | Y | 84% | 80.6% |


### Evaluation & Metrics (Charlie)


