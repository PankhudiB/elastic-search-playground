### Full Text Queries

Match query -> doesnt matter what order the words are found - and if there are words in between those words

Basic OR query -> will match any of the words
```
query : {
        "match" : {
            "title" : "Recipes with pasta or spaghetti"
        }    
    }
```


AND -> will try to find docs that have all of the words
```
query : {
        "match" : {
            "title" : {
                "query" : "Recipes with pasta or spaghetti",
                "operator" : AND 
            }
        }    
    }
```

Match phrase -> order specific occurrence and no words allowed in between
```
query : {
        "match_phrase" : {
            "title" : {
                "query" : "",
            }
        }    
    }
```

searching same text across Multiple field
```
query : {
        "multi_match" : {
            "query" : pasta,
            "fields" : ["title" , "description"]
        }    
    }
```

------
