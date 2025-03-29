# Chapter 6: Classes

Following [Chapter 5](./chapter_5.md), classes are a way to keep your code modular, however this time we also encapsulate the variables too, say you have a list of students, each student has a name, a year they're in, and their birthdate, one way you could do it is by making them into arrays like this  

```lua
local names = {"name1","name2","name3"}
local years = {"grade 1","grade 2","grade 3"}
local birthdates = {"12-1-2001","1-2-2003","2-2-2003"}
```

You see how this is grounds for issues? You might miss something and make different size arrays, you might remove a student from the names list but not from the years or birthdates lists, this is why we encapsulate every variable related to an object into something called a class, you could say it's defining a custom data type

Now because there's a lot of things related to classes and I'll only cover very basic things like class definition, class functions (also called methods), default values, and class usage.

### class Definition and Default values

Class definitions differ between languages, so check the documentation of your preferred language, however, in lua it is done like this  
```lua

Student = {
  name = "placeholder name",
  year = "placeholder year",
  birthdate = "placeholder birthdate"
}
function Student:create(o)
    o.parent = self
  end
```
Here we defined an class with some default values for name, year, and birthdate, so in case we forgot to assign a value to them, these values will show up, which makes for a nice of error detection  

Worth noting how the class name starts with a capital letter, that's mostly just convention, just how it's a convention for constants (values that will not change ever) to be written all in uppercase  

And the bit of `o.parent = self` can be considered black magic for now, all it does is make a new object with the same format as that class

### class Functions

Some classes can have methods/functions, say you and someone else are working on a game that has cars :) cars can move, correct? And each car has a model and top speed, you were tasked with creating the car class so all your friend should care about is having a car object (an instance of the class) that he can tell to move.  

We'll first start by defining the class as we did in the class definition part  
```lua

Car= {
  model= "placeholder model",
  top_speed=0 
}
function Car:create(o)
    o.parent = self
  end

```

This will allow your friend to make a new car to their liking by `Car:create`  so if they wanted a Sedan with a top speed of 100 (unit intentionally left blank) then they can just do `local car1 = Car:create{model="sedan",top_speed=100}` and that would be it :D  

All that's left now is making the care move, see how we wrote a function that creates an instance of the car? It's exactly the same way here too 
```lua


Car= {
  model= "placeholder model",
  top_speed=0 
}
function Car:create(o)
    o.parent = self
  end
function Car:move()
  print("Vroom!")
  end

```

That's literally it :D your friend now can call it with `car1:move()` without caring about what actually is inside the function `move()`
