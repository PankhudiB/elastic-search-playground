####Sharding
Sharding enables us to scale the data volume. 
Adding more nodes to the cluster helps too, but only to a certain extent 
(unless there are no very large indices).

What is a shard ?
An index is divided into one or more shards,
where each shard stores a part of the index' data.
