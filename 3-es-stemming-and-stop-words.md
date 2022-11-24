### ES Stemming & Stop words 

Doc might have text like : "the Patrick loved bagels"

But user might search "loves" -> even though its different tense.
the doc should show up for the search

1. `Stemming` reduces word to their root form ->
   1. loved -> love
   2. drinking -> drink

2. `Stop word` :
   1. words not useful for relevance scoring
   2. on, at, to , a, the 

-------------------
> DEMO

> ANALYZE API :

POST /_analyze
{
"text" : "a nice apple juice",
analyser: "standard"
}

1. standard
2. english
3. stop

------   
`Q : `
If words are analysed during indexing. What happens when we search for them ?

`A :`
