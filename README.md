##To-do
1. Use 2D-vector (or vector with nested queue/priority queue)
    - Column: size/associativity
    - Row: blocks of 16 (store address in a set of 16, valid bit w/ each block), # blocks -> associativity
2. If miss
    - replace: LRU(Last recently used)
               FIFO (First in first out)
3. If hit
    - store the hit times so we can compute the hit rate later
4. Input will be a bunch of addresses
    - Need to read in line by line
    - Need to store them into cache at the same time (do we make several differnet vector or do it one by one?)
    - Need to do replacement and keep track of hit rate 

##Notes
- Block offset always is 4 bits (16 elements).
- Index is different based on associativity and cache size and needs to represent the number of sets we have.
    - e.g. Direct mapping + size of 1024 blocks = 1024 sets, 10 bits for index
- Tag is the rest of the 64 bit address. e.g. for above case, 50 bits for tag.

---
####[Deliverables](http://www.cs.ucr.edu/~windhs/lab7/lab7.html)

You should build a cache simulator that reads one address trace file and simulates multiple cache architectures and reports the miss rate (# misses / total accesses). Your simulator should support all the following attributes:

64 bit addresses
Block Size: 16 elements
Replacement Policies: LRU, FIFO
Cache Sizes: 1024, 2048, 4096, 8192, 16384 locations
Associativity: Direct Mapped, 2-way, 4-way, and 8-way
The output of your simulator should have to following format.

First output the LRU policy data, followed by the Fifo policy data
The x-axis should hold the cache sizes
The y-axis should hold the cache associativity
The output should go to 2 decimal places. (leading zeros for the whole numbers are optional)
You can build your simulator in C/C++, or Python. If you want to use a different language please check with the TA first. Your program should read from standard input, and write to standard output. To test your simulation you can use the memory trace file here. (If oyu are having problems with the zip, you can try the original file).The output for this file should look like:

LRU Replacement Policy
1024	2048	4096	8192	16384
1	55.01	42.07	29.30	20.74	13.91
2	51.58	36.44	23.70	13.98	08.49
4	48.85	33.97	20.04	11.33	06.37
8	47.44	32.20	18.63	10.02	05.72

FIFO Replacement Policy
1024	2048	4096	8192	16384
1	55.01	42.07	29.30	20.74	13.91
2	53.31	38.32	25.47	15.37	09.49
4	51.86	37.07	23.11	13.67	07.86
8	51.14	35.98	22.40	12.79	07.44

http://www.cs.ucr.edu/~windhs/lab7/lab7.html
