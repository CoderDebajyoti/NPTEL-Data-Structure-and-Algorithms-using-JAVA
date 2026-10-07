# NPTEL Programming with Java -- Week 10

## Topic: Java Networking and Searching/Sorting

### Question 1

**Which of the following statements about RandomAccessFile are TRUE?
Select all that apply.**

**Answer:** a, b, d

-   It supports both read and write operations on the same file.
-   It belongs to the `java.io` package.
-   The file pointer can be moved to any byte position using `seek()`.

**Explanation:** `RandomAccessFile` supports both reading and writing
and provides `seek()` for direct byte-position access. It does not
maintain a buffer like `BufferedReader`.

------------------------------------------------------------------------

### Question 2

**A developer opens a file using
`new RandomAccessFile("data.bin", "rw")` and calls `seek(8)` followed by
`writeInt(42)`. Which is correct?**

**Answer:** b

**Explanation:** `seek(8)` moves the file pointer to byte offset 8.
`writeInt(42)` writes an integer using 4 bytes, so bytes 8--11 are
written/overwritten.

------------------------------------------------------------------------

### Question 3

**Which correctly distinguishes sequential access from random access?**

**Answer:** c

**Explanation:** Sequential access reads data in order, while random
access can jump directly to any byte position in a file.

------------------------------------------------------------------------

### Question 4

**Which statements about linear search are TRUE? Select all that
apply.**

**Answer:** a, b, d

-   Linear search works on both sorted and unsorted arrays.
-   Linear search has `O(n)` worst-case time complexity.
-   An early-exit optimization is possible when the array is sorted.

**Explanation:** In the worst case, every element may need to be
checked. For a sorted array, the search can stop when the current
element becomes greater than the key.

------------------------------------------------------------------------

### Question 5

**Consider the given linear search method. Is the claim correct and what
does the program print?**

**Answer:** b

**Output:**

``` text
-1
1
```

**Explanation:** The loop starts from index `1`, so index `0` is never
checked. The value `7` at index `0` is therefore missed, returning `-1`.
The value `3` is at index `1`, so the second search returns `1`.

------------------------------------------------------------------------

### Question 6

**Which correctly describes the conditions and complexity of
interpolation search?**

**Answer:** a, d

**Explanation:** Interpolation search requires sorted data. When data is
approximately uniformly distributed, its average complexity can be
`O(log log n)`. In the worst case, it can degrade to `O(n)`.

------------------------------------------------------------------------

### Question 7

**What will be the output of the given binary search program?**

**Answer:** b

**Output:**

``` text
3
-1
```

**Explanation:** In the sorted array `{3, 7, 11, 15, 22, 31}`, the value
`15` is at index `3`. The value `10` does not exist, so the method
returns `-1`.

------------------------------------------------------------------------

### Question 8

**Which statements are TRUE about binary search? Select all that
apply.**

**Answer:** a, c, d

-   Binary search requires the input array to be sorted.
-   `int mid = low + (high - low) / 2` avoids integer overflow for large
    indices.
-   The worst-case time complexity of binary search is `O(log n)`.

------------------------------------------------------------------------

### Question 9

**What will be the output of the given Java program?**

**Answer:** b

**Output:**

``` text
3 5 1 8
```

**Explanation:** The program performs one pass through the array and
swaps adjacent elements when they are out of order. Starting with:

`5 3 8 1`

After the comparisons:

`3 5 1 8`

So the output is `3 5 1 8`.

------------------------------------------------------------------------

### Question 10

**Which statements correctly compare insertion sort and bubble sort?
Select all that apply.**

**Answer:** a, b, d

-   Both have `O(n²)` worst-case time complexity.
-   Insertion sort performs well on nearly sorted data.
-   Both are stable sorting algorithms.

**Explanation:** Neither algorithm is universally preferred for every
use case. Insertion sort is particularly efficient when the input is
already or nearly sorted.

------------------------------------------------------------------------

# Final Answer Key

  Question   Answer
  ---------- -------------
  1          **a, b, d**
  2          **b**
  3          **c**
  4          **a, b, d**
  5          **b**
  6          **a, d**
  7          **b**
  8          **a, c, d**
  9          **b**
  10         **a, b, d**

## Quick Revision

-   `RandomAccessFile` → read + write + `seek()`
-   `seek(8)` → moves pointer to byte 8
-   `writeInt()` → writes 4 bytes
-   Linear Search → `O(n)`
-   Binary Search → sorted array, `O(log n)`
-   Interpolation Search → sorted data; average `O(log log n)` for
    uniform data, worst `O(n)`
-   Insertion Sort → good for nearly sorted data
-   Bubble Sort → stable, worst-case `O(n²)`
-   Insertion Sort → stable, worst-case `O(n²)`
