

```
"query" : { "term" : { "name" : "lobster"} } -> found
"query" : { "term" : { "name" : "Lobster"} } -> not found
"query" : { "match" : { "name" : "Lobster"} } -> found
```

WHY ???

term query -> do exact matching (they are not analysed) -> looked up at inverted index

full text queries are analysed

So,

term query for "lobster" ---> found in inverted index
term query for "Lobster" ---> NOT found in inverted index
full text query for "Lobster" ---> found -> bcoz it was analysed
