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
alloca.out and malloc.out

Which program is slowest? Is it always the slowest?
new.out is the slowest but 

Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?


Was there a trend in program execution time based on the length of the block chain?


Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap? Speculate on any similarities and differences in programs?
Considering either the malloc.cpp or alloca.cpp versions of the program, generate a diagram showing two Nodes. Include in the diagram

    the relationship of the head, tail, and Node next pointers.
    show the size (in bytes) and structure of a Node that allocated six bytes of data
    include the bytes pointer, and indicate using an arrow which byte in the allocated memory it points to.



There's an overhead to allocating memory, initializing it, and eventually processing (in our case, hashing it). For each program, were any of these tasks the same? Which one(s) were different?


As the size of data in a Node increases, does the significance of allocating the node increase or decrease?
