# Lexical Scope

We have seen the meaning of the two words in plain English.
With that knowledge, let's define **Lexical Scope** in plain English:

> **Lexical Scope** simply means that the **region** in which a **word** exists is determined by where it was **defined** or **created**.

Other definitions would be:

> **Lexical Scope** means that the meaning/value of a word can only be determined by the **region/environment** where it was created.
>
> **Lexical Scope** means that you don't directly outsource the meaning of a word to people from an outside **region** that uses the word. This is because lexical places emphasis on the origin on where it was **created/defined**.

Okay, i'll give an example.
Let's use the word: **"Dance"**.
The word "dance" was created/defined in Britain. The British people know its meaning. This word exists in the scope in which it was created: "Britain". Wales is in Britain so Wales has access to this word (remember we already explained why above). So the Welsh people can update the meaning of this word to suit their local dialect. This is because they are inside the scope of Britain.

The Germans cannot directly come and change the meaning of this word. This is because the word was not created in Germany. So, if the Germans wanted to use the English word: **"dance"** and that word has not yet been created by Britain, that word would not be available no matter how hard they try. This would make no one to know the actual meaning of that word in Germany because the word doesn't exist in the **British Lexicon**. (Don't worry if this seems gibberish, i'll explain with code later on)

Since we're students of Science and not Linguists, let's replace "word" with "variable".

Our new definition would be:

> **Lexical Scope** simply means that the **region** in which a **variable** exists is determined by where it was **defined** or **created**.
>
> **Lexical Scope** means that the meaning/value of a variable can only be determined by the region/environment where it was created.
>
> **Lexical Scope** means that you don't directly outsource the meaning of a variable to code from an outside region(block) that uses the variable. This is because lexical places emphasis on the origin on where the variable was **created/defined**.

So what lexical scope shows us is that a variable can only be used in the scope in which it was created and not where it was called.

Let's see how this works in code:

```javascript
function rideBritishBoat() {
  let boatName = "Queen's Dab"; // local variable
  return `Driving ${boatName}`;
}

function rideGermanBoat() {
  const status = rideBritishBoat();
  return status;
}

rideGermanBoat();
```

The example above simulates a scenario where the Germans bought a boat from Britain....(You could swap it which ever country you want...no need to fight why i didn't mention some other country. These are just country names and not JavaScript libraries 😛 ).
The _`rideGermanBoat()`_ uses the _`rideBritishBoat()`_.
Since JavaScript uses lexical scope, when executing the _`rideBritishBoat()`_ function, it goes to where it was **created** and gets the reference of the variable: boatName. So with lexical scoping, whenever _`rideBritishBoat()`_ is executed, JavaScript goes inside the function's scope to look for the variables used in this function.

**Note**: The scope of the _`rideBritishBoat()`_ function is its local scope and the global scope. The rideGermanBoat() is not in the lexical scope of the _`rideBritishBoat()`_ function because _`rideBritishBoat()`_ was not created inside it.

Now, let's change the example a bit:

```javascript
function rideBritishBoat() {
  return `Driving ${boatName}`; // Reference Error: boatName not defined
}

function rideGermanBoat() {
  let boatName = "Merkel's Dab";
  const status = rideBritishBoat();
  return status;
}

rideGermanBoat();
```

The above code fails. The _`rideBritishBoat()`_ functions fails to be precise. It fails when trying to access _`boatName`_ in the return statement.

**Why?**

This is because JavaScript uses lexical scope.
How this works is when it encounters _`boatName`_ variable inside the _`rideBritishBoat()`_ function, it **looks for** where the _`boatName`_ variable was **created** in its **Scope Chain**. That is, all possible scope of that function which is the: **Local Scope** of the function, then it checks its enclosing scope in this case the **Global Scope**.

So that is how JavaScript checks for variables. It first checks the local block in which the current variable is used to know if it was declared there. If it wasn't, then it goes up to the enclosing scope and keeps going if it doesn't find a declaration till it reaches the top of the chain which is the **global scope**.

There is one other type of Scoping called **"Dynamic Scoping"**.
The previous code would work in a language that supports dynamic scoping(e.g Lisp).
This is because in a dynamically scoped environment, the variable is checked at run-time. What is means is that when you execute _`rideGermanBoat()`_ and execution gets to _`rideBritishBoat()`_ the runtime environment checks for the value of _`boatName`_ where the code is currently running. In this case it finds it, so no problem and the code works at expected and prints out _`Driving Merkel's Dab`_.

**Lexical Scope** is also called **Static Scope** because its the scope is determined at compile-time. Meaning it's environment/scope is fixed and can't just change. In other words, variables can only be called from within the block of code in which it was declared/created.

**Dynamic Scope** is called **dynamic** because its environment (outer scope) can change. In other words, variables can be called from outside the block which they are created.

So we could have another function that uses the _`rideBritishBoat()`_ called _`rideBangladeshiBoat()`_:

```javascript
function rideBangladeshiBoat() {
  let boatName = "Royal Boat";
  const status = rideBritishBoat();
  return status;
}

rideBangladeshiBoat();
```

In a dynamically scoped language, you can see the value of _`boatName`_ variable inside _`rideBritishBoat()`_ is dependent on the scope in which it is executed. As we can see that this scope can change, hence it is dynamic.
So inside _`rideBritishBoat()`_, it calls the _`boatName`_ variable of _`rideBangladeshiBoat()`_ which is outside its block scope.

That's Dynamic Scoping and Lexical Scoping is the opposite.

**But remember**,

> JavaScript is not Dynamically scoped.

This is just to show you the difference.

So lexical scoping checks for variables at **compile-time** (variables needs to be created and accessible in the scope/block it is used) while dynamic scoping checks for variables at run-time (variables might not be created in the scope when compiling but can be present when the function is running).

Sticky Note on Lexical Scope -

1. Lexical scope enforces finding variables from the scope/block they were created/declared and not the environment where they are used or invoked.

2. Lexical has to do with where a variable was declared/created.
