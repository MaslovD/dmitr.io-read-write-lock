# How it works...  
While the writer has acquired the write lock, none of the reader tasks can read the data.  

You can see some messages of the reader tasks after the Write Lock Acquired message, but they are instructions that were executed before and not shown yet in the console. Once the writer task has released the lock, reader tasks gain access to the prices information again and show the new prices.

As mentioned previously, the ReentrantReadWriteLock class has two locks: one for read operations and one for write operations.
The lock used in read operations is obtained with the readLock() method declared in the ReadWriteLock interface.  
This lock is an object that implements the Lock interface, so we can use the lock(), unlock(), and tryLock() methods.
The lock used in write operations is obtained with the writeLock() method declared in the ReadWriteLock interface. 
This lock is also an object that implements the Lock interface, so we can use the lock(), unlock(), and tryLock() methods. 
It is the responsibility of the programmer to ensure correct use of these locks, using them for the same purposes for which they were designed.
When you get the read lock of a Lock interface, you can't modify the value of the variable.
Otherwise, you probably will have data errors related to inconsistency.