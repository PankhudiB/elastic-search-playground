### ES Analyze

1. before text is stored - it is processed

```
Document -> Analyzer -> Storage 
                |
                |
                1.Character Filter
                2.Tokenizer
                3.Token filters 
```

1. Character Filter -> 
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

