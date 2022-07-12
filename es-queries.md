## ES Queries 

>Basic info of cluster :

GET /_cluster/health

GET /_cat/nodes?v

GET /_cat/indices?v&expand_wildcards=all

--------------

>Creating document

products -> being the index here 

POST /products/_doc
{
    "name" : "blah"
}

-> returns the id & the no of shards it was able to put the doc succesfully

>insert doc with specific id

PUT /products/_doc/100
{
    "name" : "blah"
}

--------------

>retrieve the doc by id

GET /products/_doc/100

-> json has `found: true` field &  `_source` field -> that has the doc

---------

>Update works similar

 we can update existing field or add new field

> ES DOCUMENTS ARE IMMUTABLE !!!!!
    
--> we actually replaced the doc

--> UPDATE API -> retrieves original -> changes field value -> and existing doc is entirely `replaced`

------------

We can do scripting inside the query
and even update without knowing the current value of field

--------

we can upsert, delete , replace similarly




