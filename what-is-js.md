# What is JavaScript

## Introduction: JavaScript's Pillars

JavaScript, a versatile and widely-used programming language, can be divided into three fundamental parts, known as the 'three pillars.'
 Understanding these pillars is essential to grasp the essence of JavaScript.

 Comprehending these concepts not only enhances our confidence in writing JavaScript but also plays a pivotal role in minimizing bugs in our code.


### **The three pillars are:** 

- Types and Coercion
- Lexical Scope
- Prototypical Inheritance

In this article, we will focus specifically on Lexical Scope and Prototypical Inheritance. The aim is to provide a thorough understanding of these two pillars, enabling you to make informed choices in your approach to JavaScript development.

## Lexical Scope

Understanding JavaScript's Lexical Scope is a key step in grasping closures and, by extension, the module pattern in JavaScript.

before we jump into scoops it is important to note that even tho Javascript is a script language, The Javascript engine still goes thru a compilation process before executing the code. in the compiled process we can say that Javascript has a kind of Scope manager. the job of the scope manager is determines two things: the role of a variable (is it being set or accessed?) and the scope in which this variable exists.
right after this first pass "compilation", Javascript will pass the job to the Virtual Machine to execute the code.

so lets imagine that we have two different characters talking to each other in this Javascript story.

- the Scope manager
- the Virtual Machine.

the Scope manager will be the one preparing everything before hand, and creating a plan. this plan will be used for when the execution engine steps in and start to excute our code.

**So... what is Scope?**

Scope in JavaScript can be thought of as the context in which values and expressions are 'visible' or can be accessed. Essentially, it's about 'where to look for things.' A variable in JavaScript can play two roles: either a value is being assigned to it, or a value is being retrieved from it. 

Consider this example:
```Javascript
// Example of scope in action:
x = 42;        // Here, 'x' is being assigned a value.
console.log(y); // Here, the value of 'y' is being retrieved.
```
When a Javascript engine process the code it is constantly asking at first in what position is this variable in, and secondly in what scope is this variable in. 

When the JavaScript engine processes this code, it first identifies the positions of variables 'x' and 'y'. Then, it determines the scopes where these variables exist. If a variable is not found in the immediate scope, the engine looks outward to the enclosing scope, continuing this process until the variable is found or no more scopes are available.

so lets break this down with an example.

```Javascript
1 var developer = "Isaac";
2
3 function office() {
4   var developer = "Mitchell";
5    console.log("Welcome!");
6 } 
7
8 function letsGo() {
9    var walk = "Where?";
10    console.log(walk)
11 }
12
13 office(); // Welcome!
14 letsGo(); // Where?
```

In our example, the 'developer' variable declared at the top on line 1 is in the global scope. 
When the compiler processes this line, it checks if the variable already exists in the global scope. If not, it creates the variable and assigns the value 'Isaac' to it. As the compiler continues, it encounters the 'office' function on line 3. 

This function creates a new scope. Inside this scope, on line 4, there is another 'developer' variable. The compiler checks if this variable exists within the 'office' scope and, finding that it does not, assigns the value 'Mitchell' to it. It's important to note that this 'developer' is different from the global 'developer' because they exist in separate scopes

In the example above, the compiler will be setting the developer variable the office function and the letsGo function to the Global scope.
also it will be setting the second developer variable that we find on line 4 to the office scope.

and on line 9 the walk variable will be set in the letsGo function scope.

right after the Scope manager has done is job, and there is no more declaration, we can say it prepared the everything,  before execution in some way it created a plan and now it is ready for execution.

so now the Scope Manager has it's plan at hand and the Engine starts in to execute the code. and it while the engine is working it will be asking the to the Scope manager, details about the parts of code it needs to execute.

so the Virtual Machine Engine start execution, it will check line 1 it sees that there is a declaration for developer so it asks the Scope manager, hey do you know something about a developer? the Scope manager will answer yes here it is, it's in the global scope. and so the Virtual engine excutes line one and creates a space for the value "Isaac" and saves it somewhere in the computer".

right there after the Virtual Machine will jump to line 13 and checks again with the the Scope manager, and asks do you know about a office.
the Scope manager checks its plan. and sees yes there is one. so it passes it to the  Virtual machine, and so the Virtual machine will execute the function "office". so now we are in the office function, and the Scope manager and the Virtual machine will do the same proccess in the office function, asking if he know about the developer variable, the Scope manager checks it plan finds that yes there it is and passes it to the Virtual machine so that it can create (alocate space) and save the string "Mitchell".  









  



