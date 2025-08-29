# SIEVE is Simpler than LRU: an Efficient Turn-Key Eviction Algorithm for Web Caches
## Research Question

Is it possible to have a cache-replacement algorithm for typical (Zipfian distributed) web workloads which is simultaneously:

- Efficient (high hit rate/low miss rate)
- Simple (easy to implement)
- Scalable (in terms of concurrency)

..?

## Summary of SIEVE

Metadata:

- FIFO queue of cached items
  - Newly cached items inserted at head
  - Evicted items removed from middle (at the position of "Hand")
- "Recently accessed" bit per item
- "Hand" pointer
  - Moves from tail to head, eating accessed bits and stale items like Pac-Man