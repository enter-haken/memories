```
id: 3c5556ed-0027-4b73-bde7-54ee61d5ece3
title: Distributed systems
links:
  - 1c4ddc26-3b6c-11ea-8a1f-d3bd2d7b8f9d
```

# Distributed Systems

## offline

* big data analysis clusters
* movie scene rendering farms

## soft real-time

* search index builders

## hard real-time

* request / reply
* web servers
* credit card transactions
* telephony

## problems

* function calls are split into multiple steps
* every step can have failures
* testing is hard

## unknown unknowns

> One way we’ve found to approach distributed engineering is to distrust everything.

## distributed bugs

> If a failure is going to happen eventually, common wisdom is that it’s better if it happens sooner rather than later.

### epidemic

> 1. Distributed bugs necessarily involve use of the network.
> 2. Therefore, distributed bugs are more likely to spread to other machines (or groups of machines), because, by definition, they already involve the only thing that links machines together.

> Distributed problems get worse at higher levels of the system, due to recursion.
> Distributed bugs often show up long after they are deployed to a system.
> Many of the above problems derive from the laws of physics of networking, which can’t be changed


# Further reading

* [Challenges with distributed systems][1]

[1]: https://aws.amazon.com/builders-library/challenges-with-distributed-systems
