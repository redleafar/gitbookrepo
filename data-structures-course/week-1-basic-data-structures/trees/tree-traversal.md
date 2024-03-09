# Tree Traversal

Often we want to visit the nodes of a tree in a particular order. For example print the nodes of the tree.

* Depth-first: We completely traverse one sub-tree before exploring a sibling sub-tree
* Breadh-first: We traverse all nodes at one level before progressing to the next level. (We visit all of our siblings instead of children).

They show recursive implementations for Depth-first printing the key (normally you want to do something else here):

**InOrderTraversal**

<figure><img src="../../../.gitbook/assets/imagen (12).png" alt=""><figcaption></figcaption></figure>

In reality this is only defined for binary trees.

**PreOrderTraversal**

<figure><img src="../../../.gitbook/assets/imagen (13).png" alt=""><figcaption></figcaption></figure>

This one is not defined only for binary trees but for every tree.

**PostOrderTraversal**

<figure><img src="../../../.gitbook/assets/imagen (14).png" alt=""><figcaption></figcaption></figure>
