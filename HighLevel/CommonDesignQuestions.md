# Notes on Rate Limiter
A rate limiter limits the amount of requests a client can send. This is commonly used to avoid DDOS
attacks. A threshold is defined on the max amount of requests (like 2 accounts/day) so that the server
is not overwhelmed with requests it cannot handle and to prevent misuse of services.

A Rate limiter can be implemented on the client side or the server side. Client side
implementations are not reliable in the sense that malicious actors can change the
implementation. It can also be done by an intermediate layer with the help of a microservice.
A commonly used rate limiting algorithm is called Token Bucket. The basic idea
is that there are a certain number of tokens that are filled in the bucket. And has each 
request comes it takes a token,if there are no tokens in the bucket then the request is dropped.
There are other algorithms but on a high level you need to keep count
of the number of requests based on the user id, IP or other parameters. We need memory to keep
track of the count. Using data bases are slow due to the disk read speed, so you need somthing
like a in-memory cache (Redis for example).

# Notes on Consistent Hashing
Consistent hashing is used to distribute data/requests evenly among databases/servers. Hashes are defined with a number of servers in mind
and when one of them fail or are removed, the hash may not produce consistent results.

Consistent hashing is a special kind of hashing such that when a
hash table is re-sized and consistent hashing is used, only k/n keys need to be remapped on
average, where k is the number of keys, and n is the number of slots. In contrast, in most
traditional hash tables, a change in the number of array slots causes nearly all keys to be
remapped.

# Design a key-value store
Key-value stores are non relational databases where the key is unique and the values associated with the key is
accessed through the key. A single server key-value store is easy to design, we could put them in a hash table. Two optimizations
can be done: data compression and storing only frequently used keys in memory and rest on disk.
A distributed key-store is also possible but you need to keep in mind the CAP theorem when designing one.
C : Consistency A : Availability P : Partition Tolerance
It is impossible for any distributed system to provide all three. One of it has to be sacrified according to the CAP theorem. 
