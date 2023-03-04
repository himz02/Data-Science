# Natural Language Processing

This project was created by following the instructions and excercises from the Natural Language Processing tutorial by CodeBasics on Yotube. Thank to the creator for providing such a helpful resource.

1. Regular expressions
A lot of natural langauge processing problems require you to use regular expression or are at least in part a regex problem. So it is important to understand its basics and familiarize yourself with it.

2. Difference between libraries: spacy and nltk  
- spacy is object oriented  
doc is an object and sents is it property and we are accessing them through object oriented programming  
provides most efficient nlp algorithms for a given tasks    
- nltk is mainly a string processing library;  
offers so many algorithms for specific customizations  

3. Tokenization in spacy
It is not as simply as splitting strings at full stop or space but you need laguage specific rules.  
We use a blank pipeline here.

4. Pipeline
Pipelines can be modified to include functionality needed for the job.

5. Language processing pipeline in spacy
- tagger give you part of speech
- lemmatizer gives you base word
- ner gives you entities

6. Stemming and Lemmatization
- Stemming is basic and primary in the sense that it follows a set of rules in removing some prefix or suffix values to convert the word into its base form
- Spacy does not have support for stemming so nltk is used
- Lemmatization is a little more advanced because it requires understanding of the language.

7. Parts of speech: POS Tagging
- A trained model is able to get this information about parts of speech because of the different components in the pipeline.
- A blank pipeline will not be able to give this information about language intrinsics.
- tag_ gives even more detailed information such as the tense of the verb
- All this information is goint be very useful in the NLP piepiline

8. Named Entity Recognition
- ner in the nlp pipeline gives contect to words  
How to build your own ner?
- Manually add the ent for each text, then use lookup to access it
- Follow a set of rules to identify text such as "inc" refers to an organization or such
- CRF Conditional Random Fields BERT is used for ner in machine learning

## Vector Space Model
The process of representing text as vector is called Vector Space Model.  
Examples include:
- Label Encoding  
Build a vocabulary from the entire text and assign a number to each word and use that number as an identifer to the text. 
- One Hote Encoding  
All words are construed as features and the row is given value 1 when we encounter the word otherwise zero such as [0, 0, 0, .....1, 0, 0, 0, 0] suggests that the word in that column is what we are reading.  


Issues with the above two methods:  
Does not capture the meaning of the word  
Can take up huge memory of space depending on the vocabulary    
Out of Vocabulary problem     


- Bag of Words
It is based on the count vectorizer. Build a vocabulary out of the text and then each vector defines the number of occurrences of each word.  
It still takes up huge amount of space but is better than one hot encoding because in OHE each word is converted to a vector the length of the complete vocabulary  
But in Bag of Words a para (not each word) can be coverted to a vector which will be the length of the vocabulary.  
It is sparse representation.
Does not capture the meaning of the word.  
- TF-IDF
- Word Embeddings

9. Bag of Words: Apply on a spam/ham dataset using sklearn

10. Stop Words: Remove Stop words from a complete dataset
Removing stop words from the text that may not contribute to the model can help with sparse matrix.  
It can cause loss of pertinent information and should be used carefully with the problem statement in mind.
One should not remove Stop words:
- Chat bot, Q/A system
- Language translation
- Anywhere you can not afford loss of information, somtimes even sentiment analysis

11. Bag of n-grams: Apply preprocessing ang Bag of ngrams to a complete dataset
Bag of words does not capture the relationship between words as it does not take into account the order of words.   
Bag of n-grams takes collection of n words and counts their occurence instead of counting the occurence of single words.   
It can be used as a 2-gram such that it creates a vocabulary of 2 words each (pairs) and counts the occurence of pairs.  
A 3-gram measures the occurence of 3 words each, so on and so forth.  

Bag of words is a special case of Bag of n-grams where n = 1.  
Often 1-gram and bi-gram are combined to make more meaningful vectors.  
Cons:
- As n increases, dimensionality increases, sparsity increases
- Doesn't address out of vocabulary problem

12. Text Representation using TF-IDF
Cons:
- As vocabulary increases, sparsity increases
- Does not capture the relationship between words
- Also suffers from out of vocabulary problem

13. Word Embeddings
Tf-idf and Bag of words have limitations:    
- Similar words do not have similar vectors; do not capture the meaning of words  
- Sparse matric depending on the vocabulary  


But Word Embeddings work in a way that: 
- similar words have similar vectors  
- Dimensionality is low  


How does word embedding work?  
Think of this as solving a fake problem using neural networks and obtaining word vectors as a side-effect of solving the fake problem.     


Let's say for the corpus: "The king of the county has established his rule. The emperor is eccentric and suffers from severe ignorance." We are trying to predict the vector for "king" then we can use the context or the words around it as our training data and "king" as the target. When this neural network is run on this data, the weight vectors from the last layer are considered to be the word vector for king. Same context is applied for "emperor", since the target label for both will be similar the weight vector or eventually the word vector will be very close to the "king"'s word vector, hence capturing similarity.

Vector size will depend on the number of neurons in the last layer of the network. Usually the length of these vectors is 300/500.

Word Embedding also enable us to do word arithmetic:
King - women = Queen as the vectors capture their meaning.  

Word Embeddings can vary based on which dataset they are trained on.     
If trained on twitter data, it will capture tweets better. Example: glove   

14. Text classification using Spacy Word vectors

Tools used: Python, Pandas, spacy, nltk, Word2Vec, Text processing
