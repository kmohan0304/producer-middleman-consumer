# producer-middleman-consumer
Implementation of  multiple-threaded producer - middleman - consumer environment using Pthreads.   This project is an extension of the standard bounded-buffer synchronization problem.The producer, middleman, and  consumer are implemented  as threads in one process.It adds another shared buffer and a middleman and makes use of semaphore locks to prevent race conditions. 
Since busy waiting is inefficient, we will use semaphores to provide mutual exclusion and to control access to empty/full buffers.  Semaphores allow us to put a lock around the critical section
