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
