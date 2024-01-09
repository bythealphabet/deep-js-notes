# What is JavaScript?

## Introduction: The Heart of JavaScript

Hey there, fellow coders! You already know that JavaScript is the lifeblood of web interactions, right? But what really makes JavaScript tick? It’s built on three critical concepts, or let's call them the 'three pillars.'

### **These Three Pillars Are:** 

- Types and Coercion (how JavaScript juggles different data types)
- Lexical Scope (our spotlight topic today)
- Prototypical Inheritance (how objects in JavaScript are linked)

In this session, we're going to dive into Lexical Scope and Prototypical Inheritance. It’s like taking a closer look under JavaScript’s hood.

## Lexical Scope: Mapping the 'Where' in JavaScript

Let's unravel the mystery of Lexical Scope! It might sound highbrow, but it's a fundamental concept that's quite straightforward once you get the hang of it. Think of it as the rulebook for locating stuff in your code.

**A Little Heads-Up:**
Before we get our hands dirty, remember that JavaScript, despite being a scripting language, goes through a sort of 'dress rehearsal' called compilation. During this phase, there's a backstage wizard known as the Scope Manager. This wizard is tasked with figuring out where each variable or function should live in your code.

**Picture These Two Key Players:**
- The Scope Manager, the strategist, setting up the game board.
- The Virtual Machine, the executor, bringing the code to life.

The Scope Manager lays out the plan, and then the Virtual Machine follows it, animating your script.

**Scope: What’s That About?**
Imagine Scope as a big chart showing where every variable and function in your code resides. When you declare a variable or a function, it's like you're pinning it on this chart for JavaScript to reference later.

Example time:
```Javascript
// Scope in action:
x = 42;        // Assigning a value to 'x'.
console.log(y); // Attempting to retrieve 'y'.

```

As JavaScript runs this, it's constantly referring to the Scope chart, locating 'x' and 'y'.



**Breaking Down an Example:**

```Javascript
1 var developer = "Isaac";
2
3 function office() {
4   var developer = "Mitchell";
5   console.log("Welcome!");
6 } 
7
8 function letsGo() {
9   var walk = "Where?";
10  console.log(walk)
11 }
12
13 office(); // Output: Welcome!
14 letsGo(); // Output: Where?
```


*Lexical Scope Ilustrations:*

We can compare Scopes with buckets, and buckets within buckets. each bucket has its own color. And so the Global scope, we can give it the red color bucket.

looking into the example above we can see that Global scope has 3 
buckets, the first bucket is the developer variable, the second bucket is the office function, and the third bucket is the letsGo function.

bucket colors: 
- red: Global scope
- blue: office function scope
- green: letsGo function scope


In this script, the 'developer' variable on line 1 is a citizen of the global scope. The Scope Manager checks if a 'developer' already lives in this global neighborhood. Finding none, it allocates space for 'Isaac'. When we enter the 'office' function, we're stepping into a new scope. Here, we meet another local 'developer,' 'Mitchell'.

These two 'developers', though they share a name, are distinct because they're allocated in different scopes. No mix-up here!

After the Scope Manager arranges everyone in their respective places, it's time for the Virtual Machine to take the stage. It starts executing the script, consulting the Scope Manager at each step. For instance, at line 1, the Virtual Machine inquires about 'developer', and the Scope Manager confirms its global scope residence, allowing the Virtual Machine to allocate memory for 'Isaac'.

This dance between the Scope Manager and the Virtual Machine continues throughout the script. Each function call and variable declaration is meticulously executed based on the plan laid out by the Scope Manager.

This might seem straightforward, but there's more to Lexical Scope than meets the eye. Let’s delve deeper and explore more of these intricacies in JavaScript's world of Lexical Scope!
