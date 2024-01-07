# FineTunedSBERT
Text Similarity Detection and Sentiment Analysis of a Large Text via Fine-Tuned SBERT

## Abstract
I present a fine-tined Sentence Transformer (SBERT) architecture for encoding textual prompts, primarily focusing on discerning the similarity between two text prompts while considering their contextual nuances. The dataset employed for this text similarity detection task comprised pairs of questions from Quora. The approach involved initially generating raw embeddings through SBERT for each prompt pair, followed by computing cosine similarity between them. Pairs exhibiting a similarity greater than the 0.5 threshold were classified as similar. To enhance accuracy, I trained a Logistic Regression classifier using the generated embeddings and subsequently evaluated the model on a validation set. Post-evaluation, the model became adept at discerning the similarity between testing arbitrary statement pairs.

Furthermore, I fine-tuned the SBERT architecture, tailored specifically to the dataset at hand, for text sentiment analysis. For this particular task, I curated a dataset consisting of both negative and positive reviews of TV shows. Notably, I adapted the architecture of distiluse-base-multilingual-cased-v1, incorporating a dropout layer preceding the fully-connected dense layer. The model underwent training for 600 epochs, with a learning rate of 0.002, and was evaluated based on cross-entropy loss.

## Methodology
I used Sentence-BERT (SBERT) model – a modification of the pretrained BERT network that uses siamese and triplet network structures to derive semantically meaningful sentence embeddings that can be compared using cosine-similarity – to calculate our text embeddings. Our pipeline for pre-trained model was as follows:
![Approach_screenshot](https://github.com/MohtashimButt/FineTunedSBERT/blob/master/approach.png)
I then calculated the confusion matrix after comparing the results from the predicted labels with the actual labels given in the data. That confusion matrix was used to calculate the evaluation metrics mentioned below.
