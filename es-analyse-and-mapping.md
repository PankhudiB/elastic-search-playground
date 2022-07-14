### ES Analyze & Mapping

1. before text is stored - it is processed

```
Document -> Analyzer -> Storage 
                |
                |
                1.Character Filer
                2.Tokenizer
                3.Token filters 
```

1. Character Filer -> 
   1. eg. html_strip -> to get rid of html tags in the doc
   2. Can be 0 or more
2. Tokenizer -> 
   1. Split text into tokens 
   2. Stores character offset of each token in original string
   3. Only 1 tokenizer allowed
3. Token filters
   1. eg. lowercase -> modify all chars to lowercase
   2. Can be 0 or more

----------

> ANALYZE API :

POST /_analyze
{
   "text" : "a nice lemon juice",
   analyser: "standard"
}
--------

> Mapping

- defines structure of docs 
  - how they are indexed
  - and how they are stored
  - fields and their data types
- equivalent to table schema in relational DB
- 2 approaches 
  - explicit
    - we define it
  - implicit
    - ES does it for us
- both can be combined

Overview of Datatypes :

- object -> json 
- text
- integer
- boolean
- float
- double
- short
- date -> epoch
- ip
- etc..

explicit -> using "properties" key

- ES -> built on top of `Lucene` (which `does not support objects`)
that's why ES `transforms` the objects before storing to Lucene
-> to ensure we can index any valid json

-> the fields are flattened by dot notation -> heihrarchy is maintained

-> but what about arrays ?? they will fall under same key 

-> its `GOOD` for same cases -> if we run search query -> it will run through all

-> `BAD` -> search for products that have review left by person named 'John doe' with a rating of atleast 4

```
   reviews : [
      {rating: 5, author: 'some name'},
      {rating: 3.5, author: 'john doe'}
   ]


   reviews.rating : [5, 3.5]
   reviews.author : ['Some name' , 'John Doe']
```

our intention : AND --- result will be OR - due to how the values are stored internally 

To solve this : 

   `nested dataype`

   - ~ to obj
   - useful while querying array of obj
   - use nested query
   - stored as hidden doc -> which means they wont show up in search result
----------
   
>Mapping API

- PUT /index -> eg /reviews
{
    "mappings" : {
        "properties" : {
            "rating" : { "type" : "float" } ..         
        }
    }
}

> Retriving mapping

GET /reviews/_mapping/filed/

-----

`Keyword datatype`

- used for exact matching
- used for filtering,aggregating, sorting
- how does it work & why cant we use it for full text searches ?
- We can use `text` field for `full text searches` but we cant run aggregations on text field
  - so `keyword` for mapping for `aggregations` ..
- we can attach both to field -> usecase of `multi-field mapping` : 
  - Recipe : {
      description -> text
      ingredients [] --> text + keyword
  }
  - here :
    - `text` field type for ingredients will be useful when :
      - -> we are `searching for recipes that need an ingredient` -> eg garlic and the match of spelling might nod be perfect
    - `keyword` field type for ingredients will be useful when :
      - we want to `show ingredients -> recipe mapping`  
-------





