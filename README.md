## Pessimistic-locking (Thread safe queue implementation)

<hr>

Queues are everywhere. We use queues in most of the web applications for async processing. We can find queues in message-brokers, event-driven systems, thread pools etc.  

The naive queue implementation is not thread safe at all which means when multiple threads enqueue and dequque out of the same queue, it is possible that they might get incorrect results and runtime exceptions.

Concurrent queue makes implementation works in sync manner where one thread acquires a lock on the element it is accessing and releases the lock when it is done with the operation. 

No other thread can do any modification to this element so as to avoid inconsistency.

<hr>

### Advantages of Concurrent queues
1. Thread Safety - Every thread will perform an atomic operation on a single element at a time.
2. Scalability - Allows multiple threads to run and access a queue and ensuring to get the correct data.
3. Data integrity - A thread will always get the consistent data.

### Disadvantages of Concurrent queues
1. Sychronization overhead - Threads have to perform operations in sync. Even though multiple threads try to enqueue but only one thread is allowed to do so at a time. 
2. Wait/block time - Threads are blocked because of an mututal exclusive lock.