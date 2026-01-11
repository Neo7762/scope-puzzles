# Scope Puzzles - Problems
> For each problem, determine what gets printed under both Static Scope and Dynamic Scope.

Use the workspace to trace through your logic!
---
## Easy Problems
### Easy 1
**Difficulty:**  ⭐

```c
x = 10

Func() {
     Write(x) 
     }

Main() {
     x = 20 
     Func() 
     }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Easy 2
**Difficulty:**  ⭐

```c
x = 10 
y = 5

Func() { 
    Write(x + y) 
    }

Main() { 
    x = 20 
    Func() 
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Easy 3
**Difficulty:**  ⭐

```c
x = 5

Func() {
    Write(x * 2) 
    }

Main() { 
    x = 10 
    Func() 
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Easy 4
**Difficulty:**  ⭐

```c
x = 5 
y = 3 
z = 2

Func() { 
    Write(x + y + z) 
    }

Main() {
    x = 10 
    Func() 
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Easy 5
**Difficulty:**  ⭐

```c
x = 20
y = 5

Func() {
    Write(x - y)
    }

Main() {
    x = 30
    Func()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
## Medium Problems
### Medium 1
**Difficulty:**  ⭐⭐

```c
x = 10
y = 5

Func() {
    Write(x * y)
    }

Main() {
    x = 20
    Func()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Medium 2
**Difficulty:**  ⭐⭐

```c
x = 10
y = 5

Func() {
    Write(x + y)
    }

Main() {
    x = 20
    y = 10
    Func()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Medium 3
**Difficulty:**  ⭐⭐

```c
x = 10
y = 5

Func() {
    Write((x + y) * 2)
    }

Main() {
    x = 20
    Func()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
## Hard Problems
### Hard 1
**Difficulty:** ⭐⭐⭐

```c
x = 1

Func1() {
    Write(x)
    }

Func2() {
    x = 2
    Func1()
    }

Main() {
    x = 3
    Func2()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
### Hard 2
**Difficulty:** ⭐⭐⭐

```c
x = 1
y = 2

FuncA() {
    Write(x + y)
    }

FuncB() {
    y = 20
    FuncA()
    }

Main() {
    x = 10
    FuncB()
    }
```

**Questions:**
- What gets printed in Static Scope? `_______`
- What gets printed in Dynamic Scope? `_______`

**Workspace:**

```
[Your working here]









```
---
## Check Your Answers
Ready to see how you did? → [View Answer Key](ANSWERS.md)


Don't peek too early! 😉
