# Starve-Free-ReadersWriters
A starve free solution to the readers writers problem
In this pseudocode, the readers and writers enter a queue and wait for their turn. The queue operates on a First-Come-First-Served (FCFS) basis, ensuring that no reader or writer will starve. The mutex is used to synchronize access to shared resources, such as the count_readers variable and the is_writing flag.

The reader() function first enters the queue and waits until it is at the front of the queue and no writer is currently writing. Once the reader is at the front of the queue, it dequeues itself, increments the count_readers variable, and unlocks the mutex. Then, it can safely read data.

The writer() function operates similarly to the reader() function, except that it also checks if there are any readers currently reading. If there are readers, the writer will wait until all readers have finished before it can start writing. Once the writer is at the front of the queue and there are no other readers or writers, it dequeues itself, sets the is_writing flag to true, and unlocks the mutex. Then, it can safely write data. When the writer is finished, it sets the is_writing flag to false and checks if there are any more writers waiting in the queue. If there are, it sets the is_writing flag to true again and allows the next writer to start writing.

This repo was created as a submission for an assignment in the CSN-232 course taken in the springs of 2023.
