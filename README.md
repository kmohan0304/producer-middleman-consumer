# producer-middleman-consumer
Implementation of  multiple-threaded producer - middleman - consumer environment using Pthreads.   This project is an extension of the standard bounded-buffer synchronization problem.The producer, middleman, and  consumer are implemented as threads in one process.It adds another shared buffer and a middleman and makes use of semaphore locks to prevent race conditions. 
Since busy waiting is inefficient, we will use semaphores to provide mutual exclusion and to control access to empty/full buffers.  Semaphores allow us to put a lock around the critical section
Here I have used the shared variables:
1 shared buffer, which can hold N items
A semaphore mutex initialized to the value 1  (mutex is a binary semaphore providing mutual exclusion)
A semaphore full initialized to the value 0
A semaphore empty initialized to the value N  (full and empty are counting semaphores)

The problem of producer consumer is extended by adding another shared buffer and a middleman.  The producer will write items into the producer buffer.The middleman will take items from the producer buffer and place them in the consumer buffer.The consumer will read items out of the consumer buffer.So, the producer and the middleman share the producer buffer, and the middleman and the consumer share the consumer buffer. 

Inorder to make sharing of data structures easy as threads share their data address space,the producer, middleman, and  consumer are implemented as threads in one process.Synchronization mechanisms from the Pthreads library including mutex locks and semaphore locks are used.Each buffer holds 5 items.
Both the producer and consumer thread sleeps for a random time, then either produce or consume 1 item, and repeat.The middleman will sleep for some random time, then move one item from the producer buffer to the consumer buffer and repeat.
rand() returns a pseudo-random integer value between 0 and RAND-MAX.I have used rand() to generate the sleep time and again to generate the product value.Producer, middleman, and consumer threads sleep for either 1, 2, or 3 seconds, where the sleep time is uniformly distributed.rand() is also used to randomly insert items between 1-50 into the producer buffer.
The code is executed with one producer,one middleman,one consumer and three producer,three middleman,three consumer. 



