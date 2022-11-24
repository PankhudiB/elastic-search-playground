### ES Datatype & Mapping

> DataType

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
 
> Demo

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

GET /reviews/_mapping/

-----

> Keyword v/s Text Type

`Keyword` : 
- used for exact matching
- used for filtering,aggregating, sorting

`Text` : 
- We can use `text` field for `full text searches` but we cant run aggregations on text field

Both : 
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
> DEMO 

1. kubernetes-log --> message 
2. jaeger-span --> traceID 

----------




