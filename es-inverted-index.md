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

- Other datatype -> like numeric,geospatial --> stored in `BKD trees`




