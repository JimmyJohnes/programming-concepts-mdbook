# Chapter 5: Functions

We're nearly done! The last two chapters have been hard so I'll try to keep it as simple as possible with this one  

Generally we don't work with code alone we work in teams and different members of those teams finish things assigned to them at different times, which is why we needed some way to make code modular, we need to be able to write a piece of code that doesn't care about what code is around it as long as it gets the right input, and we need to be able to use a piece of code made by someone else without caring about how it's written.  

Generally this is the structure of a function definition
```c
/* declaration keyword */ /* function name */ /* function parameters */ {
  /* do something */
}
```
for the declaration keyword, strongly types languages use the datatype that a function returns, so `int` lets you know you should expect an integer,`string` lets you know you should expect a string, `void` lets you know you shouldn't expect anything, however, in weakly typed languages, a lot of them just use the keyword `function`, which is what lua uses.

