# Logic

## Operators

A quick word on operators, operators are the varios math operators we borrow from math. Some examples include:
- `+` - addition
- `-` - subtraction
- `*` - multiplication
- `/` - division
- `%` - modulus (returns remander) eg: 2%3 is 2
- `**` - exponent (power) eg: 2 ** 3 is 8 

There are also operators that compare the values on either side of them. These are called comparision operators, and here are the common ones:
- `==` - are both sides of the operator equal
- `!=` - are both sides of the operator not equal 
- `>` - is the value on the left side greater than the right
- `>=` - is the value on the left side greater than or equal to the right
- `<` - is the value on the left side less than the right
- `<=` - is the value on the left side less than or equal to the right

## Conditions
In programming, there are a few common forms of control flow, or logic if you will, based on how we think in real life.

These are:
- if statements
  - else conditions
  - else if conditions
- for loops

If statements allow you to ask a question about data. Let's consider comparing the cost of two fruits. In the grocery store if we're holding a bunch of bananas and a bag of apples, we might think that `if` bananas are cheaper, we'll buy those. We know that if that's not true, that apples are cheaper, so we really only need ask `if` the bananas are cheaper. Let's do this in python:

```
In [1]: apple_price = 3.09

In [2]: banana_price = 2.12

In [3]: if banana_price < apple_price:
   ...:     print("THIS DEAL IS BANANAS! B-A-N-A-N-A-S")
THIS DEAL IS BANANAS! B-A-N-A-N-A-S
```

As we see, bananas were clearly the deal, and so our code printed our our message in the if clause. Also note that the `if` statement is formatted by the `if` keyword, followed by an expression, followed by a semi-colon `:`. The next line and all lines that should be run `if` the statement are true should be indented. This is how python knows how much of your code is intended to be run if the statement is true. 

The price of apples and bananas changes however, so how would we know if apples were the better deal? In this example, we only have two conditions, so `if` bananas are not cheaper than apples, we need to do something `else`. We can define that behavior with the `else` clause:

```
In [6]: if banana_price < apple_price:
   ...:     print("THIS DEAL IS BANANAS! B-A-N-A-N-A-S")
   ...: else:
   ...:     print("MMMMM APPLES")
THIS DEAL IS BANANAS! B-A-N-A-N-A-S
```

Now let's see what happens when apples go on sale:
```
In [7]: apple_price = 2.02

In [8]: if banana_price < apple_price:
   ...:     print("THIS DEAL IS BANANAS! B-A-N-A-N-A-S")
   ...: else:
   ...:     print("MMMMM APPLES")
MMMMM APPLES
```

This is helpful when there are only two options, but the produce isle is a little larger, so let's also compare apples and oranges (and bananas). Now we have to ask ourselves three questions:
- are apples cheaper than bananas?
- are apples cheaper than oranges?
- are bananas cheaper than oranges?
- `else`, `if` none of these are true, it must be true that oranges are cheapest

This series of questions compares all three prices. We can model that in python like this:

```py
In [1]: apple_price = 3.33

In [2]: banana_price = 2.12

In [3]: orange_price = 2.50

In [4]: cart = ""

In [5]: if apple_price < banana_price:
    ...:     cart = "apple"
    ...: elif apple_price < orange_price:
    ...:     cart = "apple"
    ...: elif banana_price < orange_price:
    ...:     cart = "banana"
    ...: else:
    ...:     cart = "orange"

In [6]: print(cart)
banana
```


# Loops

## For loops

Let's say you run the inventory for the produce department, and you have a list of all the fruit you carry, called `fruit_list`. A customer comes up to you and asks `"Do you carry mangos?"`. First, we need to look at the list:
```py
In [7]: fruit_list = ["apple", "banana", "coconut", "date", "fig", "grape", "plum"]
```

You probably scanned each item, and thought `"that's not mango"`. In python we could have written:

```py
In [8]: if fruit_list[0] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[1] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[2] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[3] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[4] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[5] == "mango":
    ...:     print("in stock")
    ...: if fruit_list[6] == "mango":
    ...:     print("in stock")
```

This is ugly to read, and you have to manually update it if you add mangos to the fruits you carry. Instead, let's loop over the list of fruits to see if our list has "mango" in it:

```py
In [9]: for fruit in fruit_list:
    ...:     if fruit == "mango":
    ...:         print("in stock")
    ...:
```

In the above example you'll notice that it iterates through our list one `fruit` at a time, assigning that variable for that iteration to `fruit`. Then, we can check the value of `fruit` to see if we have what we want.

If we run this, nothing is output, because there isn't a mango in our list. But what if the customer is looking for `date`s? 
Let's create a `fruit_query` variable that we can pass to our loop to see if something is in stock:

```py
In [10]: fruit_query = "date"
    ...: for fruit in fruit_list:
    ...:     if fruit == fruit_query:
    ...:         print(fruit_query, "is in stock")
    ...:
date is in stock
```

Fantastic, now the customer can enter what they are looking for and have a computer tell them if you carry it. 
 

 # Challenges

 1.0 - create a list of your favorite foods. create a for loop to go over your favorite_food list, and see if pizza is on the list.

 1.1 - Can you create a list of grocery item prices, then loop through your list and total all of the prices to get the cart total?

 