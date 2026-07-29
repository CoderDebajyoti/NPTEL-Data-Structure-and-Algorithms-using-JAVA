# NPTEL Data Structure and Algorithms using JAVA

## Week 1 Quiz

> Total Questions 10

## Question 1

**Which of the following statements about generic methods in Java are TRUE?**  
*Select all that apply.*

```
☐ a. A generic method can be defined inside a non-generic class.
☑ b. The type parameter must be declared before the return type in the method signature.
☐ c. Generic methods can only return the same type as their type parameter.
☑ d. A generic method can accept multiple type parameters.
```

### Selected Answer

- ☑ b
- ☑ d

## Question 2

**Which of the following is the correct syntax for declaring a generic method `display` that accepts a single argument of any type and returns nothing?**

```text
☐ a. public T void display(T item) { ... }

☐ b. public void display(T item) { ... }

☑ c. public <T> void display(T item) { ... }

☐ d. public void <T> display(T item) { ... }
```

### Selected Answer

- ☑ c

## Question 3

**Consider the following program.**

```java
public class Swap {
    public static <A, B> void printPair(A first, B second) {
        System.out.println(second + " " + first);
    }

    public static void main(String[] args) {
        printPair(10, "Hello");
    }
}
```

**What will be the output of the above Java program?**

```text
☐ a. 10 Hello

☑ b. Hello 10

☐ c. Compilation error due to mismatched types

☐ d. null null
```

### Selected Answer

- ☑ b

## Question 4

**A developer writes a generic utility method `public static <T> boolean areEqual(T a, T b)`. Which of the following calls will compile successfully?**  
*Select all that apply.*

```text
☐ a. areEqual(1, 2.0)

☐ b. areEqual(42)

☑ c. areEqual("hello", "world")

☑ d. areEqual(true, false)
```

### Selected Answer

- ☑ c
- ☑ d

## Question 5

**Consider the following program.**

```java
public class KeyValue<K, V> {
    private K key;
    private V value;

    public KeyValue(K k, V v) {
        key = k;
        value = v;
    }

    public K getKey() {
        return key;
    }

    public V getValue() {
        return value;
    }

    public static void main(String[] args) {
        KeyValue<String, Integer> kv = new KeyValue<>("Score", 95);
        System.out.println(kv.getKey() + ":" + kv.getValue());
    }
}
```

**What will be the output of the above Java program?**

```text
☑ a. Score:95

☐ b. Compilation error because generic classes cannot use + operator

☐ c. null:0

☐ d. Runtime error due to unboxing failure
```

### Selected Answer

- ☑ a

## Question 6

**Which of the following statements about type erasure in Java generics are TRUE?**  
*Select all that apply.*

```text
☑ a. After compilation, generic type information is removed and replaced with Object (or the bound type).

☐ b. Type erasure allows two overloaded methods that differ only in their generic type parameter.

☑ c. At runtime, a List<String> and a List<Integer> are represented by the same class.

☑ d. Type erasure is the reason generic arrays like new T[10] cannot be created directly.
```

### Selected Answer

- ☑ a
- ☑ c
- ☑ d

## Question 7

**Consider the following program.**

```java
public class Stats<T extends Number> {
    private T val;

    public Stats(T v) {
        val = v;
    }

    public double doubled() {
        return val.doubleValue() * 2;
    }

    public static void main(String[] args) {
        Stats<Integer> s = new Stats<>(7);
        System.out.println(s.doubled());
    }
}
```

**What will be the output of the above Java program?**

```text
☐ a. 7

☐ b. 14

☑ c. 14.0

☐ d. Compilation error because doubleValue() is not defined on T
```

### Selected Answer

- ☑ c

## Question 8

**A developer wants to write a single generic class `Container<T>` that enforces `T` must be a subtype of `Comparable<T>`. Which declaration is correct?**

```text
☐ a. class Container<T super Comparable<T>>

☐ b. class Container<T extends Comparable>

☑ c. class Container<T extends Comparable<T>>

☐ d. class Container<T implements Comparable<T>>
```

### Selected Answer

- ☑ c

## Question 9

**Which of the following are valid instantiations of class `Wrapper<T extends Number & Comparable<T>>`?**  
*Select all that apply.*

```text
☑ a. new Wrapper<Integer>()

☐ b. new Wrapper<String>()

☑ c. new Wrapper<Double>()

☐ d. new Wrapper<Object>()
```

### Selected Answer

- ☑ a
- ☑ c

## Question 10

**Consider the following program.**

```java
public class MaxFinder {
    public static <T extends Comparable<T>> T findMax(T a, T b) {
        return (a.compareTo(b) >= 0) ? a : b;
    }

    public static void main(String[] args) {
        System.out.println(findMax(3, 7));
        System.out.println(findMax("apple", "mango"));
    }
}
```

**What will be the output of the above Java program?**

```text
☐ a.
7
apple

☐ b.
3
mango

☑ c.
7
mango

☐ d. Compilation error because Comparable cannot be used as a bound
```

### Selected Answer

- ☑ c