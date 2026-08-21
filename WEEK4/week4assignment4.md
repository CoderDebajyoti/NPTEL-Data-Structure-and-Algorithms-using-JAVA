# NPTEL Programming in Java --- Week 4 Quiz

## Question 1

**Question:**\
What happens to a node in a Java Linked List when it is removed from the
list structure such that no active references point to it?

**Options:**

a)  It causes a memory leak unless explicitly deallocated using the
    `delete` keyword.\
b)  It remains in memory indefinitely until the JVM is restarted.\
c)  It is automatically reclaimed by the Java Garbage Collector during
    its normal cleanup cycles.\
d)  It throws a `RuntimeMemoryException` if not cleared manually.

**Right Option:**\
**c)** It is automatically reclaimed by the Java Garbage Collector
during its normal cleanup cycles.

------------------------------------------------------------------------

## Question 2

**Question:**\
Which of the following statements correctly differentiates between a
Singly Linked List and a Circular Singly Linked List?

**Options:**

a)  A Circular Singly Linked List allows O(1) random access to any node,
    whereas a Singly Linked List does not.\
b)  In a Circular Singly Linked List, the next pointer of the last
    (tail) node points back to the first (head) node instead of being
    null.\
c)  A Singly Linked List can store heterogeneous elements, whereas a
    Circular Singly Linked List only stores integers.\
d)  A Circular Singly Linked List requires two reference pointers per
    node (next and prev), whereas a Singly Linked List requires only
    one.

**Right Option:**\
**b)** In a Circular Singly Linked List, the next pointer of the last
(tail) node points back to the first (head) node instead of being null.

------------------------------------------------------------------------

## Question 3

**Question:**\
Consider the following Java snippet that manipulates a singly linked
list node:

``` java
public class LinkedListDemo {
    static class Node {
        int data;
        Node next;

        Node(int d) {
            data = d;
            next = null;
        }
    }

    public static void main(String[] args) {
        Node head = new Node(10);
        head.next = new Node(20);
        head.next.next = new Node(30);

        Node temp = head.next;
        head.next = temp.next;

        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }
}
```

What will be the output printed to the console when this code is
executed?

**Options:**

a)  10 20\
b)  20 30\
c)  10 30\
d)  NullPointerException

**Right Option:**\
**c)** 10 30

------------------------------------------------------------------------

## Question 4

**Question:**\
What is the worst-case time complexity for inserting a new node at the
end (tail) of a standard Singly Linked List when only the head reference
is available (no tail pointer is maintained)?

**Options:**

a)  O(1)\
b)  O(log n)\
c)  O(n)\
d)  O(n²)

**Right Option:**\
**c)** O(n)

------------------------------------------------------------------------

## Question 5

**Question:**\
Assume a Singly Linked List maintains both a head and a tail reference
pointer. What are the time complexities for insertion at the end and
deletion from the end, respectively?

**Options:**

a)  O(1) for insertion at end; O(1) for deletion from end\
b)  O(n) for insertion at end; O(1) for deletion from end\
c)  O(1) for insertion at end; O(n) for deletion from end\
d)  O(n) for insertion at end; O(n) for deletion from end

**Right Option:**\
**c)** O(1) for insertion at end; O(n) for deletion from end

------------------------------------------------------------------------

## Question 6

**Question:**\
Consider the following Java method designed to insert a new node at a
specific 0-based index position within a Singly Linked List:

``` java
public void insertAtPosition(int index, int data) {
    Node newNode = new Node(data);

    if (index == 0) {
        newNode.next = head;
        head = newNode;
        return;
    }

    Node curr = head;
    for (int i = 0; i < index - 1; i++) {
        if (curr == null) {
            System.out.println("Position out of bounds");
            return;
        }
        curr = curr.next;
    }

    newNode.next = curr.next;
    curr.next = newNode;
}
```

If a linked list currently contains the elements 10 → 20 → 30 → 40
(indices 0 to 3) and the method `insertAtPosition(2, 25)` is called,
what will be the new sequential order of elements in the list?

**Options:**

a)  10 → 25 → 20 → 30 → 40\
b)  10 → 20 → 25 → 30 → 40\
c)  10 → 20 → 30 → 25 → 40\
d)  25 → 10 → 20 → 30 → 40

**Right Option:**\
**b)** 10 → 20 → 25 → 30 → 40

------------------------------------------------------------------------

## Question 7

**Question:**\
Consider the following Java method that prints a Singly Linked List
while reversing the ordering of elements using recursion:

``` java
public void printReversed(Node head) {
    if (head == null) {
        return;
    }

    printReversed(head.next);

    System.out.print(head.data + " ");
}
```

If this method is invoked on a linked list containing 5 → 10 → 15 → 20,
what is the exact output and what is the auxiliary space complexity
incurred by the program?

**Options:**

a)  Output: 5 10 15 20 \| Auxiliary Space: O(1)\
b)  Output: 20 15 10 5 \| Auxiliary Space: O(1)\
c)  Output: 20 15 10 5 \| Auxiliary Space: O(n)\
d)  Output: 5 10 15 20 \| Auxiliary Space: O(n)

**Right Option:**\
**c)** Output: 20 15 10 5 \| Auxiliary Space: O(n)

------------------------------------------------------------------------

## Question 8

**Question:**\
In a Doubly Linked List, every node contains two reference pointers
alongside the data element. Which of the following operations can be
performed in O(1) time on a Doubly Linked List but requires O(n) time on
a standard Singly Linked List? (Assume you are given a direct reference
to the node that needs to be operated on, and it is not the tail node.)

**Options:**

a)  Inserting a new node at the head of the list.\
b)  Deleting a specific node when given only a reference to that node.\
c)  Searching for a specific integer value within the list.\
d)  Finding the middle node of the list.

**Right Option:**\
**b)** Deleting a specific node when given only a reference to that
node.

------------------------------------------------------------------------

## Question 9

**Question:**\
Consider the following Java method designed to perform deletion from any
position (0-based index) in a Singly Linked List:

``` java
public void deleteAtPosition(int index) {
    if (head == null) return;

    if (index == 0) {
        head = head.next;
        return;
    }

    Node prev = head;
    for (int i = 0; prev != null && i < index - 1; i++) {
        prev = prev.next;
    }

    if (prev == null || prev.next == null) return;

    // Line X
}
```

Which of the following code statements must be inserted at Line X to
correctly unlink and remove the target node from the list?

**Options:**

a)  `prev = prev.next;`\
b)  `prev.next = prev.next.next;`\
c)  `prev.next = null;`\
d)  `prev.next.next = prev;`

**Right Option:**\
**b)** \`prev.next = prev.next.next;

------------------------------------------------------------------------

## Question 10

**Question:**\
When reversing the ordering of elements in a Singly Linked List
iteratively using three reference pointers (prev, curr, and nextTemp),
what is the primary role of the nextTemp pointer during each step of the
iteration?

**Options:**

a)  It stores the reversed sub-list created so far.\
b)  It prevents memory leaks by marking unlinked nodes for the Garbage
    Collector.\
c)  It temporarily preserves the reference to the remainder of the
    original list before curr.next is overwritten to point backward.\
d)  It points to the tail node so that reverse traversal can begin from
    the end of the list.

**Right Option:**\
**c)** It temporarily preserves the reference to the remainder of the
original list before `curr.next` is overwritten to point backward.
