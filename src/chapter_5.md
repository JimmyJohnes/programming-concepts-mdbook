# Chapter 5: Functions
> last updated: 2025-03-29

We're nearly done! The last two chapters have been hard so I'll try to keep it as simple as possible with this one  

Generally we don't work with code alone we work in teams and different members of those teams finish things assigned to them at different times, which is why we needed some way to make code modular, we need to be able to write a piece of code that doesn't care about what code is around it as long as it gets the right input, and we need to be able to use a piece of code made by someone else without caring about how it's written.  

Generally this is the structure of a function definition
```c
/* declaration keyword */ /* function name */ /* function parameters */ {
  /* do something */
}
```
for the declaration keyword, strongly types languages use the datatype that a function returns, so `int` lets you know you should expect an integer,`string` lets you know you should expect a string, `void` lets you know you shouldn't expect anything, however, in weakly typed languages, a lot of them just use the keyword `function`, which is what lua uses.  

The function name is just that, a name, similar to how you used a name for the variables in your code so you can use their value over and over again, a function name is used to call (ie. use their code) the function over and over again.  

Finally the function parameters, they're what the function *expects* to be given to it before it can start it's work, say you have a function that adds two numbers, you can't do that without being passed two numbers first.  
Here's how to write a function in lua  
```lua
function {function name} ({parameters})
end
```
applying it to the add two example
```lua
function add_two (num1, num2)
  local sum = num1 + num2
  return sum
  end
```
notice a new keyword here, `return`, it means "send this value back to whoever ran my code", in this case it's the sum of numbers passed to the function  
and a function that doesn't take it parameters is written like this
```lua
function {function name} ()
  -- do something
  end
```

Finally, you can call the function to use it by writing it's name followed by the parentheses and any value you pass onto the function, so in our previous example `add_two(2,3)` would return 5 which you can store in a variable or output or do with as you'd like
