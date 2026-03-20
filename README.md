# Fake News Detection using BERT

##  Problem Statement

Fake news has become a major issue in today’s digital world, where misleading information spreads rapidly through online platforms. It becomes difficult for people to identify whether the news they are reading is real or fake.

The objective of this project is to build a system that can automatically classify news articles as **Fake** or **Real** using Natural Language Processing and Transformer-based models.



##  Dataset

The dataset used in this project is taken from Kaggle:

https://www.kaggle.com/datasets/emineyetm/fake-news-detection-datasets

The dataset contains approximately 44,898 news articles, including both fake and real news. Each article consists of fields such as title and text, which are used for building the model.

Out of the total dataset:

- 23,481 are Real news samples

- 21,417 are Fake news samples

The dataset is fairly balanced, which helps in training the model effectively without bias toward any particular class.

##  Approach

In this project, I have followed a step-by-step approach.

First, I have loaded the fake and real news datasets and assigned labels:

- Fake news: 0
- Real news: 1

Then, I have combined both datasets into a single dataset and shuffled it to ensure randomness.

After that, I have created a new column called “content” by combining the title and text so that the model gets complete information.

Next, I have split the dataset into training and testing sets using an 80:20 ratio.

Then, I have used the BERT tokenizer to convert the text into numerical format, applied padding and truncation, and set a maximum sequence length of 256.

After preprocessing, I have created a PyTorch dataset and fine-tuned a pretrained BERT model for classification.

Finally, I evaluated the model and created a simple Gradio interface for user interaction.


##  Model Used

- **Model:** bert-base-uncased
- **Library:** HuggingFace Transformers
- **Framework:** PyTorch

BERT is a powerful NLP model that understands the context of words in a sentence, making it highly effective for text classification tasks.



##  Metrics

After training, I evaluated the model using:

- Accuracy – Measures overall correctness of predictions

- Precision – Measures how many predicted labels are actually correct

- Recall – Measures how well the model identifies all relevant cases

- F1-score – Harmonic mean of precision and recall

I also used a confusion matrix to visualize the model’s performance.

## Deployment

To make the project more interactive, I created a simple Gradio interface.

In this interface, a user can enter any news headline or article, and the model will predict whether it is fake or real.

This makes the project more practical and user-friendly.

## Challenges

Some challenges I observed:

- The model sometimes gets confused when fake news looks very realistic

- Long articles are truncated, which may lead to loss of important information

- Similar wording between fake and real news can cause misclassification
  
##  Improvements

The model can be improved by:

- Increasing maximum sequence length
- Training for more epochs
- Using DistilBERT for faster performance
- Hyperparameter tuning
- Handling class imbalance



##  Key Learnings

Through this project, I have learned:

- How to work with real-world NLP datasets
- How tokenization converts text into numerical format
- How transformer models like BERT work
- How to fine-tune pretrained models
- How to evaluate model performance
- How to build a simple deployment using Gradio

