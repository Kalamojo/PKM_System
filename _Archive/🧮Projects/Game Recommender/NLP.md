---
tags:
  - NLP
  - Python
completed: 1
parent: "[[Data Processing|Data Processing]]"
type: sub
---
# Natural Language Processing


## Run-down
1. Preprocess the summaries
	1. Lowercase all words
	2. Remove stopwords
	3. Reduce each word to their stem
2. Using for loops (and the zipfile searching program as a reference), create a new object attribute "bag-of-words" that is a combination of all relevant info
3. Use Count Vectorizer (or TFIDF ((Term Frequency Inverse Document Frequency)) Vectorizer) to store each game along with their word counts