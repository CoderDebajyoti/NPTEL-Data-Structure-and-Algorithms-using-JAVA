# NPTEL Data Structure and Algorithms using JAVA

## Week 2 Quiz

## Question 1

**Which of the following correctly describes the relationship between the Collection and Map interfaces in the Java Collections Framework?**

- a. Map extends Collection because maps are a type of collection.
- b. Collection and Map are independent root interfaces in the JCF hierarchy.
- c. Both Collection and Map extend the Iterable interface directly.
- d. Map is a sub-interface of Set since keys in a map form a set.

**Answer:** b
```

## Question 2

**Which of the following statements about the Java Collections Framework are TRUE? Select all that apply.**

- a. ArrayList implements both List and Queue.
- b. LinkedList implements both List and Deque.
- c. PriorityQueue does not guarantee FIFO ordering.
- d. HashSet maintains insertion order.

**Answer:** b, c
```

## Question 3

**Consider the following program.**

```java
import java.util.*;

public class Q3 {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>(Arrays.asList("banana", "apple", "cherry"));
        Collections.sort(list);
        System.out.println(list.get(0));
    }
}
```

**What will be the output of the above Java program?**

- a. banana
- b. cherry
- c. apple
- d. Compilation error because Arrays.asList returns a fixed-size list

**Answer:** c

## Question 4

**Which of the following correctly describes the role of the `Collections` utility class in the JCF?**

- a. Collections is the root interface that all JCF classes implement.
- b. Collections is a class containing static utility methods that operate on Collection objects.
- c. Collections and Collection are two names for the same interface.
- d. Collections is an abstract class that must be subclassed to use its methods.

**Answer:** b

## Question 5

**Which of the following correctly describes the difference between `HashSet` and `TreeSet`?**

- a. HashSet maintains natural ordering; TreeSet does not.
- b. TreeSet allows null elements; HashSet does not.
- c. HashSet offers O(1) average-case operations; TreeSet offers O(log n).
- d. Both HashSet and TreeSet preserve insertion order.

**Answer:** c

## Question 6

**Consider the following program.**

```java
import java.util.*;

public class Q6 {
    public static void main(String[] args) {
        TreeMap<String, Integer> map = new TreeMap<>();
        map.put("banana", 2);
        map.put("apple", 5);
        map.put("cherry", 1);

        System.out.println(map.firstKey());
        System.out.println(map.lastKey());
    }
}
```

**What will be the output of the above Java program?**

- a.
  ```
  banana
  cherry
  ```
- b.
  ```
  apple
  cherry
  ```
- c.
  ```
  cherry
  apple
  ```
- d.
  ```
  apple
  banana
  ```

**Answer:** b

## Question 7

**Consider the following code. A developer claims it will throw a RuntimeException when the second `put` is called because the key `"a"` already exists. Is the claim correct, and what actually happens?**

```java
import java.util.*;

public class Q7 {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();

        map.put("a", 1);
        map.put("b", 2);
        map.put("a", 3);

        System.out.println(map.get("a"));
        System.out.println(map.size());
    }
}
```

- a. The claim is correct; a DuplicateKeyException is thrown.
- b. The claim is incorrect; the second `put("a", 3)` is silently ignored and the map retains value `1` for key `"a"`.
- c. The claim is incorrect; `put` overwrites the existing value and the map prints `3` then `2`.
- d. The claim is incorrect; both values are stored under key `"a"` and `get("a")` returns a list.

**Answer:** c

## Question 8

**Which of the following are characteristics of the `SortedMap` interface in Java? Select all that apply.**

- a. Keys are maintained in ascending order by default.
- b. It provides `firstKey()` and `lastKey()` methods.
- c. It allows unsorted insertion and sorts only on retrieval.
- d. TreeMap is the primary implementation of `SortedMap`.

**Answer:** a, b, d

## Question 9

**Consider the following program.**

```java
import java.util.*;

public class Q9 {
    public static void main(String[] args) {
        LinkedHashSet<String> set = new LinkedHashSet<>();

        set.add("dog");
        set.add("cat");
        set.add("dog");
        set.add("bird");

        System.out.println(set);
    }
}
```

**What will be the output of the above Java program?**

- a. `[dog, cat, bird, dog]`
- b. `[bird, cat, dog]`
- c. `[cat, dog, bird]`
- d. `[dog, cat, bird]`

**Answer:** d

## Question 10

**Which of the following statements about Java legacy classes are TRUE? Select all that apply.**

- a. Vector is thread-safe because its methods are synchronized.
- b. Hashtable allows one null key and multiple null values.
- c. Stack extends Vector and inherits its synchronized methods.
- d. Enumeration has been superseded by the Iterator interface in modern Java.

**Answer:** a, c, d