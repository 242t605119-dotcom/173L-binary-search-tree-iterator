# LeetCode 173 - Binary Search Tree Iterator

## Problem

Design an iterator over a **Binary Search Tree (BST)**.

The iterator should return the nodes in **inorder traversal** order.

The data structure must support:

* `next()` — Returns the next smallest number in the BST.
* `hasNext()` — Returns whether there is another node available.

### Example

For the BST:

```text
        7
       / \
      3   15
         /  \
        9    20
```

The inorder traversal is:

```text
3 → 7 → 9 → 15 → 20
```

So calling `next()` repeatedly returns:

```text
3
7
9
15
20
```

## Approach

I use a **stack** to simulate inorder traversal.

Inorder traversal follows:

```text
Left → Root → Right
```

First, all the left nodes are pushed onto the stack.

When `next()` is called:

1. Remove the top node from the stack.
2. If that node has a right child, push the right child's left path onto the stack.
3. Return the removed node's value.

The stack always keeps the next smallest node ready.

## Algorithm

1. Create an empty stack.
2. Push the root and all its left children.
3. For `next()`:

   * Pop a node.
   * Process its right subtree.
   * Return its value.
4. For `hasNext()`:

   * Check whether the stack is empty.

## Complexity

* **Initialization:** `O(h)`
* **`next()`:** `O(h)` worst case
* **`hasNext()`:** `O(1)`
* **Space:** `O(h)`

Here, `h` is the height of the BST.

## Key Concepts

* Binary Search Tree
* Inorder Traversal
* Stack
* Iterators
* Tree Traversal

## What I Learned

This problem helped me understand how recursion can be converted into an iterative approach using a stack.

Instead of storing the complete inorder traversal, the stack stores only the nodes needed for the next operation.

## LeetCode Details

* **Problem:** 173
* **Title:** Binary Search Tree Iterator
* **Language:** Python
* **Difficulty:** Medium

## Author

T.Nandhini
