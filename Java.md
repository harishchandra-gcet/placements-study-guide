© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# JAVA Study Guide

# SECTION 1 — Java Basics & Problem-Solving Templates

### Java syntax essentials

* Primitive types: `byte(8b)`, `short(16b)`, `int(32b)`, `long(64b)`, `float(32b)`, `double(64b)`, `char(16b)`, `boolean`.
* Default values: numeric → `0`, boolean → `false`, object → `null`.
* Type conversion: widening allowed implicitly (e.g., `int -> long`), narrowing must cast (e.g., `long -> int`).

  ```java
  int a = (int) 10L; // explicit cast
  ```

### I/O (quick)

* Console input with `Scanner` (common in exams)

  ```java
  Scanner sc = new Scanner(System.in);
  int n = sc.nextInt();
  String s = sc.next();
  ```
* Fast input (competitive) — `BufferedReader` + `StringTokenizer`.

### Problem patterns & templates

* **Loop template**

  ```java
  for (int i = 0; i < n; i++) { ... }
  while (cond) { ... }
  ```
* **Function template**

  ```java
  static int func(int[] a) { /* logic */ return 0; }
  ```
* **Common macros (not real macros, just patterns)**:

  * Use `l + (r - l) / 2` in binary search to avoid overflow.
  * Use `StringBuilder` for repeated string concat inside loops (`O(n)` vs `O(n^2)`).

### Typical problem skeletons

* **Reverse digits**

  ```java
  int rev(int x) {
    int r = 0;
    while (x != 0) {
      r = r * 10 + x % 10;
      x /= 10;
    }
    return r;
  }
  ```
* **Check prime (simple)** — O(sqrt(n))

  ```java
  boolean isPrime(int n) {
    if (n <= 1) return false;
    for (int i = 2; i * i <= n; i++) if (n % i == 0) return false;
    return true;
  }
  ```

### Gotchas

* `==` compares references for objects; `.equals()` compares value (unless overridden).
* `switch` on `String` supported since Java 7.
* `Integer` caching: `Integer a = 127; Integer b = 127; a==b -> true` (cache -128..127).

---

# SECTION 2 — Control Flow Statements (Outputs & Tricky Cases)

### Conditionals

* `if`, `if-else`, `if-else-if`. `switch` supports `int`, `short`, `char`, `String`, `enum`.
* `switch` fall-through: missing `break` causes execution to continue.

### Loops & jumps

* `break` exits loop; `continue` skips to next iteration.
* `return` exits method immediately.
* `for-each` for arrays/collections:

  ```java
  for (int x : arr) { ... }
  ```

### Output prediction traps

* Uninitialized local variables cause compile error.
* `for(int i=0; i<10; i++) System.out.println(i);` prints 0..9.
* `do { } while(false);` executes once.

### Quick examples

* **Switch fall-through**

  ```java
  int x = 1;
  switch(x) {
    case 1: System.out.print("A");
    case 2: System.out.print("B"); break;
    default: System.out.print("C");
  }
  // Output: AB
  ```

---

# SECTION 3 — Searching & Sorting (Templates + Complexities)

### Searching

* **Linear Search** — O(n)

  ```java
  int linear(int[] a, int key) {
    for (int i=0; i<a.length; i++) if (a[i]==key) return i;
    return -1;
  }
  ```
* **Binary Search** (array must be sorted) — O(log n)

  ```java
  int binary(int[] a, int key) {
    int l = 0, r = a.length - 1;
    while (l <= r) {
      int m = l + (r - l) / 2;
      if (a[m] == key) return m;
      else if (a[m] < key) l = m + 1;
      else r = m - 1;
    }
    return -1;
  }
  ```

☠ MCQ trap: binary search requires sorted array; complexity O(log n) best/worst/average (worst O(log n) for successful/unsuccessful).

### Sorting

* **Bubble Sort** — O(n²) worst, stable, in-place.
* **Selection Sort** — O(n²), unstable maybe, in-place.
* **Insertion Sort** — O(n²) worst, O(n) best (nearly sorted), stable.
* **Merge Sort** — O(n log n), stable, not in-place (extra memory).
* **Quick Sort** — O(n log n) average, O(n²) worst (bad pivot), in-place.

#### Minimal code: Merge & Quick (templates)

* **Merge (divide & conquer)** — key idea: merge sorted halves.
* **Quick** — pick pivot, partition, recurse (use randomized pivot to reduce worst-case).

### Complexity cheat table

| Algorithm | Best       | Average    | Worst      | Stable | Extra Space            |
| --------- | ---------- | ---------- | ---------- | ------ | ---------------------- |
| Bubble    | O(n)       | O(n²)      | O(n²)      | Yes    | O(1)                   |
| Insertion | O(n)       | O(n²)      | O(n²)      | Yes    | O(1)                   |
| Selection | O(n²)      | O(n²)      | O(n²)      | No     | O(1)                   |
| Merge     | O(n log n) | O(n log n) | O(n log n) | Yes    | O(n)                   |
| Quick     | O(n log n) | O(n log n) | O(n²)      | No     | O(log n) recursion avg |

☠ Gotcha: `Arrays.sort()` for primitives uses Dual-Pivot Quicksort (as of Oracle JDK) — average O(n log n).

---

# SECTION 4 — String Handling (Deep + Gotchas)

### String basics

* `String` is immutable; concatenation via `+` creates new objects.
* `StringBuilder` / `StringBuffer` are mutable. `StringBuffer` is synchronized.

### Common methods

* `length()`, `charAt(i)`, `substring(begin, end)`, `indexOf(str)`, `lastIndexOf`, `equals()`, `equalsIgnoreCase()`, `compareTo()`, `trim()`, `split(regex)`.

  ```java
  String s = "hello";
  char c = s.charAt(1); // 'e'
  String sub = s.substring(1,4); // "ell"
  ```

### Frequent operations & patterns

* **Reverse string**

  ```java
  String reverse(String s) {
    return new StringBuilder(s).reverse().toString();
  }
  ```
* **Check palindrome**

  ```java
  boolean pal(String s) {
    return s.equals(new StringBuilder(s).reverse().toString());
  }
  ```
* **Count frequency**

  ```java
  int[] freq = new int[256];
  for (char c : s.toCharArray()) freq[c]++;
  ```

### Immutability & SCP

* Literals go to SCP; `new String("x")` creates new object on heap.

  ```java
  String a = "hi";
  String b = "hi";
  a == b // true
  String c = new String("hi");
  a == c // false
  ```

### Gotchas & MCQ traps

* `s1 == s2` checks reference equality; `.equals()` checks content (unless not overridden).
* `String` methods that return new string — original unchanged.
* `substring` behavior changed in Java 7+: no memory leak (no shared char[]).

---

# SECTION 5 — Arrays & Collections

### Arrays

* Syntax: `int[] a = new int[n]; int[][] mat = new int[r][c];`
* Common operations: traverse, sort (`Arrays.sort(a)`), copy (`Arrays.copyOf`), fill (`Arrays.fill`).
* Multidimensional arrays are arrays of arrays.

### Collections overview (interface based)

* `List` — `ArrayList` (backed by array, random access O(1)), `LinkedList` (doubly-linked, O(1) insertion at ends).
* `Set` — `HashSet` (no order, O(1) average), `TreeSet` (sorted, O(log n)).
* `Map` — `HashMap` (key->value), `TreeMap` (sorted keys).
* `Queue` — `LinkedList` or `PriorityQueue`.

### Key differences

* **Array vs ArrayList**: array fixed-length; `ArrayList` dynamic resizing, boxing for primitives (use `int[]` for primitives).
* **HashMap vs TreeMap**: HashMap O(1) average, TreeMap O(log n); TreeMap sorted.

### Iteration

* `Iterator` supports `remove()` safely.

  ```java
  Iterator<Integer> it = list.iterator();
  while (it.hasNext()) {
    if (it.next() == something) it.remove();
  }
  ```
* For-each loop cannot remove element.

### Autoboxing issues

* Converting `int` ↔ `Integer` automatically. Beware of `null` `Integer` causing NPE when unboxed.

### Minimal codes

* **ArrayList usage**

  ```java
  List<Integer> list = new ArrayList<>();
  list.add(5);
  int val = list.get(0);
  ```

---

# SECTION 6 — Object-Oriented Programming (Core + Examples)

### Core concepts

* **Class & Object**: blueprint & instance.
* **Encapsulation**: `private` fields + public getters/setters.
* **Inheritance**: `extends` keyword; single inheritance for classes.
* **Polymorphism**:

  * Compile-time: method overloading (same name, different params).
  * Runtime: method overriding (same signature in subclass).
* **Abstraction**: `abstract class` vs `interface`.

  * Java 8+ interfaces can have `default` and `static` methods.
* **Composition** is preferred over inheritance in many designs.

### Constructors

* Default constructor provided if no explicit one.
* Use `this()` to call another constructor in same class.
* `super()` calls parent constructor (must be first statement).

### `static` vs instance

* `static` members belong to class; instance members belong to object.
* `static` methods can't access instance members directly.

### `final`

* `final` variable can't change; `final` method can't be overridden; `final` class can't be extended.

### Example: Polymorphism & overriding

```java
class A { void show() { System.out.println("A"); } }
class B extends A { void show() { System.out.println("B"); } }
A obj = new B();
obj.show(); // prints "B" -> runtime polymorphism
```

### Abstract class vs Interface (concise)

* Abstract class: can have state (fields), constructors; supports method implementation. Use when classes share common code/fields.
* Interface: contract; multiple inheritance of type; Java 8+ supports default implementations.

### Gotchas & MCQs

* `static` methods are not polymorphic — calling static method via reference uses compile-time type.
* `private` methods are not inherited (can be in parent but invisible).
* `abstract class` can have constructors (but cannot be instantiated).

---

# SECTION 7 — Exception Handling (Rules & Patterns)

### Basics

* `try { } catch(ExceptionType e) { } finally { }`
* `throw new Exception("msg")` — throws
* `throws` in method signature declares checked exceptions may be thrown.

### Checked vs Unchecked

* Checked: `IOException`, `SQLException` — must be caught or declared.
* Unchecked: `RuntimeException` subclasses, e.g., `NullPointerException`, `ArithmeticException` — not required to be declared.

### Flow rules & finally

* `finally` executes except when `System.exit(0)` called or JVM killed.
* `return` in `try` or `catch` still executes `finally` before returning (unless `System.exit`).

  ```java
  int f() {
    try { return 1; } 
    finally { System.out.println("x"); } // prints x, returns 1
  }
  ```

### Custom exception

```java
class MyEx extends Exception { MyEx(String s) { super(s); } }
throw new MyEx("err");
```

### Gotchas

* Catch blocks order: child exceptions must be caught before parent. Compiler error otherwise.
* `catch (Exception e)` catches all checked and unchecked exceptions — overbroad.

---

# SECTION 8 — Java Date & Time API (Java 8+)

### Key classes (java.time)

* `LocalDate` — date without time (YYYY-MM-DD).
* `LocalTime` — time without date.
* `LocalDateTime` — both.
* `ZonedDateTime` — with timezone.
* `Period` — date-based amount (years, months, days).
* `Duration` — time-based amount (hours, minutes, seconds).
* `DateTimeFormatter` — parsing & formatting.

### Examples

```java
LocalDate d = LocalDate.of(2024, 2, 29); // valid leap year
LocalDate now = LocalDate.now();
LocalDate next = now.plusDays(5);
String fmt = now.format(DateTimeFormatter.ofPattern("dd-MM-yyyy"));
LocalDate parsed = LocalDate.parse("05-11-2025", DateTimeFormatter.ofPattern("dd-MM-uuuu"));
```

### Gotchas

* Use `Period.between(a, b)` for date differences (years/months/days). Use `Duration` for time differences (seconds/nanos).
* `SimpleDateFormat` (legacy) is not thread-safe — prefer `DateTimeFormatter`.

---

# SECTION 9 — Multi-threading & Concurrency (Short, common exam bits)

### Basics

* `Thread` class vs `Runnable`:

  ```java
  class MyThread extends Thread { public void run() { ... } }
  class MyRun implements Runnable { public void run() { ... } }
  new Thread(new MyRun()).start();
  ```
* `synchronized` keyword for locking on object/class.
* `volatile` ensures visibility across threads for single reads/writes.

### Concurrency utilities (Java util concurrent)

* `ExecutorService`, `Future`, `Callable`, `ConcurrentHashMap`, `BlockingQueue`.

### Gotchas

* `start()` starts thread; `run()` just calls method on current thread.
* Deadlocks: circular waiting for locks.

---

# SECTION 10 — Common Standard Library Quick Reference

* `Arrays` class: `Arrays.sort()`, `Arrays.copyOf()`, `Arrays.equals()`.
* `Collections` class: `Collections.sort(list)`, `Collections.reverse(list)`.
* `Math` class: `Math.max()`, `Math.min()`, `Math.pow()`, `Math.sqrt()`.

---

# SECTION 11 — Output-Prediction Examples (Short)

1. **Integer caching**

   ```java
   Integer a = 100, b = 100;
   System.out.println(a == b); // true
   Integer c = 200, d = 200;
   System.out.println(c == d); // false (outside cache)
   ```

2. **String pool & new**

   ```java
   String s1 = "a";
   String s2 = new String("a");
   System.out.println(s1 == s2); // false
   ```

3. **Finally with return**

   ```java
   int f() {
     try { return 1; } finally { return 2; }
   }
   // returns 2 (finally's return overrides)
   ```

---

# SECTION 12 — MCQ Traps & Short Answers (Exam-style)

* Q: Does `StringBuilder` have synchronization? — No (StringBuffer does).
* Q: Can a constructor be `static`? — No.
* Q: Can an `interface` have instance fields? — No (only `public static final` constants).
* Q: Can abstract class have `final` method? — Yes.
* Q: What causes `ConcurrentModificationException`? — Modifying a collection while iterating with for-each without using iterator.remove().

---

# SECTION 13 — Mini Practice Bank (20 quick tasks you should solve)

1. Reverse an integer (handle negative).
2. Check if number is palindrome (no string conversion).
3. Find second largest element in array.
4. Remove duplicates from array (in-place or using set).
5. Reverse words in a sentence.
6. Check anagram of two strings.
7. Implement binary search (iterative).
8. Merge two sorted arrays (result sorted).
9. Find kth smallest element (use PriorityQueue).
10. Implement stack using two queues (or queue using two stacks).
11. Count vowels/consonants in a string.
12. Rotate array to right by k positions.
13. Detect loop in linked list (Floyd’s tortoise & hare).
14. Implement `pow(x, n)` via fast exponentiation.
15. Sort an array of 0s,1s,2s (Dutch national flag).
16. Print FizzBuzz up to n.
17. Check balanced parentheses.
18. Convert decimal to binary string.
19. Find longest increasing subsequence (DP).
20. Serialize/deserialize simple object to/from String (basic format).

---

# SECTION 14 — Revision Tables & Cheats

### Primitive vs Wrapper quick

| Primitive | Wrapper     | Default (field) |
| --------: | ----------- | --------------- |
|     `int` | `Integer`   | 0               |
|    `long` | `Long`      | 0L              |
| `boolean` | `Boolean`   | false           |
|    `char` | `Character` | '\u0000'        |

### Access modifiers

| Modifier  | Class | Package | Subclass | World |
| --------- | :---: | :-----: | :------: | :---: |
| public    |   Y   |    Y    |     Y    |   Y   |
| protected |   Y   |    Y    |     Y    |   N   |
| default   |   Y   |    Y    |     N    |   N   |
| private   |   Y   |    N    |     N    |   N   |

### OOP Quick comparison

* `extends` (class) vs `implements` (interface).
* Single class inheritance; multiple interfaces.

---

# SECTION 15 — Final Checklist Before Exam

* Memorize: `String` mutability, `==` vs `.equals()`, primitives/wrappers, `try-catch-finally` behavior.
* Practice: binary search, string operations, arrays, Collections usage (`HashMap`, `ArrayList`).
* Be ready to trace short code outputs (5–15 lines).
* Timebox: spend first 20–25 minutes on easy MCQs, next on coding.

---

# Appendix — Short Code Snippets (Copy-ready, Minimal)

* Binary search:

```java
static int bs(int[] a, int key) {
  int l=0, r=a.length-1;
  while (l<=r) {
    int m = l + (r-l)/2;
    if (a[m]==key) return m;
    if (a[m] < key) l = m+1;
    else r = m-1;
  }
  return -1;
}
```

* Reverse string:

```java
static String rev(String s) {
  return new StringBuilder(s).reverse().toString();
}
```

* Count vowels:

```java
static int vowels(String s) {
  int c=0;
  for (char ch: s.toLowerCase().toCharArray()) if ("aeiou".indexOf(ch)>=0) c++;
  return c;
}
```

* Swap without temp:

```java
int a=5, b=3;
a = a + b; b = a - b; a = a - b;
```

(But be careful with overflow; use xor for ints if needed.)
