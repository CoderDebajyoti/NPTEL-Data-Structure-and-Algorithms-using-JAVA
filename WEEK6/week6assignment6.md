# NPTEL Week 6 Quiz

## Question 1

### Question
Consider the following Java program using a PriorityQueue:

```java
Queue<Integer> q = new PriorityQueue<>();
q.offer(40);
q.offer(10);
q.offer(30);
q.offer(20);
System.out.println(q.poll());
System.out.println(q.poll());
```

What will be the output of the above Java program?

### Options
- A. 40, 30
- B. 10, 30
- C. 10, 20
- D. 40, 20

### Right Option
**C. 10, 20**

---

## Question 2

### Question
Which of the following are valid declarations when working with queues via the JCF? Select all that apply.

### Options
- A. `Queue<Integer> q = new ArrayDeque<>();`
- B. `Deque<Integer> q = new PriorityQueue<>();`
- C. `Queue<Integer> q = new PriorityQueue<>();`
- D. `Queue<Integer> q = new LinkedList<>();`

### Right Option
**A, C, D**

---

## Question 3

### Question
Which of the following statements about binary tree properties are TRUE? Select all that apply.

### Options
- A. A full binary tree with n internal nodes has exactly n + 1 leaf nodes.
- B. A complete binary tree with n nodes has height ⌊log₂ n⌋.
- C. A perfect binary tree with height h has exactly 2^(h+1) − 1 nodes.
- D. A skewed binary tree with n nodes has height n.

### Right Option
**A, B, C**

---

## Question 4

### Question
A binary tree is constructed by inserting the values 10, 5, 15, 3, 7 in that order into an initially empty BST. Which of the following correctly describes the resulting tree structure?

### Options
- A. 10 is the root; 5 and 15 are its children; 3 and 7 are children of 5.
- B. 10 is the root; 15 is its only child; 5, 3, 7 form a left-skewed subtree.
- C. The tree is perfectly balanced with height 1.
- D. 3 is the leftmost node and 15 is the rightmost node, but 7 is the root.

### Right Option
**A. 10 is the root; 5 and 15 are its children; 3 and 7 are children of 5.**

---

## Question 5

### Question
Which of the following statements about BST search complexity are TRUE? Select all that apply.

### Options
- A. In a balanced BST, search is O(log n) in the worst case.
- B. In a skewed BST, search degrades to O(n) in the worst case.
- C. BST search is always O(log n) regardless of tree shape.
- D. Inserting values in sorted order into a BST produces a tree with O(n) worst-case search.

### Right Option
**A, B, D**

---

## Question 6

### Question
Consider a method claimed to compute the height of a binary tree, where height is defined as the number of nodes on the longest root-to-leaf path:

```java
static int height(Node node) {
    if (node == null) return 0;
    return 1 + height(node.left) + height(node.right);
}
```

The tree has root 1, children 2 and 3, and node 4 as the left child of node 2. The program prints 4. What is wrong with the height method?

### Options
- A. Nothing is wrong; 4 is the correct height of this tree.
- B. The method computes the node count, not the height; it sums both subtrees instead of taking the maximum.
- C. The base case should return -1 instead of 0.
- D. The recursion is missing a null check on node.left and node.right before recursing.

### Right Option
**B. The method computes the node count, not the height; it sums both subtrees instead of taking the maximum.**

---

## Question 7

### Question
Which of the following traversal sequences is consistent with a valid pre-order traversal of a BST containing {10, 5, 15, 3, 7}?

### Options
- A. [3, 5, 7, 10, 15]
- B. [10, 5, 3, 7, 15]
- C. [10, 15, 5, 7, 3]
- D. [3, 7, 5, 15, 10]

### Right Option
**B. [10, 5, 3, 7, 15]**

---

## Question 8

### Question
Consider the following Java program:

```java
Node root = null;
for (int v : new int[]{15, 10, 20, 8, 12})
    root = insert(root, v);
inOrder(root);
```

The `insert` method inserts smaller values into the left subtree and all other values into the right subtree, while `inOrder` performs left-root-right traversal.

What will be the output of the above Java program?

### Options
- A. 15 10 8 12 20
- B. 8 10 12 15 20
- C. 8 12 10 20 15
- D. 10 8 12 20 15

### Right Option
**B. 8 10 12 15 20**

---

## Question 9

### Question
Which of the following operations on a BST require traversing from root to a leaf in the worst case? Select all that apply.

### Options
- A. Searching for a value that does not exist in the tree
- B. Inserting a new value into the tree
- C. Finding the minimum value in the tree
- D. Finding the height of the tree

### Right Option
**A, B, C, D**

---

## Question 10

### Question
Consider the following BST search method:

```java
static boolean search(Node node, int val) {
    if (node == null) return false;
    if (val < node.val) return search(node.left, val);
    return search(node.right, val);
}
```

Is the claim that this method correctly searches for any value in the BST correct? What is the actual behaviour when searching for 10 in a BST containing {20, 10, 30}?

### Options
- A. The claim is correct; the method returns true for 10.
- B. The claim is incorrect; the method always returns false for any value less than the root.
- C. The claim is incorrect; the equality case is missing — when val == node.val the method recurses right indefinitely until null, returning false.
- D. The claim is incorrect; a StackOverflowError is thrown because the recursion has no valid base case.

### Right Option
**C. The claim is incorrect; the equality case is missing — when val == node.val the method recurses right until null, returning false.**

---

## Answer Summary

| Question | Right Option |
|---|---|
| 1 | C |
| 2 | A, C, D |
| 3 | A, B, C |
| 4 | A |
| 5 | A, B, D |
| 6 | B |
| 7 | B |
| 8 | B |
| 9 | A, B, C, D |
| 10 | C |
