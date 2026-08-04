# NPTEL Data Structure and Algorithms using JAVA

## Week 3 Quiz

## Question 1

**Which of the following statements correctly distinguishes between an Array and a Set based on the concepts discussed in the lecture?**

### Options

a. An array is always a set, but a set is not necessarily an array.  
b. A set is an array, but an array is not necessarily a set.  
c. Both arrays and sets must always contain unique items only.  
d. Arrays can only store heterogeneous data elements, whereas sets store homogeneous elements.

**✅ Correct Answer:** a

### Explanation

An **array** is an ordered collection of elements that may contain duplicate values, whereas a **set** is a collection of unique elements and does not require an array representation. Therefore, an array can be used to represent a collection of elements, but a set is not necessarily implemented as an array. The other options are incorrect because a set is not an array, arrays can contain duplicates, and there is no such restriction on storing heterogeneous or homogeneous elements based on arrays and sets.


## Question 2

**Which statement about the ArrayList class is correct?**

### Options

a. It has a fixed size and does not allow duplicate elements.  
b. It grows dynamically, permits duplicates, and maintains insertion order.  
c. It automatically stores all elements in sorted order.  
d. It does not support index-based access.

**✅ Correct Answer:** b

### Explanation

`ArrayList` in Java is a dynamic array implementation that automatically resizes as elements are added. It allows duplicate elements, preserves the order in which elements are inserted, and supports fast index-based access. It does not sort elements automatically.


## Question 3

**Consider the following Java snippet.**

```java
import java.util.Arrays;
import java.util.List;

public class Test {

    public static void main(String[] args) {

        String[] values = {"A", "B", "C"};

        List<String> list =
                Arrays.asList(values);

        list.set(1, "X");

        System.out.println(values[1]);
    }
}
```

**What will be the output printed to the console when this code is executed?**

### Options

a. B  
b. X  
c. null  
d. The program produces a compilation error

**✅ Correct Answer:** b

### Explanation

`Arrays.asList(values)` returns a fixed-size list backed by the original array. When `list.set(1, "X")` is executed, it updates the corresponding element in the underlying array. Therefore, `values[1]` becomes `"X"`, and the program prints:

```text
X
```


## Question 4

**Consider a two-dimensional array with the following elements:**

```text
2   4   6
8  10  12
```

**In row-major representation, which element is stored immediately after the element at row 0, column 2?**

### Options

a. The element at row 0, column 1  
b. The element at row 1, column 0  
c. The element at row 1, column 2  
d. The element at row 0, column 0

**✅ Correct Answer:** b

### Explanation

In **row-major order**, elements are stored row by row from left to right. The storage sequence for the given array is:

```text
2 → 4 → 6 → 8 → 10 → 12
```

The element at **row 0, column 2** is `6`. The next element stored is `8`, which is located at **row 1, column 0**.


## Question 5

**What is the purpose of the `Arrays.fill()` method?**

### Options

a. It removes all elements from an array.  
b. It fills an array or a specified range with a given value.  
c. It converts an array into an `ArrayList`.  
d. It searches an array using binary search.

**✅ Correct Answer:** b

### Explanation

The `Arrays.fill()` method in Java is used to assign the same value to every element of an array or to a specified range within the array. It is commonly used to initialize or reset array elements efficiently.


## Question 6

**Consider the following program.**

```java
public class Test {
    public static void main(String[] args) {
        int[] a = {10, 20, 30, 40, 0};
        int n = 4;
        int position = 2;

        for (int i = n; i > position; i--) {
            a[i] = a[i - 1];
        }

        a[position] = 25;

        for (int value : a) {
            System.out.print(value + " ");
        }
    }
}
```

**What will be the output of the above Java program?**

### Options

a. 10 20 25 30 40  
b. 10 25 20 30 40  
c. 10 20 30 25 40  
d. 25 10 20 30 40

**✅ Correct Answer:** a

### Explanation

The loop shifts all elements from index `2` onward one position to the right:

- Initial array: `10 20 30 40 0`
- After shifting: `10 20 30 30 40`
- After inserting `25` at index `2`: `10 20 25 30 40`

Therefore, the final output is:

```text
10 20 25 30 40
```


## Question 7

**Consider the following code.**

```java
import java.util.Arrays;

public class Test {

    public static void main(String[] args) {

        int[] values = {2, 1, 3, 4};

        Arrays.parallelPrefix(
            values,
            (x, y) -> x + y
        );

        System.out.println(
            Arrays.toString(values)
        );
    }
}
```

**What is the output?**

### Options

a. `[2, 1, 3, 4]`  
b. `[3, 4, 7, 4]`  
c. `[2, 3, 6, 10]`  
d. `[10, 8, 7, 4]`

**✅ Correct Answer:** c

### Explanation

`Arrays.parallelPrefix()` performs a cumulative (prefix) operation on the array using the provided binary operator. Here, the operator is addition (`x + y`), so each element becomes the sum of itself and all previous elements.

Computation:

- `2`
- `2 + 1 = 3`
- `3 + 3 = 6`
- `6 + 4 = 10`

The resulting array is:

```text
[2, 3, 6, 10]
```


## Question 8

**Consider the following two-dimensional array:**

```java
int[][] a = {

    {2, 4, 6},

    {8, 10, 12}

};
```

**If the array is represented in column-major order, which element occurs immediately after `a[0][0]`?**

### Options

a. `a[0][1]`  
b. `a[1][0]`  
c. `a[1][1]`  
d. `a[0][2]`

**✅ Correct Answer:** b

### Explanation

In **column-major order**, elements are stored column by column from top to bottom. The storage sequence for the given array is:

```text
2 → 8 → 4 → 10 → 6 → 12
```

The element at `a[0][0]` is `2`, and the next element in column-major order is `8`, which is located at `a[1][0]`.


## Question 9

**Consider the following program.**

```java
import java.util.Vector;

public class VectorDemo {

    public static void main(String[] args) {

        Vector<Integer> v = new Vector<Integer>(3, 2);

        v.addElement(10);
        v.addElement(20);
        v.addElement(30);
        v.addElement(40);

        System.out.println(v.size() + " " + v.capacity());
    }
}
```

**What will be the output printed by this code?**

### Options

a. 4 3  
b. 4 5  
c. 4 6  
d. 3 5

**✅ Correct Answer:** b

### Explanation

The `Vector` is created with an **initial capacity of 3** and a **capacity increment of 2**.

- After adding `10`, `20`, and `30`, the vector is full (size = 3, capacity = 3).
- Adding the fourth element (`40`) exceeds the current capacity, so the capacity increases by the specified increment (`3 + 2 = 5`).

Therefore:

- **Size = 4**
- **Capacity = 5**

The output is:

```text
4 5
```


## Question 10

**In the Java Collections Framework, the utility class `Arrays` provides static methods for array manipulation. Which method should be used to determine if two multi-dimensional arrays (which might contain nested arrays) are equal?**

### Options

a. `Arrays.equals(Object[] a, Object[] b)`  
b. `Arrays.deepEquals(Object[] a, Object[] b)`  
c. `Arrays.compareNested(Object[] a, Object[] b)`  
d. `Arrays.deepHashCode(Object[] a, Object[] b)`

**✅ Correct Answer:** b

### Explanation

`Arrays.deepEquals()` is used to compare multi-dimensional or nested arrays recursively. Unlike `Arrays.equals()`, which compares only the top-level elements, `deepEquals()` checks the contents of nested arrays to determine whether the arrays are truly equal.

Therefore, the correct answer is:

```java
Arrays.deepEquals(Object[] a, Object[] b)
```