# Scope Puzzles - Answer Key
> Detailed explanations for all problems.

Tip: Try the problems first! Learning happens when you struggle a bit.

---

## Easy Problems
### Easy 1 - Answer
Static Scope: 10 Dynamic Scope: 20

**Explanation**

Static Scope:
- Func() is defined at the global level
- When Func() looks for x, it checks WHERE it's defined (global scope)
- Global x = 10
- Prints: 10

Execution Trace (Static):
1. Global x = 10
2. Main() starts
3. Main's local x = 20
4. Call Func()
5. Func looks for x → defined at global → finds 10
6. Output: 10

Dynamic Scope:
- Func() is called FROM Main()
- When Func() looks for x, it checks WHO called it (call stack)
- Main() has x = 20
- Prints: 20

Execution Trace (Dynamic):
1. Global x = 10
2. Main() starts
3. Main's local x = 20
4. Call Func() FROM Main
5. Func looks for x → checks call stack → Main has x = 20
6. Output: 20

**Key Concept**

This is the fundamental difference between Static and Dynamic Scope:
- **Static** = lexical location in code
- **Dynamic** = runtime call stack

**Common Mistakes**

❌ Thinking static also uses 20 → Remember: static looks at WHERE the function is written, not called!

---

### Easy 2 - Answer
Static Scope: 15 Dynamic Scope: 25

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 10
- Looks for y → global y = 5
- Calculates: 10 + 5 = 15
- Prints: 15

Execution Trace (Static):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20 (y is not overridden in Main)
4. Call Func()
5. Func looks for x → global → finds 10
6. Func looks for y → global → finds 5
7. Output: 15

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 20
- Looks for y → Main doesn't have y, check global → y = 5
- Calculates: 20 + 5 = 25
- Prints: 25

Execution Trace (Dynamic):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 20
6. Func looks for y → not in Main → global y = 5
7. Output: 25

**Key Concept**

When only SOME variables are overridden:
- **Static** Always uses all globals (where function is defined)
- **Dynamic** Uses overridden values from caller, falls back to global for others

**Common Mistakes**

❌ Thinking both scopes give 30 (assuming y also becomes 20) → Only x is overridden in Main! y stays global.

---

### Easy 3 - Answer
Static Scope: 10 Dynamic Scope: 20

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 5
- Calculates: 5 * 2 = 10
- Prints: 10

Execution Trace (Static):
1. Global x = 5
2. Main() starts
3. Main's local x = 10
4. Call Func()
5. Func looks for x → global → finds 5
6. Calculates: 5 * 2 = 10
7. Output: 10

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 10
- Calculates: 10 * 2 = 20
- Prints: 20

Execution Trace (Dynamic):
1. Global x = 5
2. Main() starts
3. Main's local x = 10
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 10
6. Calculates: 10 * 2 = 20
7. Output: 20

**Key Concept**

Operations don't change scope rules! Whether it's addition, multiplication, or any other operation, the scope lookup rules remain the same.

---

### Easy 4 - Answer
Static Scope: 10 Dynamic Scope: 15

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 5
- Looks for y → global y = 3
- Looks for z → global z = 2
- Calculates: 5 + 3 + 2 = 10
- Prints: 10

Execution Trace (Static):
1. Global x = 5, y = 3, z = 2
2. Main() starts
3. Main's local x = 10 (y and z not overridden)
4. Call Func()
5. Func looks for all variables → all from global
6. Calculates: 5 + 3 + 2 = 10
7. Output: 10

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 10
- Looks for y → Main doesn't have y → global y = 3
- Looks for z → Main doesn't have z → global z = 2
- Calculates: 10 + 3 + 2 = 15
- Prints: 15

Execution Trace (Dynamic):
1. Global x = 5, y = 3, z = 2
2. Main() starts
3. Main's local x = 10
4. Call Func() FROM Main
5. Func looks for x → Main has x = 10
6. Func looks for y → not in Main → global y = 3
7. Func looks for z → not in Main → global z = 2
8. Calculates: 10 + 3 + 2 = 15
9. Output: 15

**Key Concept**

With multiple variables, each is looked up independently according to scope rules. Dynamic scope checks the call stack for EACH variable, falling back to outer scopes if not found in the caller.

---

### Easy 5 - Answer
Static Scope: 15 Dynamic Scope: 25

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 20
- Looks for y → global y = 5
- Calculates: 20 - 5 = 15
- Prints: 15

Execution Trace (Static):
1. Global x = 20, y = 5
2. Main() starts
3. Main's local x = 30
4. Call Func()
5. Func looks for x → global → finds 20
6. Func looks for y → global → finds 5
7. Calculates: 20 - 5 = 15
8. Output: 15

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 30
- Looks for y → Main doesn't have y → global y = 5
- Calculates: 30 - 5 = 25
- Prints: 25

Execution Trace (Dynamic):
1. Global x = 20, y = 5
2. Main() starts
3. Main's local x = 30
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 30
6. Func looks for y → not in Main → global y = 5
7. Calculates: 30 - 5 = 25
8. Output: 25

**Key Concept**

Subtraction works just like addition for scope purposes. The operation type doesn't affect how variables are looked up!

---

## Medium Problems
### Medium 1 - Answer
Static Scope: 50 Dynamic Scope: 100

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 10
- Looks for y → global y = 5
- Calculates: 10 * 5 = 50
- Prints: 50

Execution Trace (Static):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20
4. Call Func()
5. Func looks for x → global → finds 10
6. Func looks for y → global → finds 5
7. Calculates: 10 * 5 = 50
8. Output: 50

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 20
- Looks for y → Main doesn't have y → global y = 5
- Calculates: 20 * 5 = 100
- Prints: 100

Execution Trace (Dynamic):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 20
6. Func looks for y → not in Main → global y = 5
7. Calculates: 20 * 5 = 100
8. Output: 100

**Key Concept**

Multiplication makes the difference more dramatic! The larger result difference (50 vs 100) makes the scope distinction very obvious.

---

### Medium 2 - Answer
Static Scope: 15 Dynamic Scope: 30

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 10
- Looks for y → global y = 5
- Calculates: 10 + 5 = 15
- Prints: 15

Execution Trace (Static):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20, y = 10
4. Call Func()
5. Func looks for x → global → finds 10
6. Func looks for y → global → finds 5
7. Calculates: 10 + 5 = 15
8. Output: 15

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 20
- Looks for y → Main has y = 10
- Calculates: 20 + 10 = 30
- Prints: 30

Execution Trace (Dynamic):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20, y = 10
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 20
6. Func looks for y → call stack → Main has y = 10
7. Calculates: 20 + 10 = 30
8. Output: 30

**Key Concept**

When ALL variables are overridden in the caller:
- **Static** Still uses all globals (ignores caller completely)
- **Dynamic** Uses all values from caller (doubles the difference!)

Notice the dynamic result is EXACTLY double the static result!

---

### Medium 3 - Answer
Static Scope: 30 Dynamic Scope: 50

**Explanation**

Static Scope:
- Func() is defined at global level
- Looks for x → global x = 10
- Looks for y → global y = 5
- Calculates: (10 + 5) * 2 = 15 * 2 = 30
- Prints: 30

Execution Trace (Static):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20
4. Call Func()
5. Func looks for x → global → finds 10
6. Func looks for y → global → finds 5
7. Calculates: (10 + 5) * 2 = 30
8. Output: 30

Dynamic Scope:
- Func() is called FROM Main()
- Looks for x → Main has x = 20
- Looks for y → Main doesn't have y → global y = 5
- Calculates: (20 + 5) * 2 = 25 * 2 = 50
- Prints: 50

Execution Trace (Dynamic):
1. Global x = 10, y = 5
2. Main() starts
3. Main's local x = 20
4. Call Func() FROM Main
5. Func looks for x → call stack → Main has x = 20
6. Func looks for y → not in Main → global y = 5
7. Calculates: (20 + 5) * 2 = 50
8. Output: 50

**Key Concept**

Nested operations follow normal order of operations:
1. Parentheses first: (x + y)
2. Then multiplication: result * 2

Scope rules apply to variable lookup BEFORE any calculations happen!

---

## Hard Problems
### Hard 1 - Answer
Static Scope: 1 Dynamic Scope: 2

**Explanation**

This is the first problem with MULTIPLE FUNCTIONS and NESTED CALLS!

Static Scope:
- Func1() is defined at global level
- When Func1() looks for x, it checks WHERE it's defined (global)
- Global x = 1
- Prints: 1
- Note: It doesn't matter that Func2 has x = 2, or that Main has x = 3. - Func1 is defined at global level, so it uses global x!

Execution Trace (Static):
1. Global x = 1
2. Main() starts → local x = 3
3. Main() calls Func2()
4. Func2() starts → local x = 2
5. Func2() calls Func1()
6. Func1() looks for x → WHERE is Func1 defined? → Global level
7. Uses global x = 1
8. Output: 1

Dynamic Scope:
- Func1() is called FROM Func2()
- When Func1() looks for x, it checks WHO called it (call stack)
- Immediate caller is Func2, which has x = 2
- Prints: 2
- Note: Even though Main has x = 3, the IMMEDIATE caller is Func2 with x = 2!

Execution Trace (Dynamic):
1. Global x = 1
2. Main() starts → local x = 3
3. Main() calls Func2()
4. Func2() starts → local x = 2
5. Func2() calls Func1() ← IMMEDIATE CALLER
6. Func1() looks for x → check call stack → Func2 has x = 2
7. Uses Func2's x = 2
8. Output: 2

**Key Concept**

CRITICAL for dynamic scope: It's the IMMEDIATE caller that matters, not the original caller!

Call chain: Main → Func2 → Func1

Func1 uses Func2's x (not Main's x!)

**Common Mistakes**

❌ Thinking dynamic scope prints 3 (Main's x) → The IMMEDIATE caller is Func2, not Main!

❌ Getting confused by the nested calls → Draw the call stack! It helps visualize who called whom.

---

### Hard 2 - Answer
Static Scope: 3 Dynamic Scope: 30

**Explanation**

This problem has MULTIPLE FUNCTIONS and MULTIPLE VARIABLES!

Static Scope:
- FuncA() is defined at global level
- Looks for x → global x = 1
- Looks for y → global y = 2
- Calculates: 1 + 2 = 3
- Prints: 3
- Note: FuncB's y = 20 and Main's x = 10 are completely ignored in static scope!

Execution Trace (Static):
1. Global x = 1, y = 2
2. Main() starts → local x = 10
3. Main() calls FuncB()
4. FuncB() starts → local y = 20
5. FuncB() calls FuncA()
6. FuncA() looks for x → defined at global → x = 1
7. FuncA() looks for y → defined at global → y = 2
8. Calculates: 1 + 2 = 3
9. Output: 3

Dynamic Scope:
- FuncA() is called FROM FuncB()
- Looks for x → not in FuncB → check next in stack → Main has x = 10
- Looks for y → FuncB has y = 20
- Calculates: 10 + 20 = 30
- Prints: 30
- Note: Each variable is looked up independently in the call stack!

Execution Trace (Dynamic):
1. Global x = 1, y = 2
2. Main() starts → local x = 10
3. Main() calls FuncB()
4. FuncB() starts → local y = 20
5. FuncB() calls FuncA() ← IMMEDIATE CALLER
6. FuncA() looks for x → not in FuncB → check stack → Main has x = 10
7. FuncA() looks for y → check FuncB → has y = 20
8. Calculates: 10 + 20 = 30
9. Output: 30

**Key Concept**

With multiple variables in dynamic scope:
- EACH variable is looked up independently
- Search order: immediate caller → next in stack → ... → global
- x found in Main (further up the stack)
- y found in FuncB (immediate caller)

**Call stack visualization:**
```
Global: x=1, y=2
  ↑
Main: x=10
  ↑
FuncB: y=20
  ↑
FuncA needs x and y
```

Dynamic lookup walks UP the stack until it finds each variable!

**Common Mistakes**

❌ Thinking dynamic gives 3 or 22 (using some globals) → Dynamic scope searches the ENTIRE call stack, not just immediate caller!

❌ Thinking x uses FuncB's value → FuncB doesn't have x! Keep searching up the stack to Main!

## Summary
Congratulations on completing all 10 puzzles!

### Key Takeaways:

**Static Scope (Lexical):**
- "Where is the function WRITTEN?"
- Always uses variables from where the function is DEFINED
- Determined at compile time (reading the code)
- Used by: JavaScript, Python, Java, C, C++, most modern languages

**Dynamic Scope:**
- "Who CALLED the function?"
- Uses variables from the call stack at runtime
- Searches: immediate caller → next caller → ... → global
- Used by: Early Lisp, some Perl, Bash variables (rarely used today)

**Why Static Scope Won:**
- Easier to reason about (just read the code!)
- Better performance (no runtime stack searching)
- Enables optimizations
- More predictable behavior

**But understanding BOTH helps you:**
- Debug weird variable behavior
- Understand closures and lexical scoping deeply
- Ace interview questions about scope
- Appreciate why languages work the way they do

## Want More Practice?

If you found these puzzles helpful, check out [WANT-MORE.md](WANT-MORE.md) for information about the full book with 100+ problems!

## Need Help?

Still confused about something? Open an issue and let's discuss it!