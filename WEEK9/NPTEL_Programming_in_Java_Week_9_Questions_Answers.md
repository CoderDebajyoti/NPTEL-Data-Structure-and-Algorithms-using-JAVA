# NPTEL Programming in Java --- Week 9 Questions & Answers

## Question 1

**Which of the following statements about Java Set implementations are
TRUE? Select all that apply.**

-   **a.** HashSet rejects duplicate elements based on `equals()` and
    `hashCode()`.
-   **b.** TreeSet maintains elements in ascending natural order.
-   **c.** LinkedHashSet sorts elements alphabetically on insertion.
-   **d.** All three --- HashSet, TreeSet, and LinkedHashSet --- reject
    duplicate elements.

### Answer

**a, b, d**

------------------------------------------------------------------------

## Question 2

**Consider the following program:**

``` java
import java.util.*;

public class Q2 {
    public static void main(String[] args) {
        Set<Integer> s = new TreeSet<>();
        s.add(5);
        s.add(2);
        s.add(8);
        s.add(2);
        s.add(1);

        System.out.println(s);
        System.out.println(s.size());
    }
}
```

**What will be the output?**

### Answer

**c.**

``` text
[1, 2, 5, 8]
4
```

**Reason:** `TreeSet` stores elements in natural ascending order and
does not allow duplicates.

------------------------------------------------------------------------

## Question 3

**Which of the following correctly describes the Java IO stream
hierarchy? Select all that apply.**

-   **a.** InputStream and OutputStream are abstract classes at the root
    of the byte stream hierarchy.
-   **b.** Reader and Writer are abstract classes at the root of the
    character stream hierarchy.
-   **c.** FileInputStream extends Reader because it reads from files.
-   **d.** BufferedReader wraps a Reader to provide efficient character
    reading.

### Answer

**a, b, d**

------------------------------------------------------------------------

## Question 4

**Which of the following statements about DataInputStream and
DataOutputStream are TRUE? Select all that apply.**

-   **a.** They allow reading and writing Java primitive types directly
    (e.g., `readInt()`, `writeDouble()`).
-   **b.** They extend Reader and Writer respectively.
-   **c.** They wrap an existing InputStream or OutputStream.
-   **d.** `readUTF()` and `writeUTF()` support string serialization in
    a portable format.

### Answer

**a, c, d**

------------------------------------------------------------------------

## Question 5

**Consider the following code. A developer wants to write text to a
ByteArrayOutputStream using a character-oriented Writer. They write:**

``` java
import java.io.*;

public class Q5 {
    public static void main(String[] args) throws IOException {
        OutputStream os = new ByteArrayOutputStream();
        Reader r = new InputStreamReader(os);
        r.read();
    }
}
```

**What is wrong with this code?**

-   **a.** Nothing; InputStreamReader can wrap any stream including
    OutputStream.
-   **b.** It fails to compile --- InputStreamReader requires an
    InputStream, not an OutputStream.
-   **c.** It compiles but throws an IOException at runtime because
    ByteArrayOutputStream is not readable.
-   **d.** It compiles but `r.read()` always returns -1 because the
    stream is empty.

### Answer

**b**

**Reason:** `InputStreamReader` converts bytes from an **InputStream**
into characters. A `ByteArrayOutputStream` is an **OutputStream**, so it
cannot be passed to `InputStreamReader`.

------------------------------------------------------------------------

## Question 6

**Consider the following program:**

``` java
import java.io.*;

public class Q6 {
    public static void main(String[] args) throws IOException {
        ByteArrayOutputStream bos = new ByteArrayOutputStream();

        bos.write(72);
        bos.write(105);

        System.out.println(bos.toString());
        System.out.println(bos.size());
    }
}
```

**What will be the output?**

### Answer

**a.**

``` text
Hi
2
```

**Reason:** ASCII/UTF-8 values `72` and `105` correspond to `H` and `i`.
Two bytes are stored.

------------------------------------------------------------------------

## Question 7

**Which of the following correctly describes the role of
OutputStreamWriter and InputStreamReader in Java IO?**

-   **a.** Both are byte streams that wrap character streams for binary
    output.
-   **b.** OutputStreamWriter converts characters to bytes;
    InputStreamReader converts bytes to characters.
-   **c.** InputStreamReader is used for writing; OutputStreamWriter is
    used for reading.
-   **d.** Both extend InputStream and are used for reading byte data.

### Answer

**b**

------------------------------------------------------------------------

## Question 8

**Consider the following program:**

``` java
import java.io.*;

public class Q8 {
    public static void main(String[] args) throws IOException {
        StringWriter sw = new StringWriter();

        sw.write("Java");
        sw.write("IO");

        System.out.println(sw.toString());
        System.out.println(sw.toString().length());
    }
}
```

**What will be the output?**

### Answer

**d.**

``` text
JavaIO
6
```

**Reason:** `"Java"` has 4 characters and `"IO"` has 2 characters. Total
= 6.

------------------------------------------------------------------------

## Question 9

**A developer uses FileWriter to write to a file as follows:**

``` java
FileWriter fw = new FileWriter("log.txt");
fw.write("first");
fw.close();

FileWriter fw2 = new FileWriter("log.txt");
fw2.write("second");
fw2.close();
```

**Which of the following correctly describes what `log.txt` contains
after both blocks execute?**

-   **a.** `firstsecond` --- both writes are appended sequentially.
-   **b.** `second` --- the second FileWriter overwrites the file by
    default.
-   **c.** `first` --- the second FileWriter fails silently and leaves
    the file unchanged.
-   **d.** The behaviour is undefined because two FileWriter instances
    cannot target the same file.

### Answer

**b**

**Reason:** `new FileWriter("log.txt")` opens the file for writing and,
by default, does not use append mode. The second writer replaces the
previous contents.

------------------------------------------------------------------------

## Question 10

**Which of the following statements about FileReader and FileWriter are
TRUE? Select all that apply.**

-   **a.** FileWriter creates the file if it does not already exist.
-   **b.** FileReader throws a FileNotFoundException if the specified
    file does not exist.
-   **c.** FileWriter opened with the append flag (`true`) preserves
    existing file content.
-   **d.** FileReader can be used to read binary image files without
    data loss.

### Answer

**a, b, c**

**Reason:** `FileReader` is designed for character data, so it is not
appropriate for reading binary image files without potential data loss.

------------------------------------------------------------------------

# Final Answer Key

  Question   Correct Answer
  ---------- ----------------
  **1**      **a, b, d**
  **2**      **c**
  **3**      **a, b, d**
  **4**      **a, c, d**
  **5**      **b**
  **6**      **a**
  **7**      **b**
  **8**      **d**
  **9**      **b**
  **10**     **a, b, c**

## Quick Answer Sheet

``` text
1. a, b, d
2. c
3. a, b, d
4. a, c, d
5. b
6. a
7. b
8. d
9. b
10. a, b, c
```
