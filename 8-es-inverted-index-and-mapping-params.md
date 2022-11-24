[#inverted-index , #doc_values , #norms]

### ES Inverted Index

For faster look-ups and search :
Diff data structures are used for this :

ES maintains Inverted Index for `text field`

It is mapping of

```
Terms            ------------------------->   Documents that contain those terms
(Tokens - that came out of analyzer) 
```

- they contain more info like - relevance score 

- if the doc has 2 text fields then --> 2 Inverted indices -> `1 per text field`

- Inverted index are maintained on disc

- Other datatype -> like numeric,geospatial --> stored in `BKD trees`

---------

`doc_values` :

-> another DS

-> uninverted inverted index

->  on-disk data structure, built at document index time

-> They store the same values as the _source but in a column-oriented fashion that is way more efficient for sorting and aggregations

-> disable doc_values -> if not aggre,sorting,scripting 

---------

`norms` :

- normalisation factors used for relevance scoring
- often we just dont want to filter results - we want to `rank` them 
- eg. google search engine -> 4th 5th pages 


useful for :
    - fields used for relevance scoring 
    - eg. name field for product 

can be disabled for fields:
    -  fields used for filtering and aggregation
    - eg. tags for a product -> used for filter -> 
    {
        "mappings" : {
            "properties" : {
                "norms" : false
            }
        }
    }

text -> inverted_index -> analysed -> relevance scoring
keyword -> exact matches -> not analysed
doc_values -> separate column for the field -> not allowed for text

