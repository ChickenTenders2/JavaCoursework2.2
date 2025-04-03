I’ve been tasked to complete a queue data structure using a circular array with two methods,
enqueue and dequeue. The circular array is a fixed-size array that stores elements in a circular
manner. It behaves like a queue data structure, where elements are added to the rear (end) and
removed from the front; and when the end of the array is reached, the next element wraps
around to the beginning. A real life example would be a vehicle roundabout, where vehicles
come (enqueues) and go (dequeues) in a circular manner, and once it is full, new vehicles need
to wait for current front vehicles to leave before enqueuing.
Circular arrays are commonly known as the most memory-efficient way of implementing the
enqueue and dequeue methods. The enqueue method is responsible for adding an element to
the rear, while the dequeue method is responsible for removing an element from the front, and
the modulo operator will wrap the end to the front.
For the enqueue function, it first checks whether a queue is full by comparing the numElements
with the queue.length. If the queue is full, a newQueue is created which doubles the queue
capacity. It then copies the old queue to the new one in the same order. Whether the queue is
full or not, it will calculate the index at the end of the queue with (front + i) % queue.length. In
order to operate the circular array, the module operator (%) is used to wrap around any given
array index when it exceeds the array size. This ensures that the index stays within the bounds
of the circular array, unlike a dynamic array where the boundary isn’t considered. Finally, the
enqueue function adds a new element at the end of the queue, and increments numElements.
The dequeue function first checks if the queue is empty, if it is an IllegalStateException will be
thrown. Then, it stores the front element in removedElement, and shifts all remaining elements
to the front by one position. Any empty position in a queue will be labeled as ‘null’, and
numElements are decremented.
