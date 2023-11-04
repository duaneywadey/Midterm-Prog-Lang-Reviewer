# 1.) Python Scope Example

```python
def outer_func():
    var = 100
    print("This ", var, " is from outer function")
    
    def inner_func():
        nonlocal var
        var+=50
        print("This ", var, " is from inner function")
        
        def inner_func_two():
            nonlocal var
            var+=50
            print("This ", var, " is from inner function two")
            
            def inner_func_three():
                nonlocal var
                var-=200
                print("This ", var, " is from inner function three")
            
            inner_func_three()
            
        inner_func_two()
        
    inner_func()
    
outer_func()
```

### How does the code work?

* The outer_func() is called and the local variable var is initialized with the value 100.

* The inner_func() is next called and the nonlocal keyword is used to indicate that var is a nonlocal variable. This allows it to be accessed and modified from the inner scope. The value of var is incremented by 50 using the += operator.

* The inner_func_two() is called. The value of var is incremented by 50 using the += operator.
* The inner_func_three() is called. The value of var is decremented by 200.


# 2.) Python Scope Example 

```python
def outer_func():
    var = [1,2,3,4,5]
    print("This ", var, " is from outer function")
    
    def inner_func():
        var = [2,4,6,8,10]
        print("This ", var, " is from inner function")
        
        def inner_func_two():
            var = [5,10,15,20,25]
            print("This ", var, " is from inner function two")
            
            def inner_func_three():
                nonlocal var
                var.append(30)
                print("This ", var, " is from inner function three")
            
            inner_func_three()
            
        inner_func_two()
        
    inner_func()
    
outer_func()
```

### How does the code work?

* The code defines a function called outer_func. A variable var is defined and assigned a list of numbers [1,2,3,4,5] inside the outer_func function. The code then prints a message 

* The code defines a function called inner_func inside the outer_func function. A variable var is defined and assigned a list of numbers [2,4,6,8,10] inside the inner_func. Same case with inner_func_two. 

* The code also defines yet another function called inner_func_three inside the inner_func_two function. Inside the inner_func_three function is the keyword nonlocal. It is used to indicate that the variable var refers to the same variable in the outer scope, the inner_func_two function. The code appends the number 30 to the var list.


