#### ES improvements

1. the data-types of fields and are they necessary ? 
   1. keyword
   2. text 
2. And can we change this mapping post creation of index ?
3. time series data -> 
   1. we want to filter by specific time value
   2. but rather aggregate by time intervals
   3. another optimization with time series field -> disable norms -> if relevance scoring is not needed
4. Fix Mapping to save storage space :
   1. not just dynamic : false but dynamic : strict
5. Set doc_values to false if you don't need sorting, aggr & scripting
6. 