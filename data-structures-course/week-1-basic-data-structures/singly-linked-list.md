# Singly-Linked List

Head pointer that points to another node, that then points to another one and so on unitl one that doesn't point any further

A node contains a:

* Key, and a
* Pointer (to the next node, the last one as nil/null as pointer)

**Operations**

Can have different names depending on the language, but normally they are:

* PushFront (Key) add to front
* Key TopFront() return front item
* PopFront() remove front item
* PushBack(Key) add to back (also known as Append)
* Key TopBack() return back item
* PopBack() remove back item
* Boolean Find(Key) is key in list?
* Erase(Key) remove key from list
* Boolean Empty() empty list?
* AddBefore(Node, Key) adds key before node

Note mine: PushFront push **before** the first element and PushBack **after** the last element. That is because it is "empujando" all the list forward or backwards.

**Times for some operations**

PushFront : O(1) (Create node, update next pointer, and updated head pointer to point the new one

PopFront: O(1) (Update head pointer and remove the node)

PushBack (no tail): O(n) (Start fron Head and move until the last element)

