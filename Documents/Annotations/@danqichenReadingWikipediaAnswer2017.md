---
alias: Reading Wikipedia to Answer Open-Domain Questions
authors: Danqi Chen, Danqi Chen, Adam Fisch, Adam Fisch, Jason Weston, Jason Weston, Antoine Bordes, Antoine Bordes
year: 2017
type: paper
tags: academic
page(s): 1870–1879
---
> [!abstract]
> This paper proposes to tackle open-domain question answering using Wikipedia as the unique knowledge source: the answer to any factoid question is a text span in a Wikipedia article. This task of machine reading at scale combines the challenges of document retrieval (finding the relevant articles) with that of machine comprehension of text (identifying the answer spans from those articles). Our approach combines a search component based on bigram hashing and TF-IDF matching with a multi-layer recurrent neural network model trained to detect answers in Wikipedia paragraphs. Our experiments on multiple existing QA datasets indicate that (1) both modules are highly competitive with respect to existing counterparts and (2) multitask learning using distant supervision on their combination is an effective complete system on this challenging task.

# Annotations  
(4/29/2024, 7:02:34 PM)

([Danqi Chen et al., 2017, p. 1870](zotero://select/library/items/798T3EPX)) First-pass impressions:  
We have many Wikipedia articles. We use the term frequency in each article to create embeddings for them. So when a question is posed, we get the term frequency of that question, and then match it with the most similar article.  
At this point, we then use a Recurrent Neural Network that was trained to identify the most relevant paragraph given a question. This way, the paragraph that (hopefully) contains the answer is extracted.

“Articles and questions are compared as TF-IDF weighted bag-ofword vectors.” ([Danqi Chen et al., 2017, p. 1872](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=3&annotation=UPLVEDAE))

“n-gram features. Our best performing system uses bigram counts” ([Danqi Chen et al., 2017, p. 1872](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=3&annotation=ILVLK3GX))

([Danqi Chen et al., 2017, p. 1872](zotero://select/library/items/798T3EPX)) 5 documents are retrieved for the Document Reader to process

“We keep most of the pre-trained word embeddings fixed and only fine-tune the 1000 most frequent question words because the representations of some key words such as what, how, which, many could be crucial for QA systems.” ([Danqi Chen et al., 2017, p. 1873](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=4&annotation=A8IZ4HS3))

“the last part we incorporate is an aligned question embedding falign(pi) = ∑ j ai,jE(qj), where the attention score ai,j captures the similarity between pi and each question words qj.” ([Danqi Chen et al., 2017, p. 1873](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=4&annotation=JZG56U7I))

“Compared to the exact match features, these features add soft alignments between similar but non-identical words (e.g., car and vehicle).” ([Danqi Chen et al., 2017, p. 1873](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=4&annotation=K92EFHT3))

“We compute q=∑ j bjqj where bj encodes the importance of each question word: bj = exp(w · qj) ∑ j′ exp(w · qj′ ) ,” ([Danqi Chen et al., 2017, p. 1873](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=4&annotation=B6ISL2U4))

“Concretely, we use a bilinear term to capture the similarity between pi and q and compute the probabilities of each token being start and end as: Pstart(i) ∝ exp (piWsq) Pend(i) ∝ exp (piWeq)” ([Danqi Chen et al., 2017, p. 1873](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=4&annotation=A2J2S3TI))

“That is, a model is required to answer a question given the whole of Wikipedia as a resource; it is not given the relevant paragraph as in the standard SQuAD setting.” ([Danqi Chen et al., 2017, p. 1874](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=5&annotation=4762567Z))

“All the QA datasets presented above contain training portions, but CuratedTREC, WebQuestions and WikiMovies only contain question-answer pairs, and not an associated document or paragraph as in SQuAD, and hence cannot be used for training Document Reader directly.” ([Danqi Chen et al., 2017, p. 1875](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=6&annotation=SHEYNYYP))

“Specifically, we compute the ratio of questions for which the text span of any of their associated answers appear in at least one the top 5 relevant pages returned by each system.” ([Danqi Chen et al., 2017, p. 1876](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=7&annotation=IMJSD3F3))

“or by using cosine distance in the word embeddings space (by encoding questions and articles as bag-of-embeddings), both of which we find performed worse.” ([Danqi Chen et al., 2017, p. 1876](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=7&annotation=IIYS2P6L))

“Without the aligned question embedding feature (only word embedding and a few manual features), our system is still able to achieve F1 over 77%.” ([Danqi Chen et al., 2017, p. 1876](zotero://select/library/items/798T3EPX)) ([pdf](zotero://open-pdf/library/items/P9FMXX38?page=7&annotation=VH3B4735))

([Danqi Chen et al., 2017, p. 1877](zotero://select/library/items/798T3EPX)) Pass 2 impressions:  
Once a document (or small set of documents) has been retrieved, the multilayered RNN does more than simply retrieve a paragraph that likely contains the answer. It also identifies the answer within that paragraph.  
On an unrelated note, this paper very accurately predicts the need of such systems in the future. Sites like Wikipedia are designed for humans to read, not machines. Enabling machines to work with such data would be and is a great development in Natural Language Processing and Artificial Intelligence as a whole.

## References
1. [danqichenReadingWikipediaAnswer2017](zotero://select/items/@danqichenReadingWikipediaAnswer2017)
