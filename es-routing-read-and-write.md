### ES Routing 

1. How ES know where to store the doc ?
2. How are doc found once indexed ?

> Routing --> process of resolving a shard for a doc

> shard_num = hash(_routing) % no of shards

- _routing -> is the id of doc. -> Default
- we can use custom routing -> need to take care of good distribution

-------

### How does ES reads data (not search) ?

-> `GET request` --> `Routing` (to figure out shard for the given doc) --> A shard is chosen from `Replication Group` --> coordinating node collects response from that shard 

-> ES uses `ARS (Adaptive Replica Selection)`

### How does ES write data ?

-> routing happens ~ to above --> but write request always goes to `Primary shard` in the Replication Group

-> this validates the request - structure , values

-> Primary shard writes locally and returns

-> parallely sent to replicas 




