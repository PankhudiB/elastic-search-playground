### Bool queries
```
"query" : {
    "bool" : {
        "must" -> relevance , it similar to AND operator
        "must_not" -> relevance
        "filter" -> does not rely on relevance - pure bool
        "should" -> when coupled with must OR filter -> 
                    it does the boosting of relevance score
                    but does not become the criteria of search
                 
                 -> when used without must / filter 
                    -> then atleast 1 of the should array should satisfy
                    -> its like an OR operator   
    }
}
```
--------
##### To debug the boolean queries
- and what made the doc appear in result

- we can use /explain api + add a field called "_name" to each query clause
- each doc in the result will have a "matched_queries" field that ll tell why it appeared in result

--------

### how does match query work ?

match query are analysed 

post analysis -> they are usually a bunch of bool queries of term queries 