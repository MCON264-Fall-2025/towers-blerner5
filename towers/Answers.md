#  MCON 264 — Recursion Assignment: Towers of Hanoi × 3


##  Overview

In this lab, you implemented three recursive versions of the Towers of Hanoi problem and (optionally) one iterative version.  
Each part reinforces a key concept of recursion — base case, recursive case, and growth pattern — and illustrates how recursion can be refactored or replaced by iteration.

---

## Part 1 — Classic Towers of Hanoi (`TowersOfHanoi.java`)

### 1. Base Case
_Describe the base condition that stops recursion (for example, what happens when `n == 0`?)._

> ✎ Your answer here
when n is 0 recusrsion cannot happen becuase you can not go down from 0
### 2. Recursive Case
_Explain the sequence of recursive calls and what each represents._

>✎ Your answer here
> recursive calls is when you call to a method on the number before you in the stack


### 3. Sample Trace (for n = 3)

| Move # | From | To |
|:--:|:--:|:--:|
| 1 | A | C |
| 2 | A | B |
| 3 | C | B |
| … |  |  |

_Total moves = 2ⁿ − 1 = 7 (for n = 3)_

---

## Part 2 — Counting Moves (`TowersExercise21.java`)

### 1. Approach
_How did you modify the standard recursion to count rather than print moves?_

>  Your answer here
> instead of calling the moves 2 times i called it 3 times

### 2. Verification of Formula
_Complete the table and verify that count = 2ⁿ − 1._

| n | Expected (2ⁿ − 1) |     Program Output     | Matches? (Y/N) |
|:--:|:--:|:----------------------:|:--------------:|
| 1 | 1 |           1            |       Y        |
| 2 | 3 |           7            |       N        |
| 3 | 7 |          128           |       N        |
| 4 | 15 |         32,767         |       N        |
| 5 | 31 |       1,048,575        |       N        |

### 3. Reflection
_What changes when you replace printed moves with a counter? What are the pros and cons?_

> ✎ Your answer here
how to measure the algorithm
pro = quicker con = harder to debug
---

## Part 3 — Hanoi Variation (`TowersVariations.java`)

### 1. New Rule
_Every move must pass through the middle peg. How does this alter the recursion?_

> ✎ Your answer here
> many more steps are involved

### 2. Observed Move Counts

| n | Expected ≈ 3ⁿ − 1 | Program Output | Matches? (Y/N) |
|:--:|:--:|:--------------:|:--------------:|
| 1 | 2 |       2        |       Y        |
| 2 | 8 |       8        |       Y        |
| 3 | 26 |       26       |       Y        |
| 4 | 80 |       80       |       Y        |

### 3. Analysis
_Why does this variation grow faster than the standard version? How do additional move constraints affect complexity?_

> ✎ Your answer here
because there is an extra step involved
> the algorithm has to include all those extra steps
---

## Comparative Analysis

### 1. Growth Patterns

| Version | Approx. Formula | Growth Type |
|:--|:--|:--|
| Standard | 2ⁿ − 1 | Exponential |
| Variation | 3ⁿ − 1 | Exponential (faster) |
| Iterative (Optional) | 2ⁿ − 1 | Same as recursive but loop based |

### 2. Stack Depth and Memory
_Estimate the maximum recursion depth before StackOverflowError and discuss how stack size (–Xss flag) affects this._

> ✎ Your answer here
> the highest n can go is probably 1,000 (I had to ask AI about this)
> -Xss lets you maually decide size of stack

---

## Part 4 — Beyond Recursion (Extra Credit)

### Iterative / Explicit-Stack Version (`TowersIterative.java`)

1. How does your iterative version simulate recursion?
2. How did you track pending calls or frames?
3. Which version (r vs iterative) is clearer? Why?

> ✎ Your answer here

---

## Discussion &amp; Reflection

1. What three questions can you use to verify a recursive solution works?
2. How do the base case and recursive case cooperate to guarantee termination?
3. What is the trade-off between elegance and efficiency in recursion?

> ✎ Your answers here
>is there a base case, what is my max number of steps, do I have to use the mid
> makes sure you are only counting valuable numbers...nothing that cannot be recursed
> the answers are correct and efficient but the code is a lot of redundancy

---

## References (APA or MLA format)

- Dale, N., Joyce, D., &amp; Weems, C. (2016). *Object-Oriented Data Structures Using Java* (Ch. 3 Recursion). Jones &amp; Bartlett.
- Additional videos or websites you consulted (YouTube CS50 Recursion, GeeksForGeeks Hanoi, etc.)

---

 **Submission Checklist**

- [ ] `TowersOfHanoi.java` — implemented and tested
- [ ] `TowersExercise21.java` — counts moves correctly
- [ ] `TowersVariations.java` — middle-peg constraint implemented
- [ ] (Extra Credit) `TowersIterative.java` — loop or explicit stack solution
- [ ] All JUnit tests pass (green on GitHub Actions)
- [ ] This `ANSWERS.md` file completed and committed to repo  
