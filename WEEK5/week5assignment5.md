# Week 5 Assignment — Stack and Queue

## Question 1

**Which of the following statements about stack data structures are TRUE? Select all that apply.**

### Options

- **a.** A stack follows LIFO (Last In, First Out) ordering.
- **b.** Both push and pop operate on the same end of the stack.
- **c.** A stack can be implemented using either an array or a linked list.
- **d.** `peek` removes the top element and returns it.

### Right Option(s)

**a, b, c**

---

## Question 2

**A stack is implemented using a singly linked list where the head of the list represents the top of the stack. Which of the following correctly describes the push operation?**

### Options

- **a.** A new node is added at the tail; the head pointer is unchanged.
- **b.** A new node is created, its next pointer is set to the current head, and the head is updated to the new node.
- **c.** A new node is created, the current head's next is set to the new node, and the head is unchanged.
- **d.** The existing head node's data is overwritten with the new value.

### Right Option

**b**

---

## Question 3

**Consider the following program.**

```java
import java.util.Stack;

public class Q3 {
    public static void main(String[] args) {
        Stack<Integer> s = new Stack<>();
        s.push(5);
        s.push(10);
        s.push(15);
        s.pop();
        s.push(20);
        System.out.println(s.peek());
        System.out.println(s.size());
    }
}
```

**What will be the output of the above Java program?**

### Options

- **a.**
  ```
  15
  3
  ```
- **b.**
  ```
  20
  4
  ```
- **c.**
  ```
  20
  3
  ```
- **d.**
  ```
  10
  3
  ```

### Right Option

**c**

---

## Question 4

**Which of the following correctly describes the difference between `Stack` (from `java.util`) and using a `Deque` (e.g., `ArrayDeque`) as a stack in Java?**

### Options

- **a.** Stack is faster because it is not synchronized.
- **b.** Deque used as a stack is generally preferred because Stack extends Vector and inherits unnecessary synchronized overhead.
- **c.** Stack and ArrayDeque are interchangeable with no practical difference.
- **d.** ArrayDeque does not support LIFO operations.

### Right Option

**b**

---

## Question 5

**Consider the following stack implementation. A developer claims that after calling `pop()` twice on a stack containing `[10, 20, 30]` (top = 30), they will receive 30 and then 20.**

```java
public class Q5 {
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
        }
    }

    static Node top = null;

    static void push(int data) {
        Node node = new Node(data);
        node.next = top;
        top = node;
    }

    static int pop() {
        int val = top.data;
        return val;
    }
}
```

**Is the claim correct? What is the actual behaviour?**

### Options

- **a.** The claim is correct; both calls return the expected distinct values.
- **b.** The claim is incorrect; the first `pop()` returns 30 but the second also returns 30 because `top` is never updated.
- **c.** The claim is incorrect; a `NullPointerException` is thrown on the second `pop()`.
- **d.** The claim is incorrect; the code fails to compile because `pop()` is missing a return statement.

### Right Option

**b**

---

## Question 6

**Which of the following are valid applications of a queue data structure? Select all that apply.**

### Options

- **a.** Breadth-first search traversal of a graph
- **b.** Evaluating postfix expressions
- **c.** Print spooler managing documents sent to a printer
- **d.** CPU scheduling using round-robin

### Right Option(s)

**a, c, d**

---

## Question 7

**Consider the following program.**

```java
import java.util.Queue;
import java.util.ArrayDeque;

public class Q7 {
    public static void main(String[] args) {
        Queue<String> q = new ArrayDeque<>();
        q.offer("A");
        q.offer("B");
        q.offer("C");
        q.poll();
        q.offer("D");
        System.out.println(q.peek());
        System.out.println(q.size());
    }
}
```

**What will be the output of the above Java program?**

### Options

- **a.**
  ```
  A
  3
  ```
- **b.**
  ```
  D
  3
  ```
- **c.**
  ```
  B
  4
  ```
- **d.**
  ```
  B
  3
  ```

### Right Option

**d**

---

## Question 8

**A priority queue contains tasks with the following priorities (higher number = higher priority):**

`T1 (priority 4), T2 (priority 7), T3 (priority 2), T4 (priority 7), T5 (priority 5)`

**Tasks are dequeued in priority order. T2 and T4 share the highest priority. Which of the following statements are TRUE about the dequeue order? Select all that apply.**

### Options

- **a.** T2 and T4 will always be dequeued before T1, T3, and T5.
- **b.** The relative order of T2 and T4 is deterministic in Java's `PriorityQueue`.
- **c.** T3 will always be the last task dequeued.
- **d.** T1 will be dequeued before T5.

### Right Option(s)

**a, c**

---

## Question 9

**Consider the following program.**

```java
import java.util.Deque;
import java.util.ArrayDeque;

public class Q9 {
    public static void main(String[] args) {
        Deque<Integer> dq = new ArrayDeque<>();
        dq.addFirst(1);
        dq.addFirst(2);
        dq.addFirst(3);
        dq.removeFirst();
        dq.addLast(0);
        System.out.println(dq);
    }
}
```

**What will be the output of the above Java program?**

### Options

- **a.** `[3, 2, 1, 0]`
- **b.** `[1, 2, 3, 0]`
- **c.** `[2, 1, 0]`
- **d.** `[0, 1, 2]`

### Right Option

**c**

---

## Question 10

**Consider the following method intended to dequeue from a queue and then re-enqueue a sentinel value. A developer claims it compiles and runs correctly.**

```java
import java.util.Queue;
import java.util.ArrayDeque;

public class Q10 {
    static Queue<Integer> q = new ArrayDeque<>();

    static int dequeue() {
        return q.poll();
        q.offer(0);
    }

    public static void main(String[] args) {
        q.offer(1);
        System.out.println(dequeue());
    }
}
```

**Is the developer's claim correct? What actually happens?**

### Options

- **a.** The claim is correct; it prints 1 and re-enqueues 0.
- **b.** The claim is incorrect; `q.poll()` on an empty queue causes a `NullPointerException` at runtime.
- **c.** The claim is incorrect; the code fails to compile because `q.offer(0)` is unreachable.
- **d.** The claim is incorrect; `return q.poll()` returns null since the queue was never populated.

### Right Option

**c**
