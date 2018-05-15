

![](https://media.giphy.com/media/3o6EhWs5qeqi5ENCzm/giphy.gif)
As the title states, JavaScript closures have always been a bit of a mystery to me. I have read multiple articles, I have used closures in my work, sometimes I even used a closure without realizing I was using a closure.
Recently I went to a talk where someone really explained it in a way it finally clicked for me. I’ll try to take this approach to explain closures in this article. Let me give credit to the great folks at CodeSmith and their JavaScript The Hard Parts series.
Before we start
Some concepts are important to grok before you can grok closures. One of them is the execution context.

![](https://cdn-images-1.medium.com/max/800/1*1vMy563vz6LA_67VrzeT9g.png)

When code is run in JavaScript, the environment in which it is executed is very important, and is evaluated as 1 of the following:
Global code — The default environment where your code is executed for the first time.
Function code — Whenever the flow of execution enters a function body.
(…)
(…), let’s think of the term execution context as the environment / scope the current code is being evaluated in.
In other words, as we start the program, we start in the global execution context. Some variables are declared within the global execution context. We call these global variables. When the program calls a function, what happens? A few steps:
JavaScript creates a new execution context, a local execution context
That local execution context will have its own set of variables, these variables will be local to that execution context.
The new execution context is thrown onto the execution stack. Think of the execution stack as a mechanism to keep track of where the program is in its execution
When does the function end? When it encounters a return statement or it encounters a closing bracket }. When a function ends, the following happens:
The local execution contexts pops off the execution stack
The functions sends the return value back to the calling context. The calling context is the execution context that called this function, it could be the global execution context or another local execution context. It is up to the calling execution context to deal with the return value at that point. The returned value could be an object, an array, a function, a boolean, anything really. If the function has no return statement, undefined is returned.
The local execution context is destroyed. This is important. Destroyed. All the variables that were declared within the local execution context are erased. They are no longer available. That’s why they’re called local variables.

Here is how it works. Whenever you declare a new function and assign it to a variable, you store the function definition, as well as a closure. The closure contains all the variables that are in scope at the time of creation of the function. It is analogous to a backpack. A function definition comes with a little backpack. And in its pack it stores all the variables that were in scope at the time that the function definition was created.

So our explanation above was all wrong, let’s try it again, but correctly this time.

