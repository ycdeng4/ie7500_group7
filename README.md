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
Bert-base-uncased model from Hugging Face framwork. 

### Dataset Preparation
In order to prepare the dataset for training, several data preprocessing tasks are applied. This stage involves converting all text to lowercase along with the removal of URLs, @ mentions, hashtag symbols, HTML entities, excess whitespace and punctuations. With regards to hashtags, only the symbols are removed while the text attached to the hashtags are kept since it contains important information for analysis.

### Model Development

Model Chosen: BERT (Bidirectional Encoder Representations from Transformers)

Architecture: Base size (12 layers, 768 hidden units, 12 attention heads, ~110M parameters)

Tokenizer: WordPiece tokenizer with lowercase preprocessing (i.e., uncased)

Training Data: BookCorpus + English Wikipedia

Use Case: General-purpose language understanding (text classification, QA, NER, etc.)

Modularity:

• Preprocessing, and tokenization were implemented as reusable components in separate blocks.
 
• Easy to adapt for other classification tasks or swap in another transformer model.

### Training & Fine-Tuning

To improve BERT model, we will conduct the following strategyies: 
- clean and preprocess raw data to remove noise as mentioned in the dataset preparation step
- hyperparameter tuning including learning rate and epoch tuning


### Evaluation & Metrics
In order to measure how well these models correctly classify the tweets in the dataset, several evaluation metrics were used including accuracy and F1-score. These metrics were chosen due to the balance between correctly catching as many disaster related tweets as possible while also minimizing false positives. Accuracy tells us how often the model was correct overall, while the F1 score helps balance how many real disaster tweets it correctly identifies (recall) and how many false positives it avoids (precision). Both of these metrics are important for this use case of identifying disaster related tweets in emergency situations. We also measured how long it takes to run each model to identify the computational cost of each model. Based on our experimentation so far, it appears that the BERT models have higher accuracy and F1 scores, but they also have a higher computational cost when compared to the simpler random forest model. These results have guided us to proceed with refining one of the BERT models for future stages of this project.

