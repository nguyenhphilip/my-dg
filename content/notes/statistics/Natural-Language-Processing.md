---
title: Natural Language Processing
creation date: 2020-10-25 14:36
---

[fastai](notes/statistics/fastai.md)
- One debate in the field of NLP, and Machine Learning in general
    - using machine learning to predict outcomes but not necessarily understand the underlying phenomena; 
    - vs. a more theory-driven approach
    - CNN - one way of incorporating hypotheses, structures, and prior knowledge into your model when modeling underlying mechanisms
- Some Preprocessing
    - Lemmatization - fancier stemming
        - More computationally expensive, slower than stemming, but more accurate
        - Use lemmatization when you have less data, and you want to emphasize the importance of more significant words...
        - Might not want to remove stop words when you have lots of data and are using a large neural net to deal with more complexity
    - Stemming - getting roots of words (simpler) by chopping ends off
- Factorization analogous to matrix decomposition
    - think of multiplication tree, where the final factors of a number are prime
    - similar with matrix decomposition, where the factor matrices have nice properties depending on the type of decomp
        - Properties of matrices decomposed by SVD:
            - $$ A = USV $$
            - $U$ is orthonormal - columns are orthogonal and pairwise-normalized (dot product between any two columns = 0, between itself = 1)
            - $S$ is diagonal, and the values along the diagonal are essentially non-negative weights in descending order (principal components - the singular values!)
            - $V$ same properties as U, except transposed, so the rows are orthonormal to each other
    - SVD vs NMF (non-negative matrix factorizations)
        - NMF - non-negative values more interpretable
            - need to set # of topics you want
        - SVD - exact decomposition - can fully represent input matrices (i.e. can recompose original matrix)
            - more info and extra work
