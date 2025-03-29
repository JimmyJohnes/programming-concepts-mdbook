# Chapter 4: Loops
> last updated: 2025-03-27  

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

