# Arrays

&#x20;**Array**

Contiguous area of memory consisting of equal-size elements indexed by contiguos integers. Initial index can be 0 or 1 depending on the language.\


Key point of arrays:

* Constant-time access to read and write any particular element in an array. This means we just do arithmetic to figure out the address of a particular element of an array:\
  \
  address = array\_addr + elem\_size \* (i-first\_index)

**Multi-Dimensional Arrays**

* For the address you have to count all the number of elements before the position
* That would be:\
  \
  address = elem\_size \* \[(row - 1) \* (max\_colum) + (column - first\_index)]&#x20;



<figure><img src="../../.gitbook/assets/imagen (5).png" alt=""><figcaption><p>Example of address calculation for Muiltidimensional arrays</p></figcaption></figure>

There is a supossition here is that the way this is layed out is from row to row, that is **Row-major**&#x20;

**Column-major** is when is layed out from column to column

**Times for common operations**

<figure><img src="../../.gitbook/assets/imagen (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

If you add or remove in the End, you already know the final position and is just 1 operation so that's why is O(1). However for the Beginning or the Middle you have to move other elements to make space, so that's why is O(n) (linear time).

For Read and Write, remember you have constant time acces O(1) which is an advantage.





