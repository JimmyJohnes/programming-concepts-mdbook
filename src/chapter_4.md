# Chapter 4: Loops
> last updated: 2025-03-29

Before we get into what loops are there's an extra bit I need to talk about [some extra things about variables](./chapter_2.md) which are arrays  

## Arrays  
We explained before that variables are name places in memory big enough for one value, but sometimes we need more than one value, so as an effort not to repeat ourselves, arrays were made.  
Arrays assign a place in memory for multiple values under one name, so say we have a to-do list, trying to make it by adding each of them as a separate variable would be difficult  
```lua
local entry1 = "do your skincare"
local entry2 = "wash the dishes"
local entry3 = "iron your clothes"
```
it's already hard to manage these in bulk programmatically, for example editing them or adding and removing some of them while running (also called runtime), this why they created arrays, with arrays it'd look something like this  
```lua
local list_entries = {} -- declares an array
list_entries[1] = "do your skincare"
list_entries[2] = "washt he dishes"
list_entries[3] = "iron your clothes"
```
so now if you want you can just add new entry by during runtime by called `list_entries[4], list_entries[5]` and so on  
<span style="color: red">NOTE: in most languages, the array's index starts at 0, so if you want to access the Nth element, use index N-1  
for example: for the 1st element use ` list_entries[0] ` and so on, lua is the only language that starts at 1 to my knowledge, though it now also supports starting at 0</span>  

Now that we have gone over arrays, what happens if the array contains 100, 1000, or millions of items? This is where loops come in  

## Loops
They're ways to repeat a certain block of code N number of times, and they generally have 3 types  

### For loops
usually written like this
```c
for(/* initial value*/ ; /* stopping condition */ ; /* value change */){
  // do something
}
```
however it's different in some languages, so check the documentation for the language you're using, in lua it looks like this  
```lua
for initial value, stopping value, value change do
  -- do something
  end
```
Say we want to find the even numbers from 1 to 100, this would be difficult to do it manually, which is why we would want to use a loop, one way to do it is with a for loop  
first we'd want to define the loop as we did before  
```lua
for i=1,100,1 do
  -- TODO: implement the logic
end
```
we used i as a common practice, you can however name the variable that you assign the initial value to anything.  
Now we can combine that with what we learned in [Chapter 3](./chapter_3.md) to only output the numbers that are even, what are even numbers? They're numbers that don't leave a remainder when divided by 2, as we know we use a modulo `%` for that  
```lua
for i=1,100,1 do
  if (i%2 == 0) then
      print(i)
    end
end
```
what the above code does, is try every number from 1 to 100, divides it by 2, and checks if there's any remainder left, it there is, then the number is odd and the `print(i)` statement doesn't execute, otherwise the number is even and we output it.  
Running the above code outputs something like this  
```
2
4
6
8
10
...
```
### While Loops  
almost exactly the same the for loops except we moved the `initial value` and the `value change` parts outside of the loop declaration leaving us with something more like this  
```lua
while condition do 
  -- do something
  end
```
it's mostly used for when something iterates automatically, think some value that has been already declared be someone else and all you do is say "give me the next value", however, that doesn't mean it can't be used like a for loop, this is answer to the same example in the for loop but with a while loop instead  
```lua 
local i = 1
while i<=100 do 
  if (i%2==0) then
    print(i)
    end
  i = i + 1
end
```
notice how here we declared i beforehand, and increased it's value by 1 manually, and extra note, what we did for the value of it is called *incrementation*, we *increment* the value, could also find it written as `i++` or `i+=1` in other languages, they mean the same thing  

### Do While Loops
exactly what a while loop does, except it ensure it runs for at least 1 time  
so for example assume in our while loop we set i = 3 and we wanted it to run for as long as i<2, that would not even execute the loop because we already reached i>=2, a do while loop would still run once even if the condition is false, look it up in your desired language as it's not included in lua    

Lastly, there's one last thing I should mention
### the break statement
Suppose in any loop you did, there was a reason you wanted to stop, say you were sending a value to another program and that program replies back with an OK, if you don't receive that OK you want to stop the loop, that's when a break statement comes in, it stops the loop and moves out a block whenever it's executed  
so if it's in one loop
```lua
while condition do
  break
  end
```
would go back to our global scope, it's when it's not enclosed in anything (if statements, loops, and in the future, functions), however, in a local scope, say two loops inside each other (also called nested loops, same for if statements)  
for example:  
```lua 
while condition do
  while condition do
    break
    print("this statement will not be executed as the break above it will move us to the outer while loop")
    end
  print("this statemnent will be executed")
  end
```

