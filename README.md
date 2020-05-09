# Extractive-text-summarization-using-clustering
Extractive text summarization using clustering of sentences 
## Text summarization
Text summarization are of two types
### Abstractive
The abstraction technique entails paraphrasing and shortening parts of the source document. The abstractive text summarization algorithms create new phrases and sentences that relay the most useful information from the original text — just like humans do.
### Extractive
The extractive text summarization technique involves pulling keyphrases from the source document and combining them to make a summary. The extraction is made according to the defined metric without making any changes to the texts.

Here I implement extractive text summarization. ie creating summary by selecting important sentences from a given text file.
1. Remove new line character from input file.
2. Split file into list of sentences.
3. Convert each sentences into fixed length vectors.
     I used skip-thought sentence encoder for this task.
     I used implementation proposed by this paper - [skip-thought vectors](https://arxiv.org/abs/1506.06726)
4. After creating vector representation I used K-Means clustering to project these vectors into a high dimentional space of predefined no of clusters( No of clusters = required no of sentences required in the summary ).
5. Each cluster represent semantically similar sentences which can be represented by a single sentence.The representative sentence of each cluster can be selected by choosing the sentence vector at the center of the cluster.          
6. Sentences at the cluster centers are ordered to make the summary.
