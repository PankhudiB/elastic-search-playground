
### Relevance Score

OLD algo

1. TF - Term Frequency 
   1. how many times a term appear in the field for the doc
   2. more times the term occurs -> the more relevant the doc is
   

2. Inverse Document Frequency
   1. How often the term appear in the index (i.e across all docs)
   2. the more often the term appears -> lower the score and relevance
   3. eg . that this is to


3. Field length norm
   1. longer the field -> less likely the word in the field is relvant
   2. eg: title salad in 50 chars is more relevant than in 50000 chars description

Comparison with BM25 Algo

- Better at handling stop words
  - not necessarily you always want to remove the stop words 
  - and if you didnt -> then there are chances their relevance score may be boosted
  - Solution -> `Non-linear Term Frequency Saturation`
    - the idea is BM25 has upper limit for how much a term can be boosted based on how many times it occurs.
    - eg. boost for term that appears 1000 times wil be equal to term that appears 30 times.
  
- Improves field-length norms
  - PM25 considers each field separate -> takes avg of field length 