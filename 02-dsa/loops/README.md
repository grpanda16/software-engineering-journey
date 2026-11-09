# Java Loops — Complete Notes & DSA Practice

**Learning Path:** Beginner → Intermediate → Advanced → DSA Interviews  
**Language:** Java 25  
**Topic:** Control Flow — Iteration  
**Goal:** Master loops, understand their execution, and apply them to algorithmic problem-solving.

---

## Table of Contents

1. Introduction to Loops
2. Why Loops Are Important
3. Types of Loops in Java
4. For Loop — Complete Theory
5. While Loop — Complete Theory
6. Do-While Loop — Complete Theory
7. Enhanced For Loop (For-Each)
8. Nested Loops
9. Break and Continue
10. Loop Execution Flow Diagrams
11. Dry Run and Tracing
12. Common Mistakes and Tricky Cases
13. Time and Space Complexity
14. Loop Optimization Techniques
15. Real-World Applications
16. DSA Interview Patterns
17. Practice Problems
18. Progress Tracker

---

# 1. Introduction to Loops

## What is a loop?

A loop is a programming control-flow structure that executes a block of instructions repeatedly while a specified condition remains true.

Instead of writing the same instruction multiple times, we use loops to automate repetition.

### Without a loop

```java
System.out.println(1);
System.out.println(2);
System.out.println(3);
System.out.println(4);
System.out.println(5);
```

### With a loop

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

**Output:**

```text
1
2
3
4
5
```

Both programs produce the same output, but the loop is easier to maintain, extend, and reuse.

### Important terminology

| Term | Meaning |
|---|---|
| Iteration | One execution of a loop body |
| Initialization | Assigning the initial value |
| Condition | Determines whether execution continues |
| Update | Changes the loop control variable |
| Loop body | Instructions executed repeatedly |
| Loop variable | Variable controlling or tracking iterations |
| Termination | When the loop finishes |
| Infinite loop | A loop that continues indefinitely unless interrupted |

---

# 2. Why Are Loops Important?

Loops are fundamental to software engineering and DSA.

### Real-world examples

**Banking:** Process transactions or calculate account balances.

**E-commerce:** Iterate through shopping cart products to calculate the total.

**Backend development:** Process batches of records or API responses.

**Data engineering:** Transform and validate records in datasets.

**Algorithms:** Search arrays, sort values, traverse graphs, and solve optimization problems.

### Importance in DSA

| DSA Topic | How Loops Are Used |
|---|---|
| Arrays | Traversing and updating elements |
| Strings | Character processing |
| Searching | Linear and binary search |
| Sorting | Comparing and rearranging elements |
| Two pointers | Moving indices based on conditions |
| Sliding window | Maintaining ranges |
| Matrices | Row and column traversal |
| Hashing | Counting and looking up values |
| Dynamic programming | Filling DP tables |
| Graphs | Processing neighbors and traversal queues |

**Important:** Knowing loop syntax is only the beginning. DSA requires choosing the correct algorithm and understanding its complexity.

---

# 3. Types of Loops in Java

Java provides three primary loop statements and an enhanced `for` loop.

| Loop | Condition Checked | Best Use |
|---|---|---|
| `for` | Before each iteration | Count-controlled repetition |
| `while` | Before each iteration | Condition-controlled repetition |
| `do-while` | After each iteration | Execute at least once |
| Enhanced `for` | Automatically iterates | Arrays and collections |

A `for` or `while` loop may execute zero times.

A `do-while` loop always executes its body at least once when reached normally.

---

# 4. For Loop — Complete Theory

## Syntax

```java
for (initialization; condition; update) {
    // Statements
}
```

### Example

```java
public class ForLoopExample {
    public static void main(String[] args) {

        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }

    }
}
```

### Understand the three parts

```text
for (int i = 1; i <= 5; i++)
     |          |        |
     |          |        +-- Update
     |          +----------- Condition
     +---------------------- Initialization
```

**Initialization:** `int i = 1` runs once.

**Condition:** `i <= 5` is checked before each iteration.

**Body:** Runs when the condition is true.

**Update:** `i++` runs after the loop body completes normally.

## Execution Flow Diagram

```text
         START
           |
           v
      Initialize i=1
           |
           v
      Is i <= 5 ?
        /      \
      YES       NO
       |         |
       v         v
    Print i     END
       |
       v
      i++
       |
       +--------> Check condition again
```

## Dry Run

| Step | i | i <= 5 | Output |
|---|---|---|---|
| 1 | 1 | true | 1 |
| 2 | 2 | true | 2 |
| 3 | 3 | true | 3 |
| 4 | 4 | true | 4 |
| 5 | 5 | true | 5 |
| 6 | 6 | false | Stop |

## Program 1 — Print Numbers from 1 to 10

```java
for (int i = 1; i <= 10; i++) {
    System.out.print(i + " ");
}
```

**Output:**

```text
1 2 3 4 5 6 7 8 9 10
```

## Program 2 — Print Even Numbers

```java
for (int i = 2; i <= 20; i += 2) {
    System.out.print(i + " ");
}
```

**Output:**

```text
2 4 6 8 10 12 14 16 18 20
```

## Program 3 — Print Numbers in Reverse

```java
for (int i = 10; i >= 1; i--) {
    System.out.print(i + " ");
}
```

**Output:**

```text
10 9 8 7 6 5 4 3 2 1
```

## Program 4 — Sum of First N Numbers

```java
int n = 5;
int sum = 0;

for (int i = 1; i <= n; i++) {
    sum += i;
}

System.out.println(sum);
```

**Output:** `15`

### Dry Run

| i | sum before | sum after |
|---|---|---|
| 1 | 0 | 1 |
| 2 | 1 | 3 |
| 3 | 3 | 6 |
| 4 | 6 | 10 |
| 5 | 10 | 15 |

### DSA Optimization Trick

Instead of looping through all values, use:

```java
long n = 5;
long sum = n * (n + 1) / 2;

System.out.println(sum);
```

The loop approach takes **O(n)** time.

The mathematical formula takes **O(1)** time under the usual fixed-width arithmetic model.

Use a sufficiently large numeric type and consider overflow for large inputs.

---

# 5. While Loop — Complete Theory

A `while` loop repeats as long as its condition evaluates to true.

## Syntax

```java
while (condition) {
    // Statements
}
```

## Flow Diagram

```text
        START
          |
          v
     Check condition
       /       \
     true      false
      |          |
      v          v
   Execute      END
    body
      |
      +-------> Check again
```

## Program 1 — Print 1 to 5

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

**Output:**

```text
1
2
3
4
5
```

## Program 2 — Count Digits

```java
int number = 12345;
int count = 0;

while (number > 0) {
    count++;
    number /= 10;
}

System.out.println(count);
```

**Output:** `5`

This example assumes a positive integer. Zero and negative inputs require additional handling.

## When Should You Use While?

- When the number of iterations is not known in advance.
- When a loop depends on changing state.
- For binary search.
- For two-pointer algorithms.
- For linked-list traversal.

---

# 6. Do-While Loop — Complete Theory

A `do-while` loop executes its body first and checks the condition afterward.

## Syntax

```java
do {
    // Statements
} while (condition);
```

**Important:** The semicolon after the condition is required.

## Flow Diagram

```text
        START
          |
          v
      Execute body
          |
          v
     Check condition
       /       \
     true      false
      |          |
      |          v
      |         END
      |
      +-----> Execute body
```

## Example

```java
int i = 1;

do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

## Important Interview Trick

```java
int i = 10;

do {
    System.out.println(i);
} while (i < 5);
```

**Output:** `10`

Why?

Because the body executes once before checking the condition.

Compare that with a `while` loop, which would execute zero times.

---

# 7. Enhanced For Loop (For-Each)

The enhanced `for` loop is useful for reading elements from arrays and collections.

## Syntax

```java
for (type variable : collection) {
    // Statements
}
```

## Example

```java
int[] numbers = {10, 20, 30, 40};

for (int number : numbers) {
    System.out.println(number);
}
```

**Output:**

```text
10
20
30
40
```

## Normal For vs Enhanced For

| Normal For | Enhanced For |
|---|---|
| Direct index access | No automatic index variable |
| Supports reverse traversal | Typically forward traversal |
| Can modify array elements by index | Reassigning loop variable doesn't modify array |
| Useful for two-pointer logic | Useful for reading all elements |

### Tricky Example

```java
int[] arr = {1, 2, 3};

for (int x : arr) {
    x = x * 10;
}

System.out.println(arr[0]);
```

**Output:** `1`

Changing `x` doesn't change the array element because `x` receives a copy of each primitive `int` value.

For collections of objects, the loop variable receives a copy of the reference. You can mutate a referenced object if it is mutable, but reassigning the reference does not replace the collection element.

---

# 8. Nested Loops

A nested loop is a loop inside another loop.

## Example

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        System.out.print(j + " ");
    }
    System.out.println();
}
```

**Output:**

```text
1 2 3
1 2 3
1 2 3
```

## Execution Diagram

```text
Outer i = 1
   |
   +-- Inner j = 1
   +-- Inner j = 2
   +-- Inner j = 3

Outer i = 2
   |
   +-- Inner j = 1
   +-- Inner j = 2
   +-- Inner j = 3

Outer i = 3
   |
   +-- Inner j = 1
   +-- Inner j = 2
   +-- Inner j = 3
```

The inner loop completes its iterations for each outer-loop iteration.

## Program — Triangle Pattern

```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

**Output:**

```text
*
* *
* * *
* * * *
* * * * *
```

The total number of stars is:

`1 + 2 + 3 + 4 + 5 = 15`

For N rows, the number of stars is:

`N × (N + 1) / 2`

Time complexity: **O(n²)**

Auxiliary space complexity: **O(1)**, excluding printed output.

---

# 9. Break and Continue

## Break

`break` immediately terminates the nearest enclosing loop.

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;
    }
    System.out.print(i + " ");
}
```

**Output:**

```text
1 2 3 4
```

## Continue

`continue` skips the remaining statements in the current iteration.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }
    System.out.print(i + " ");
}
```

**Output:**

```text
1 2 4 5
```

### Important Difference

```text
break:
Current loop -> Exit loop

continue:
Current iteration -> Skip remaining body -> Next iteration
```

In a `for` loop, `continue` proceeds to the update expression before the next condition check.

In a `while` loop, make sure the variables controlling the condition are updated appropriately, or you may accidentally create an infinite loop.

---

# 10. Loop Execution Flow Diagrams

## For Loop

```text
Initialization
      |
      v
Condition ---- false ----> Exit
      |
     true
      |
      v
     Body
      |
      v
    Update
      |
      +--------> Condition
```

## While Loop

```text
Condition ---- false ----> Exit
      |
     true
      |
      v
     Body
      |
      +--------> Condition
```

## Do-While Loop

```text
     Body
      |
      v
Condition ---- false ----> Exit
      |
     true
      |
      +--------> Body
```

---

# 11. Dry Run and Tracing

A dry run means manually simulating code without executing it.

This is an essential DSA interview skill.

### Example

```java
int sum = 0;

for (int i = 1; i <= 4; i++) {
    sum += i * 2;
}

System.out.println(sum);
```

### Dry Run Table

| Iteration | i | i * 2 | sum |
|---|---|---|---|
| 1 | 1 | 2 | 2 |
| 2 | 2 | 4 | 6 |
| 3 | 3 | 6 | 12 |
| 4 | 4 | 8 | 20 |

**Final output:** `20`

### Dry Run Strategy

1. Identify initial variable values.
2. Evaluate the condition.
3. Execute statements in order.
4. Record updated values.
5. Repeat until the condition becomes false.
6. Check the final output.

---

# 12. Common Mistakes and Tricky Cases

## Mistake 1 — Off-by-One Error

```java
for (int i = 0; i <= 5; i++) {
    System.out.println(i);
}
```

This executes **6 times**, not 5.

The values are `0, 1, 2, 3, 4, 5`.

If you want five iterations starting at zero, use `i < 5`.

## Mistake 2 — Infinite Loop

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
}
```

`i` never changes, so the condition remains true.

**Fix:**

```java
i++;
```

inside the loop body.

## Mistake 3 — Accidental Semicolon

```java
for (int i = 0; i < 5; i++);

System.out.println("Hello");
```

The semicolon forms an empty loop body.

The print statement executes only once, after the loop finishes.

## Trick 1 — Post-Increment

```java
int i = 5;

System.out.println(i++);
System.out.println(i);
```

**Output:**

```text
5
6
```

`i++` evaluates to the old value, then increments the variable.

## Trick 2 — Pre-Increment

```java
int i = 5;

System.out.println(++i);
```

**Output:** `6`

`++i` increments first, then evaluates to the new value.

## Trick 3 — Multiple Loop Variables

```java
for (int i = 0, j = 5; i < j; i++, j--) {
    System.out.println(i + " " + j);
}
```

**Output:**

```text
0 5
1 4
2 3
```

This pattern is useful for understanding two-pointer algorithms.

## Trick 4 — Empty Loop Body

```java
int i = 0;

for (; i < 5; i++) {
}

System.out.println(i);
```

**Output:** `5`

The loop runs five iterations even though its body is empty.

## Trick 5 — Overflow

```java
int i = Integer.MAX_VALUE;
i++;
System.out.println(i);
```

**Output:** `-2147483648`

Java `int` arithmetic wraps on overflow.

This matters when designing loop bounds and binary search calculations.

---

# 13. Time and Space Complexity

Time complexity describes how an algorithm's work grows as input size increases.

Space complexity describes how much additional memory is needed.

## Example 1 — Constant Time

```java
System.out.println("Hello");
```

Time: **O(1)**  
Auxiliary space: **O(1)**

## Example 2 — Linear Time

```java
for (int i = 0; i < n; i++) {
    System.out.println(i);
}
```

Time: **O(n)**  
Auxiliary space: **O(1)**

## Example 3 — Quadratic Time

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        System.out.println(i + " " + j);
    }
}
```

Time: **O(n²)**  
Auxiliary space: **O(1)**

## Example 4 — Logarithmic Time

```java
for (int i = 1; i < n; i *= 2) {
    System.out.println(i);
}
```

For positive `n`, the loop doubles `i` each time.

Time: **O(log n)** under the usual algorithmic model, assuming arithmetic does not overflow.

## Example 5 — Consecutive Loops

```java
for (int i = 0; i < n; i++) {
    System.out.println(i);
}

for (int j = 0; j < n; j++) {
    System.out.println(j);
}
```

Total iterations: `n + n = 2n`

Time complexity: **O(n)**

### Complexity Cheat Sheet

| Loop Pattern | Complexity |
|---|---|
| Fixed number of iterations | O(1) |
| One loop over n elements | O(n) |
| Two consecutive n loops | O(n) |
| Two nested n loops | O(n²) |
| Three nested n loops | O(n³) |
| Repeatedly doubling | O(log n) |
| Outer n loop, inner logarithmic loop | O(n log n) |

**Important:** Nested loops are not automatically O(n²). You must count the actual total number of iterations.

---

# 14. Loop Optimization Techniques

## Technique 1 — Avoid Unnecessary Iterations

Instead of checking every integer for evenness:

```java
for (int i = 1; i <= 20; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

You can increment by two:

```java
for (int i = 2; i <= 20; i += 2) {
    System.out.println(i);
}
```

Both are O(n) for a variable upper bound n, but the second performs fewer iterations.

## Technique 2 — Early Exit

```java
int[] arr = {4, 8, 15, 16, 23};
int target = 15;

for (int i = 0; i < arr.length; i++) {
    if (arr[i] == target) {
        System.out.println("Found at index " + i);
        break;
    }
}
```

Stop once the answer is found.

## Technique 3 — Replace Repeated Computation

Sometimes mathematical formulas, prefix sums, hashing, or other algorithms can reduce repeated work.

However, optimization must preserve correctness.

## Technique 4 — Understand Bounds

Compare:

```java
i < n
```

and

```java
i <= n
```

The difference may cause an extra iteration or an array index error.

For an array of length `n`, valid indices are `0` through `n - 1`.

---

# 15. Real-World Applications

## Example 1 — Shopping Cart Total

```java
int[] prices = {100, 200, 300};
int total = 0;

for (int price : prices) {
    total += price;
}

System.out.println(total);
```

**Output:** `600`

## Example 2 — Finding Maximum Value

```java
int[] numbers = {12, 45, 7, 89, 23};

int max = numbers[0];

for (int i = 1; i < numbers.length; i++) {
    if (numbers[i] > max) {
        max = numbers[i];
    }
}

System.out.println(max);
```

**Output:** `89`

This example assumes the array is nonempty.

Time complexity: **O(n)**  
Auxiliary space: **O(1)**

## Example 3 — Processing Records

```java
String[] users = {"Alice", "Bob", "Charlie"};

for (String user : users) {
    System.out.println("Processing: " + user);
}
```

Loops are used in backend systems to process collections of data.

In production applications, batch processing, streaming, or database operations may be more appropriate depending on the workload.

---

# 16. DSA Interview Patterns

Master these patterns after understanding basic loops.

## Pattern 1 — Linear Traversal

```java
for (int i = 0; i < arr.length; i++) {
    // Process arr[i]
}
```

Used for arrays, strings, counting, and searching.

## Pattern 2 — Two Pointers

```java
int left = 0;
int right = arr.length - 1;

while (left < right) {
    // Process both ends

    left++;
    right--;
}
```

Used for reversing arrays, palindrome checking, and pair problems.

## Pattern 3 — Sliding Window

```java
int left = 0;

for (int right = 0; right < arr.length; right++) {
    // Expand window

    while (/* window violates condition */ false) {
        // Shrink window
        left++;
    }
}
```

This is a conceptual template. Replace the placeholder condition with a real problem-specific condition.

Used for subarrays, substrings, and range problems.

## Pattern 4 — Binary Search

```java
int left = 0;
int right = arr.length - 1;

while (left <= right) {
    int mid = left + (right - left) / 2;

    if (arr[mid] == target) {
        System.out.println(mid);
        break;
    } else if (arr[mid] < target) {
        left = mid + 1;
    } else {
        right = mid - 1;
    }
}
```

This requires an array sorted in ascending order.

Time complexity: **O(log n)**

## Pattern 5 — Matrix Traversal

```java
for (int row = 0; row < matrix.length; row++) {
    for (int col = 0; col < matrix[row].length; col++) {
        System.out.println(matrix[row][col]);
    }
}
```

Used for 2D arrays, grid traversal, and matrix problems.

---

# 17. Practice Problems

Try solving these without looking up the solution.

## Beginner — Fundamentals

- [ ] 1. Print numbers from 1 to 100
- [ ] 2. Print even numbers from 1 to 100
- [ ] 3. Print odd numbers from 1 to 100
- [ ] 4. Print numbers in reverse order
- [ ] 5. Calculate the sum of first N natural numbers
- [ ] 6. Calculate factorial of a number
- [ ] 7. Print a multiplication table
- [ ] 8. Count digits in an integer
- [ ] 9. Calculate the sum of digits
- [ ] 10. Reverse the digits of an integer

## Intermediate — Logic Building

- [ ] 11. Check whether a number is prime
- [ ] 12. Print prime numbers in a range
- [ ] 13. Generate Fibonacci numbers
- [ ] 14. Check whether a number is a palindrome
- [ ] 15. Find the GCD of two integers
- [ ] 16. Print a right triangle star pattern
- [ ] 17. Print an inverted triangle pattern
- [ ] 18. Print a number pyramid
- [ ] 19. Find the maximum element in an array
- [ ] 20. Find the second-largest distinct element

## Advanced — DSA Foundations

- [ ] 21. Implement linear search
- [ ] 22. Implement binary search
- [ ] 23. Reverse an array using two pointers
- [ ] 24. Check whether a string is a palindrome
- [ ] 25. Move zeroes to the end of an array
- [ ] 26. Find pairs with a target sum
- [ ] 27. Find maximum sum of a fixed-size subarray
- [ ] 28. Count character frequencies
- [ ] 29. Traverse a 2D matrix
- [ ] 30. Analyze nested loops with changing bounds

---

# 18. Progress Tracker

| Topic | Status |
|---|---|
| Loop fundamentals | Not started |
| For loop | Not started |
| While loop | Not started |
| Do-while loop | Not started |
| Enhanced for loop | Not started |
| Nested loops | Not started |
| Break and continue | Not started |
| Dry runs | Not started |
| Complexity analysis | Not started |
| DSA loop patterns | Not started |

**Problems solved:** 0 / 30

**Current focus:** For loops

**Next milestone:** Solve five beginner loop problems independently and explain the time and space complexity of each.

---

# Final Interview Checklist

Before considering Java loops mastered, I should be able to:

- [ ] Explain every part of a loop
- [ ] Predict loop output without executing code
- [ ] Identify off-by-one errors
- [ ] Recognize and fix infinite loops
- [ ] Choose between `for`, `while`, and `do-while`
- [ ] Understand nested-loop execution
- [ ] Calculate loop time complexity
- [ ] Explain auxiliary space complexity
- [ ] Use loops to traverse arrays and strings
- [ ] Implement basic two-pointer and sliding-window patterns
- [ ] Solve unfamiliar problems without copying solutions
- [ ] Explain my algorithm clearly

**Learning principle:** Don't memorize code. Understand the conditions, state changes, invariants, and reasons an algorithm terminates.

*Repository: software-engineering-journey | Java DSA Learning Notes*