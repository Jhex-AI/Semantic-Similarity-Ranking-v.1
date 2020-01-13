# Semantic Similarity Ranking

A simple implementation of ranking for search based systems using semantic similarity. 

### Simple Writeup

**Note: A more detailed writeup will be added soon**

1. Acquired the dataset through Slack.
2. Pre-processed the dataset
    1. Removed Stop-words
    2. Lemmatizated the corpus and saved for future reference
    3. Creation of Inverted-Index (demonstation purposes)
3. Converted corpus to vectors using Word2Vec
4. Tested the semantic similarity on random query words using the model,

    Most similar word examples to the query
    ```python
    modelW2V.wv.similarity('cancer', 'tumor') 
    #0.8035345
    ```
    ```python
    modelW2V.wv.similarity('cancer','ovarian')
    #0.860453
    ```
    Least similar word examples to the query
    ```python
    modelW2V.wv.similarity('cancer', 'cloud') 
    #0.8035345
    ```
5. Converted corpus to vectors using Doc2Vec
6. Found most similary documents given a query
    ```python
    new_sentence = "i love dogs".split(" ") 
    # *query = {i,love,dogs}*
    
    model.docvecs.most_similar(positive=[model.infer_vector(new_sentence)],topn=5)
    # *selecting the top n documents*
    
    #Result
    #[('5235', 0.7422172427177429),
    #('4870', 0.7328481674194336),
    #('95', 0.7185875773429871),
    #('5868', 0.7118589878082275),
    #('1954', 0.6987151503562927)]
    
    # *Format = {'DocID','Accuracy of the document with the query'}*
    ```

Cheers!
