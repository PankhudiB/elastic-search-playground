### ES Stemming & Stop words 

Doc might have text like : "Patrick loved bagels"

But user might search "loves" -> even thought its different tense. the doc should show up for the search

1. `Stemming` reduces word to their root form ->
   1. loved -> love
   2. drinking -> drink

2. `Stop word` :
   1. words not useful for relevance scoring
   2. on, at, to , a, the 
------   
`Q : `
If words are analysed during indexing. What happens when we search for them ?

`A :`
the original word is still in _source.
The search query is also sent through & analysed through same analyser as used during indexing
------

