Project 1 - Analysis and Reporting

./alloca.out (list length = 10000):
0.01 real       0.01 user       0.00 sys        5216 memory (KB)
0.01 real       0.00 user       0.00 sys        5224 memory (KB)
0.01 real       0.00 user       0.00 sys        5224 memory (KB)
0.00 real       0.00 user       0.00 sys        5248 memory (KB)
0.01 real       0.01 user       0.00 sys        5212 memory (KB)
0.01 real       0.00 user       0.00 sys        5216 memory (KB)
0.01 real       0.00 user       0.00 sys        5216 memory (KB)
0.01 real       0.00 user       0.00 sys        5216 memory (KB)
0.01 real       0.01 user       0.00 sys        5224 memory (KB)
0.01 real       0.00 user       0.00 sys        5216 memory (KB)
 min: 0.000000  avg: 0.009000  max: 0.010000

./list.out (list length = 10000):
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4632 memory (KB)
0.02 real       0.02 user       0.00 sys        4080 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4616 memory (KB)
0.02 real       0.02 user       0.00 sys        4608 memory (KB)
0.02 real       0.02 user       0.00 sys        4608 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4648 memory (KB)
 min: 0.020000  avg: 0.020000  max: 0.020000

./malloc.out (list length = 10000):
0.01 real       0.00 user       0.00 sys        4064 memory (KB)
0.01 real       0.01 user       0.00 sys        4072 memory (KB)
0.01 real       0.00 user       0.00 sys        4052 memory (KB)
0.01 real       0.01 user       0.00 sys        4064 memory (KB)
0.01 real       0.01 user       0.00 sys        4064 memory (KB)
0.01 real       0.00 user       0.00 sys        4064 memory (KB)
0.01 real       0.01 user       0.00 sys        4072 memory (KB)
0.00 real       0.00 user       0.00 sys        4064 memory (KB)
0.01 real       0.00 user       0.00 sys        4056 memory (KB)
0.00 real       0.00 user       0.00 sys        4048 memory (KB)
 min: 0.000000  avg: 0.008000  max: 0.010000

./new.out (list length = 10000):
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.01 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4676 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4648 memory (KB)
0.02 real       0.02 user       0.00 sys        4648 memory (KB)
0.02 real       0.01 user       0.00 sys        4624 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
0.01 real       0.01 user       0.00 sys        4640 memory (KB)
0.02 real       0.02 user       0.00 sys        4640 memory (KB)
 min: 0.010000  avg: 0.019000  max: 0.020000


Which program is fastest? Is it always the fastest?
The fastest program was malloc.cpp averaging around 0.008000 seconds in the trial, but it is not necessarily always the fastest as seen in the times above.

Which program is slowest? Is it always the slowest?
The slowest program was list.cpp with an average time of 0.020000 seconds, but it is not necessarily always the slowest as seen in the times above.

Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?
Yes, as the size of data increases so does execution time. More bytes have to be processed in the hash() function leading to the cost of allocation to be less significant compared to the computational complexity.


Was there a trend in program execution time based on the length of the block chain?
Yes, as the number of nodes increases so does execution time.

Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap? Speculate on any similarities and differences in programs?
The number of heap breaks was relatively similar across the programs that use heap allocation such as malloc.cpp, new.cpp, and list.cpp, because they all 
request memory dynamically from the heap as the list grows. The alloca.cpp program showed fewer or different heap break behavior since it allocates memory 
on the stack instead of the heap. Increasing the stack size does not directly affect the heap because they are separate memory regions, but it allows 
alloca.cpp to handle larger recursion depths without crashing. The main similarity is that all programs allocate memory for nodes, while the key difference 
is whether that memory comes from the heap or the stack.

Considering either the malloc.cpp or alloca.cpp versions of the program, generate a diagram showing two Nodes. Include in the diagram the relationship 
of the head, tail, and Node next pointers. show the size (in bytes) and structure of a Node that allocated six bytes of data include the bytes pointer, 
and indicate using an arrow which byte in the allocated memory it points to.

head -> Node1 -> Node2 -> ... -> NodeN -> nullptr
        |         |                ^
        v         v                |
       data      data             tail

_________________________
|next ptr (8 bytes)     |
_________________________
|numBytes = 6 (4 bytes) |
|(4 bytes unused)       |
_________________________
|bytes ptr (8 bytes)    |
_________________________
allocated in memory         [byte1][byte2][byte3][byte4][byte5][byte6]
                               ^- bytes ptr






There's an overhead to allocating memory, initializing it, and eventually processing (in our case, hashing it). For each program, were any of these tasks the same? Which one(s) were different?
All programs initialize data, compute hash, and traverse the list. The differences lie with alloca.cpp using stack allocation, malloc using heap (C) allocation, new using heap (C++) allocation, and list using STL.

As the size of data in a Node increases, does the significance of allocating the node increase or decrease?
As data increases, the significance of allocating the node decreases. This is because when the node is small allocation overhead is primarily impacting runtime as opposed to when the node is large such that computation 
time overtakes the overhead of allocating the node.
