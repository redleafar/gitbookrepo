# Queues

Queue: Abstract data type with the following operations:

* Enqueue(key): Adds key to collection
* Key Dequeue(): Removes and returns least recently-added key
* Boolean Empty(): are there any elements?

Is like waiting in a line. First come first serve situation.

Is called FIFO: First In, First Out

### Queue Implementation with Linked List

* Enqueue: use List.PushBack
* Dequeue: use List.TopFront and List.PopFront
* Empty: use List.Empty

### Queue Implementation with Array

In order to have $$O(1)$$we use two indexes one **read** index and a **write** index, keeping track of the array as a circular array. The **write** index says where the Enqueue happens and **read** where Dequeue happens. The queue is empty when the write and read are equal. When the **write** index arrives to the last element for the next Enqueue has to go to the first element.

When the **write** index arrives to the same position than **read** after an Enqueue  then is an error. If **read** arrives to the same than **write** after a dequeue then the queue is empty.

Each queue operation for Lists and arrays is $$O(1)$$
