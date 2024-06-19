---
aliases: 
tags:
  - academic
type:
  - report
---
# Reading Wikipedia to Answer Open-Domain Questions

> [!summary]
> This system returns answers to questions using Wikipedia articles. The process is two-fold: first, a Document Retriever identifies a small subset of all articles that contain relevant information with regards to the question. Secondly, a Document Reader looks at all paragraphs in the article, then each word/token in each paragraph, and returns the subset/window of words of text that most likely answers the question.

## Document Retriever

Given infinite time, resources, and a perfect Document Reader, this step would be unnecessary to identify highly accurate subsets of Wikipedia articles to answer any given question. Furthermore, the Document Retriever can even limit the entire system at times. 

> [!data]
> 
| Dataset      | Retriever (plain) | Retriever (+bigrams) |
| ------------ | ----------------- | -------------------- |
| SQuAD        | 76.1              | 77.8                 |
| CuratedTREC  | 85.2              | 86.0                 |
| WebQuestions | 75.5              | 74.4                 |
| WikiMovies   | 54.4              | 70.3                 |
> Table 3: Document retrieval results to illustrate the bottleneck the Document Retriever introduces. For example, even if the Document Reader model was 100% accurate, the system would be 70.3% accurate at retrieving answers at best

If the retriever mistakenly filters out articles that actually contained information relevant to the question, then the Document Reader immediately has no hope of answering a user's question.

With that being said, the Document Retriever is practically essential for reducing the workload of the Document Reader. Rather than combing through the nearly 7 million articles (as of April 2024), looking at every single paragraph and every token, a single low-computation calculation can be performed to rank documents by relevance, and then filter to the needs of the system. This way, the document reader only needs to consider a couple of articles and can afford to use highly effective but less efficient methods of extracting answers.

Here is how the Retriever works at a high level:

1. Turn all articles into vectors/lists of numbers
2. Turn the given question into a vector
3. Compare the question vector to the article vectors and rank the articles by how similar their vectors are

Furthermore, step 1 only needs to be performed one time assuming the articles do not change. To actually obtain these vectors for a given article or question, the authors opted for TF-IDF. To summarize, Term Frequency Inverse Document Frequency (TF-IDF) is simply a count of words in a document that takes into account how often that word appears in all documents as well.

> [!example] 
> ![[Reading Wikipedia to Answer Open-Domain Questions 2024-05-04 22.00.09.excalidraw|center|700]]

## Document Reader

### Paragraphs

For each token $p_i$ in a given paragraph $p$, obtain the values of each of these 4 types of features:

- Word embeddings
- Exact match
- Token features
- Aligned question embedding

#### Word Embeddings

[[Machine Learning Model|Machine Learning models]], at the end of the day, are mathematical algorithms that work on mathematical data. Text is no exception, so multiple methods have been developed to transform words and sentences into numerical representations. TF-IDF, which is described above, is one such method. However, word counts fall short of encoding the meaning of the words present in a document.

Word embeddings are an attempt encoding the meaning of words into vectors. At a high level, they are obtained by training models to predict the next word in a given document, or by associating vectors of words that commonly appear next to each other. For our purposes, we will make use of Glove, a [[Pre-Train|pre-trained]] word embeddings model.

#### Exact match



## References
1. [[@danqichenReadingWikipediaAnswer2017]]