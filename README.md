# **CalcScript Interpreter**

## **What do we expect from this test**

We expect you to create an interpreter which fulfills our requirements and still be open for more additions and/or modifications.  
The interpreter should be able to **read**, **parse** and **execute** a simple textual language called **CalcScript**.

A program in CalcScript is a sequence of textual instructions written line by line.  
Each line represents a statement that must be executed in order, and the program finishes when there are no more statements.

Encountering an unknown instruction means something went wrong.

---

## **Part 1 — Basic interpreter**

You must build a basic interpreter for **CalcScript**.

CalcScript programs may contain three types of statements:

---

### 1. Variable assignment
```text
let x = 10
```
This defines a variable named `x` with the value `10`.  
If the variable already exists, its value must be overwritten.

---

### 2. Print statement
```text
print x
```
This prints the value of the expression that follows the keyword `print`.  
For example, if `x` is `10`, it should output:
```text
10
```

---

### 3. Arithmetic expressions
CalcScript supports basic arithmetic operations and parentheses:
```text
+   -   *   /   %
```

Example:
```text
let y = (x + 2) * 3
print y
```

If `x` was `10`, this program should output:
```text
36
```

The interpreter should evaluate expressions from left to right respecting operator precedence and parentheses.

---

### **Part 1 Example**

Given the following CalcScript program:

```text
let a = 5
let b = 3
let result = (a + b) * 2
print result
```

**Step by step:**
1. `a` is assigned the value `5`
2. `b` is assigned the value `3`
3. `(a + b) * 2` → `(5 + 3) * 2` → `16`
4. `result` becomes `16`
5. `print result` → outputs `16`

**Output:**
```text
16
```

---

## **Part 2 — Input and comparisons**

We are going to extend CalcScript to support **user input** and **comparison operators**.

---

### 1. Input statement
```text
input x
```
This reads a single integer value from the user and stores it in the variable `x`.

Example:
```text
input number
let doubled = number * 2
print doubled
```

If the user enters `4`, the output should be:
```text
8
```

---

### 2. Comparison operators
CalcScript supports the following comparison operators:
```text
==   !=   <   >   <=   >=
```
Each comparison returns `1` if true, or `0` if false.

Example:
```text
let x = 5
let y = 7
print x < y
print x == y
```

Output:
```text
1
0
```

---

## **Part 3 — Logic and functions**

Now we are going to add **logical operations** and **built-in functions**.

---

### 1. Logical operators
```text
&&   ||
```
- `&&` (AND): returns `1` if both sides are non-zero.  
- `||` (OR): returns `1` if at least one side is non-zero.

Example:
```text
let a = 1
let b = 0
print a && b
print a || b
```

Output:
```text
0
1
```

---

### 2. Built-in functions
CalcScript includes the following built-in functions:

| Function | Description | Example | Output |
|-----------|--------------|----------|---------|
| `abs(x)` | Returns the absolute value of `x` | `abs(-10)` | `10` |
| `max(a,b)` | Returns the greater value | `max(4, 7)` | `7` |
| `min(a,b)` | Returns the smaller value | `min(4, 7)` | `4` |

Example:
```text
let a = -10
let b = 5
print abs(a)
print max(a, b)
print min(a, b)
```

Output:
```text
10
5
-10
```

---

## **More examples**

---

### **Example 1**
```text
input n
let square = n * n
print square
```

If the user enters `4`, output should be:
```text
16
```

---

### **Example 2**
```text
let x = 2
let y = 5
let bigger = (x > y) ? x : y
print bigger
```

Output:
```text
5
```

---

### **Example 3**
```text
let a = 10
let b = 3
print (a / b) * b + (a % b)
```

Output:
```text
10
```

---

## **Expected behavior**

- The interpreter must read and execute the program line by line.  
- Expressions must support parentheses and operator precedence.  
- Variables can be reused and updated.  
- Input values are always integers.  
- Boolean results (`true` / `false`) are represented as `1` and `0`.  
- Unknown identifiers or syntax errors should stop the program with a clear message.

---
