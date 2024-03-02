# Stacks

Abstract type with the folowing operations:

* Push(Key): adds key to collection
* Key Top(): returns most recently-added key
* Key Pop(): removes and returns most recently-added key
* Boolean Empty(): are there any elements?

Is as if you have a stack of books&#x20;

Example:

**Balanced Brackets**

<figure><img src="../../.gitbook/assets/imagen (9).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (10).png" alt=""><figcaption></figcaption></figure>

You can see it as if there is an openning symbol there has to be an equivalent closing symbol to be balanced

<figure><img src="../../.gitbook/assets/imagen (11).png" alt=""><figcaption></figcaption></figure>

For this algorithm you can see that first takes every opening symbol in the array and pushes it to the stack and then when it finds a closing symbol, pops the stack and compares the returned symbol from the pop with the current array symbol so with that it sees if there is a closing symbol match for the opening symbol. Note the stack.Empty(). That is because there can still be opening symbols in the stack without match which means that is not balanced.

Stacks can be implemented with Arrays and Linked Lists.&#x20;

With arrays we have all the stack operations

Disadvantages with arrays:

* We have maximum sizes&#x20;
* A potential problem is that we can have wasted space

In Linked Lists we also have all the stack operations and we don't have a max size.

Disadvantages with linked lists:

* Fixed amount of overhead because we need also memory for the pointers for each element pushed

**Time Complexity**

Every stack operation is O(1)

Stacks are also known as LIFO (Last Input First Output)
