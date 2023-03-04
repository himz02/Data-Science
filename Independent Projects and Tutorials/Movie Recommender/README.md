# Movie Recommender System using Content based filtering

Recommender systems can be based on three main algorithms:
- Content Based Filtering: This method is based on similarity of content such as genre, tags etc. It clusters new items based on the items viewer has interacted with before or shown interest in.
- Collaborative filtering: Clusters viewers/users together based on the similarities in their activities. If A likes 'alpha' and B likes 'alpha' and 'gamma' then 'gamma' may be recommended to A.
- Hybrid: This is a combination of the above two where both content based and collaborative filtering approaches are combined.

Here a content based method is used to define similarity.
Content is in the form of text. This text is cleaned of punctuation and reduced to its stem form.
Then the clean text is converted into vectors using a count vectorizer.
Cosine similarity is used to calculated the similarity among the vectors created.
And recommendations are eventually based on this similarity. 

Tools used: Python, Pandas, ast_literal, nltk, Stemming, CountVectorizer, Cosine Similarity
