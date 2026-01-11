# Static Scope vs Dynamic Scope - Programming Puzzles
> Master scope rules through fun logic puzzles! 🧩

This is a free resource filled with logic problems to help you understand the difference between Static Scope and Dynamic Scope.

What you'll find:
- ⭐ 5 Easy problems
- ⭐⭐ 3 Medium problems
- ⭐⭐⭐ 2 Hard problems
- 📖 Detailed answer explanations

## What Is Scope?

When a function references a variable, where does it look for that variable?
The answer depends on the scoping rules:

### Static Scope (Lexical Scope)
Functions look for variables WHERE THEY ARE DEFINED in the code.

### Dynamic Scope (Call Stack)
Functions look for variables in the CALL STACK (who called me?).

### Example
```c
x = 3

Func() {
    Write(x)      // Which x?
}

Main() {
    x = 4
    Func()
}
```

**Static Scope:**  
→ `Func()` is defined at global level  
→ Uses global `x = 3`  
→ **Output: 3**

**Dynamic Scope:**  
→ `Func()` is called from `Main()`  
→ Uses Main's `x = 4`  
→ **Output: 4**

**Key Difference:**  
- **Static:** "Where is the function WRITTEN?"
- **Dynamic:** "Who CALLED the function?"

## How To Use This

1. Read the problems
2. Try solving them yourself
3. Check your answers
4. Learn from the detailed explanations! 

**Don't worry if you get stuck!** The goal is learning, not perfection. 

## Contents

- [📝 All Problems](PROBLEMS.md) (10 puzzles: easy → medium → hard)
- [✅ Answer Key](ANSWERS.md) (with detailed explanations)
- [🚀 Want More?](WANT-MORE.md) (Full book coming soon!)

## Quick Start

Jump right in:  
- **New to scope?** Start with [Easy Problem 1](PROBLEMS.md#easy-1)
- **Know the basics?** Try [Medium Problem 1](PROBLEMS.md#medium-1)
- **Feeling confident?** Challenge yourself with [Hard Problem 1](PROBLEMS.md#hard-1)

## Why Learn This?

- Most modern languages use Static Scope (JavaScript, Python, Java, C)
- Common interview topic for CS/programming roles
- Foundation for understanding closures and functional programming
- Plus... it's fun! 🎯

## Feedback

Found this helpful? Have suggestions?  

- ⭐ Star this repo if you found it useful!
- 🐛 [Open an issue](../../issues) with feedback
- 💬 Reach out:  Leahmarieayoub@live.ie

---

**Created because my lecturer's teaching style didn't suit and I had to figure this out myself!** 🇮🇪

If this helped you, consider [supporting the full book](WANT-MORE.md)!

---

## License

Free to use for learning!  If you share it, please credit this repo. 