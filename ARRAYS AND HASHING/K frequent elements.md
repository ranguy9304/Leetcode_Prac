TOPIC : [[ARRAYS AND HASHING]]
`2023-07-09

## TOPIC INFO 
Given an integer array `nums` and an integer `k`, return _the_ `k` _most frequent elements_. You may return the answer in **any order**.

here my first approach was using a dictionary to count and then sorting it this is correct but it depends on how u sort it for best effiency for example normal sorting will be o(nlogn) we can get it k logn using max heap and popping elements k times i forgot about this type of use of heaps cause i am a dumbass and time complexity for heapify is o(n) so thats cool and removal is nlogn thats why k logn 

but we can also do this in linear time using one more sorting algo which is linear time yes u guessed it right bucket sorting but using it directly is no use be have to use the frequency to sort instead of the number therefore there will be nums.length buckets and finding k most frequent elemnts we just have to start from back till k elements  this process is linear time.

![[Pasted image 20230709170903.png]]



### BRIEF



### CONCLUSION