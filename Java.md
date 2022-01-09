A hash table is well suited for this purpose because it supports fast lookup in near constant time. I say "near" because if a collision occurred, a lookup could degenerate to O(n)O(n) time. However, lookup in a hash table should be amortized O(1), O(1) time as long as the hash function was chosen carefully.


**Internal Implementations of Collections and their time complexities:**
