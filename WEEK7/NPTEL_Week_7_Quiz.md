# NPTEL Week 7 Quiz

## Question 1

**Question:**\
A binary search tree becomes unbalanced after an insertion. At the first
unbalanced pivot P, the left subtree has height 4 and the right subtree
has height 2. The inserted node lies in the left subtree of P's left
child. Which operation correctly restores AVL balance?

**Options:** - a. Perform a single left rotation at P. - b. Perform a
single right rotation at P. - c. First rotate the left child left, then
rotate P right. - d. First rotate the right child right, then rotate P
left.

**Right Option:** **b. Perform a single right rotation at P.**

------------------------------------------------------------------------

## Question 2

**Question:**\
The array `90, 70, 80, 40, 60, 50, 30` represents a max heap in 1-based
level order. If 85 is inserted using the standard max-heap insertion
procedure, which array represents the heap after reheapification?

**Options:** - a. `90, 85, 80, 70, 60, 50, 30, 40` - b.
`90, 70, 85, 40, 60, 50, 30, 80` - c. `85, 90, 80, 70, 60, 50, 30, 40` -
d. `90, 80, 85, 70, 60, 50, 30, 40`

**Right Option:** **a. `90, 85, 80, 70, 60, 50, 30, 40`**

------------------------------------------------------------------------

## Question 3

**Question:**\
The array `96, 80, 90, 70, 50, 60, 85, 20, 40` is a max heap. The root
is deleted, the last element replaces it, and the heap is rebuilt by
repeatedly swapping with the larger child when necessary. What is the
final heap?

**Options:** - a. `90, 80, 85, 50, 70, 60, 40, 20` - b.
`90, 85, 80, 50, 70, 60, 40, 20` - c. `85, 80, 90, 50, 70, 60, 40, 20` -
d. `90, 80, 60, 50, 70, 40, 85, 20`

**Right Option:** **b. `90, 85, 80, 50, 70, 60, 40, 20`**

------------------------------------------------------------------------

## Question 4

**Question:**\
Six processes arrive in the order P1, P2, P3, P4, P5, P6 with priorities
4, 5, 3, 5, 4, 5 respectively. A larger priority number is processed
first, and processes with the same priority retain their arrival order.
Which processing order is correct?

**Options:** - a. `P1, P5, P2, P4, P6, P3` - b.
`P6, P4, P2, P5, P1, P3` - c. `P2, P4, P6, P5, P1, P3` -
d. `P2, P4, P6, P1, P5, P3`

**Right Option:** **d. `P2, P4, P6, P1, P5, P3`**

------------------------------------------------------------------------

## Question 5

**Question:**\
Heap H1 is a min heap containing 8 nodes, and heap H2 is a max heap
containing 5 nodes. To merge H2 into H1, repeatedly delete the root of
H2 and insert that value into H1 while maintaining H1's heap property.
Which statement must be true when the merge is complete?

**Options:** - a. The result contains 13 nodes and is a min heap. - b.
The result contains 13 nodes and is a max heap. - c. The result contains
8 nodes because deleting from H2 discards its nodes. - d. The final heap
type depends on the last value removed from H2.

**Right Option:** **a. The result contains 13 nodes and is a min heap.**

------------------------------------------------------------------------

## Question 6

**Question:**\
Consider the following Java program:

``` java
public class Main {
    static int[] heap = new int[10];
    static int size = 0;

    static int parent(int p) { return p / 2; }

    static void swap(int a, int b) {
        int t = heap[a];
        heap[a] = heap[b];
        heap[b] = t;
    }

    static void insert(int value) {
        heap[++size] = value;
        int current = size;

        while (heap[current] < heap[parent(current)]) {
            swap(current, parent(current));
            current = parent(current);
        }
    }

    public static void main(String[] args) {
        heap[0] = 1;
        insert(9);
        insert(4);
        insert(7);
        insert(2);

        for (int i = 1; i <= size; i++)
            System.out.print(heap[i] + " ");
    }
}
```

**Question:**\
What will be the output of the program?

**Options:** - a. `4 2 7 9` - b. `2 9 7 4` - c. `2 4 7 9` - d. `9 4 7 2`

**Right Option:** **c. `2 4 7 9`**

------------------------------------------------------------------------

## Question 7

**Question:**\
Consider the following Java program:

``` java
public class Main {
    static int[] heap = {0, 10, 4, 6, 20, 15, 12, 9};
    static int size = 7;

    static int leftChild(int p) { return 2 * p; }
    static int rightChild(int p) { return 2 * p + 1; }

    static boolean isLeaf(int p) {
        return p >= size / 2 && p <= size;
    }

    static void swap(int a, int b) {
        int t = heap[a];
        heap[a] = heap[b];
        heap[b] = t;
    }

    static void minHeapify(int p) {
        if (!isLeaf(p) &&
            (heap[p] > heap[leftChild(p)] ||
             heap[p] > heap[rightChild(p)])) {

            if (heap[leftChild(p)] < heap[rightChild(p)]) {
                swap(p, leftChild(p));
                minHeapify(leftChild(p));
            } else {
                swap(p, rightChild(p));
                minHeapify(rightChild(p));
            }
        }
    }

    public static void main(String[] args) {
        minHeapify(1);

        for (int i = 1; i <= size; i++)
            System.out.print(heap[i] + " ");
    }
}
```

**Question:**\
What will be the output of the program?

**Options:** - a. `4 10 6 20 15 12 9` - b. `6 4 10 20 15 12 9` -
c. `4 15 6 20 10 12 9` - d. `10 4 6 20 15 12 9`

**Right Option:** **a. `4 10 6 20 15 12 9`**

------------------------------------------------------------------------

## Question 8

**Question:**\
Consider the following Java program:

``` java
public class Main {
    static int[] heap = {0, 2, 5, 7, 9, 6, 8, 10};
    static int size = 7;
    static final int FRONT = 1;

    static int leftChild(int p) { return 2 * p; }
    static int rightChild(int p) { return 2 * p + 1; }

    static boolean isLeaf(int p) {
        return p >= size / 2 && p <= size;
    }

    static void swap(int a, int b) {
        int t = heap[a];
        heap[a] = heap[b];
        heap[b] = t;
    }

    static void minHeapify(int p) {
        if (!isLeaf(p) &&
            (heap[p] > heap[leftChild(p)] ||
             heap[p] > heap[rightChild(p)])) {

            if (heap[leftChild(p)] < heap[rightChild(p)]) {
                swap(p, leftChild(p));
                minHeapify(leftChild(p));
            } else {
                swap(p, rightChild(p));
                minHeapify(rightChild(p));
            }
        }
    }

    static int remove() {
        int popped = heap[FRONT];
        heap[FRONT] = heap[size--];
        minHeapify(FRONT);
        return popped;
    }

    public static void main(String[] args) {
        System.out.print(remove() + " | ");

        for (int i = 1; i <= size; i++)
            System.out.print(heap[i] + " ");
    }
}
```

**Question:**\
What will be the output of the program?

**Options:** - a. `2 | 5 6 7 9 10 8` - b. `10 | 2 5 7 9 6 8` -
c. `2 | 5 7 8 9 6 10` - d. `5 | 2 6 7 9 10 8`

**Right Option:** **a. `2 | 5 6 7 9 10 8`**

------------------------------------------------------------------------

## Question 9

**Question:**\
Consider the following Java program:

``` java
public class Main {
    static int[] heap = {0, 9, 4, 2, 1, 3, 6, 7};
    static int size = 7;

    static int leftChild(int p) { return 2 * p; }
    static int rightChild(int p) { return 2 * p + 1; }

    static boolean isLeaf(int p) {
        return p >= size / 2 && p <= size;
    }

    static void swap(int a, int b) {
        int t = heap[a];
        heap[a] = heap[b];
        heap[b] = t;
    }

    static void minHeapify(int p) {
        if (!isLeaf(p) &&
            (heap[p] > heap[leftChild(p)] ||
             heap[p] > heap[rightChild(p)])) {

            if (heap[leftChild(p)] < heap[rightChild(p)]) {
                swap(p, leftChild(p));
                minHeapify(leftChild(p));
            } else {
                swap(p, rightChild(p));
                minHeapify(rightChild(p));
            }
        }
    }

    static void minHeap() {
        for (int p = size / 2; p >= 1; p--)
            minHeapify(p);
    }

    public static void main(String[] args) {
        minHeap();

        for (int i = 1; i <= size; i++)
            System.out.print(heap[i] + " ");
    }
}
```

**Question:**\
What will be the output of the program?

**Options:** - a. `1 3 2 4 9 6 7` - b. `1 2 3 4 9 6 7` -
c. `2 1 4 9 3 6 7` - d. `9 4 2 1 3 6 7`

**Right Option:** **a. `1 3 2 4 9 6 7`**

------------------------------------------------------------------------

## Question 10

**Question:**\
A Huffman tree is being constructed for external-node weights 2, 3, 5,
7, 9. At each step, the two smallest weights are combined and their sum
is inserted back into the sorted list. What are the first three newly
created combined weights?

**Options:** - a. `5, 7, 14` - b. `5, 12, 19` - c. `8, 12, 21` -
d. `5, 10, 16`

**Right Option:** **d. `5, 10, 16`**

------------------------------------------------------------------------

# Answer Key

  Question   Correct Option   Answer
  ---------- ---------------- ----------------------------------
  1          **b**            Single right rotation at P
  2          **a**            `90, 85, 80, 70, 60, 50, 30, 40`
  3          **b**            `90, 85, 80, 50, 70, 60, 40, 20`
  4          **d**            `P2, P4, P6, P1, P5, P3`
  5          **a**            13 nodes and a min heap
  6          **c**            `2 4 7 9`
  7          **a**            `4 10 6 20 15 12 9`
  8          **a**            `2 | 5 6 7 9 10 8`
  9          **a**            `1 3 2 4 9 6 7`
  10         **d**            `5, 10, 16`
