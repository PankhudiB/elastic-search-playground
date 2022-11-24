### ES improvements

1. the data-types of fields and are they necessary ? 
   1. keyword
   2. text 
2. And can we change this mapping post creation of index ?
3. time series data -> 
   1. we dont want to filter by specific time value
   2. but rather aggregate by time intervals
   3. another optimization with time series field -> disable norms -> if relevance scoring is not needed
4. Fix Mapping to save storage space :
   1. not just dynamic : false but dynamic : strict
5. Set doc_values to false if you don't need sorting, aggr & scripting
6. Does while query through grafana - which context are we using ?
7. While doing the search Check if we need query context or filter context ?
   1. i.e whether do we really want to calculate relevance scores -> bcoz that takes time
8. Which Analyser are we using ?
9. Grafana dashboards -> _source filtering --> to reduce the amount of data we receive and n/w throttling
10. Need a Dashboard to show ES query time
11. There is a Profiler in Kibana -> use that to profile grafana queries
12. 


### ES - doubts

1. How does `search-as-you-type` work ?
