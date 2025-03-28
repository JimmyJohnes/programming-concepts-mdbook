# Chapter 3: Conditionals  
> last updated: 2025-03-26  

Sometimes you only want to activate some part of the code only if some condition applies, Say you're creating a login page that only admits one person named "mark" with all lowercase characters.   

## IF statements  
if statements allow us to execute a piece of code *if* a condition applies, otherwise, it'll be ignored and in most programming languages it looks like this:
```c
  if (condition) {
  // do something
  }
```
with some changes like removing the need for parentheses of brackets, or replacing them with a keyword or a way to indicate the start and end of an if statement.
In lua it looks like this:
```lua
  if condition then
    -- do something
    end
```
and you replace "condition" with what's called `operands` similar to in how we have in maths  
- `=` for equals
- `>` more than
- `<` less than
- `>=` more than or equals
- `<=` less than or equals
- we also have `%` for remainder, called modulo or modulus
we have here these `operands` that evaluate to either true or false, they are:
- `==` for equals
- `!=` for not equals
- `>` for more than
- `<` for less than
- `>=` for more than or equals
- `<=` for less than or equals
most programming languages have types of if statements too  

### Normal if statements
they're similar to the examples above, so let's implement the example we first mentioned, first I want you to think of the steps to implement this yourself generally not in code and then we'll figure out how to implement it.  
<details>
  <summary>Answer</summary>
  first you would want to get the user's name through some form of input, wouldn't you?  
  But how would the user know that we require their name if we don't output something telling them what we want?
  Now that we established that we need to show them some prompt and take their input, we use what learned before to write it like this  

  ```lua
    print("what is your name? please write it in all lowercase")
    io.read()
  ```
  but now we also need to remember the user input don't we? Because we want to check if their name is "mark"  
  ``` lua
  print("what is your name? please write it in all lowercase")
  local user_name = io.read()
  ```
  now we get to the point where we check if it's mark, we use the example in we used before to write it 
  ```lua
  print("what is your name? please write it in all lowercase")
  local user_name = io.read()
  if user_name == "mark" then
    print("Oh hi, mark!")
    end
  ```
</details>

### If else statements
  similar to if statements, you can add an else block for whenever the condition evaluates to false, so if `name == mark ` for example we want to show "Oh hi, mark", otherwise it'll show "Go away"
in lua you'd have an else statement like this
```lua
if condition then
  --do something
else
  --do something else
 end
```
so the Answer to it would be like this
<details>
  <summary>Answer</summary>

  ```lua
  print("what is your name? please write it in all lowercase")
  local user_name = io.read()
  if user_name == "mark" then
    print("Oh hi, mark!")
  else
    print("Go away!")
    end
  ```
</details>

### switch case
this is similar to an if statement, it's mostly used because writing multiple if statements after each other is harder to read and is slower in performance, but otherwise you're free to use whichever, lua doesn't seem to have an implementation for it so I'll refrain from writing an example, you can look it up yourself.
