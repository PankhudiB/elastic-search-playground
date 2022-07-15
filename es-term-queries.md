### Term Queries

Basic ->
```
query : {
        "term" : {
            "field_name" : "value"
        }    
    }
```

Multiple ->
```
query : {
        "terms" : {
            "tag.keyword" : ["a", "b"],
        }    
    }
```

Range ->
```
query : {
        "range" : {
            "created" : {
                "gte": 
                "lte":  
            }
        }    
    }
```


Prefix ->
```
query : {
        "prefix" : {
            "tag.keyword" : "vege"
        }    
    }
```

Wildcard ->

```
wildcards -> are slow
* -> matches any no of char
? -> matches single char

query : {
        "wildcard" : {
            "tag.keyword" : "Vege*le"        ||  "tag.keyword" : "Vege?le"            
        }    
    }
```

Regex ->
```
  "query": {
    "regexp": {
      "tags.keyword": "Veg[a-zA-Z]+ble"
    }
  }
```

------

### ASSIGNMENT

```
1.
GET /product/default/_search
{
    "query": {
        "range" : {
            "sold" : {
                "lt" = 10
            }
        }
    }
}
```

```
2.
GET /product/default/_search
{
    "query": {
        "range" : {
            "sold" : {
                "lt" = 30,
                "gte" = 10 
            }
        }
    }
}
```

```
3.
GET /product/default/_search
{
    "query": {
        "term" : {
            "tags.keyword" : "Meat" 
        }
    }
}
```

```
4.
GET /product/default/_search
{
    "query": {
        "terms" : {
            "name" : ["Tomato", "Paste"],
        }
    }
}
```


```
5.
GET /product/default/_search
{
    "query": {
        "wildcard" : {
            "name" : "past?",
        }
    }
}
```

```
6.
GET /product/default/_search
{
    "query": {
        "regexp" : {
            "name" : "[0-9]+",
        }
    }
}
```

