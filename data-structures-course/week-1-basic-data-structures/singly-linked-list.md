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

PushBack (no tail pointer): O(n) (Start from Head and move until the last element)

PopBack (no tail pointer): O(n) (Start from Head and move until the last element)

PushBack (with tail pointer): O(1) (Go to last node and update pointer of the current tail to point to the new tail)

PopBack (with tail pointer): O(n) (In this case you have to remove the tail but you have to point the node before the old tail to the new node, so you have to traverse all the list for this)

**Code examples**

<figure><img src="../../.gitbook/assets/imagen (2).png" alt=""><figcaption><p>PushFront</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (3).png" alt=""><figcaption><p>PopFront</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (4).png" alt=""><figcaption><p>PushBack</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (6).png" alt=""><figcaption><p>PopBack</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (7).png" alt=""><figcaption><p>AddAfter</p></figcaption></figure>

**Time complexity summary**

<figure><img src="../../.gitbook/assets/imagen (8).png" alt=""><figcaption></figcaption></figure>
