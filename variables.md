# Variables

Variables are place holders for values, just as they are in math. In python, instead of using the single character variables you do in math, we use words describing variable values, like `tire_pressure`, `temperature`, or `name`. 

There are guidelines to be aware of when choosing a variable name, which are defined in `PEP`s, or python enhancement proposals. These are found here:
https://www.python.org/dev/peps/

Reading them all is mundane and impractical. However, there are some important ones to be aware of, such as `PEP 8` which was the first python style guide:
https://www.python.org/dev/peps/pep-0008/


## Naming conventions

The important bits on naming a variable are condensed for you here:
```
- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive (age, Age and AGE are three different variables)
```

---

## Numbers; Ints and floats

Variables are assigned values with the `=` operator:
```py
name = "Francis"
```

There are many different `type`s of variables, depending on the `type` of data they should hold. For instance, there are two* for numbers
- `int` eg: `1`
- `float` eg: `1.0`

You can create an int variable with the following:
```py
In [1]: year = 2018

In [2]: one = 1

In [3]: two = 2

In [4]: three = one + two

In [5]: print(three) 
Out[5]: 3
```

In some cases you may need a decimal point number, in which case you're creating a float type variable, which we can see in the following example:

```
In [1]: one_third = 1/3

In [2]: two_third = 2/3

In [3]: three_third = one_third + two_third

In [4]: type(one_third)
Out[4]: float

In [5]: type(three_third)
Out[5]: float
```

The `type` keyword above is a function that takes a variable as an argument, and returns to you what type of variable it is. If this doesn't make sense to you now, don't worry. 

What we see is that if floating point arithmetic involved (`1/3 + 2/3`), the variable that you are assigning value to will become a floating point number, instead of an integer.

---

## Strings

Commonly, you'll want to work with text. To do so, you need to know about strings. The string keyword is `string`, and can be one word or a paragraph. Strings are always encapsulated in quotes, either `'`, `"`, or `"""`:

```
In [1]: name = 'hank'

In [2]: king_of_the_hill = "hank hill"

In [3]: dale_gribble_quote = """ last year, I hid Joseph's christmas gift so well
   ...:                          I still haven't found it.
   ...:                          Cutest little puppy...
   ...:                          Or should I say dog? """

In [4]: print(king_of_the_hill, ", ", dale_gribble_quote)

hank hill,   last year, I hid Joseph's christmas gift so well
                         I still haven't found it.
                         Cutest little puppy...
                         Or should I say dog?
```

Our example above is not grammatically correct. To fix this, we should capitalize the `king_of_the_hill` variable:
```
In [5]: print(king_of_the_hill.capitalize())
Out[5]: 'Hank hill'
```

It is common to need to know the length of a string. There is a function in python called `len` that is given an argument, that returns something's length. For strings, this looks like the following:
```py
print(len(king_of_the_hill))
9
```

The string "hank hill" has 8 characters and a space character, for a total of 9 characters.

---
## Lists

Lists are meant to group together data. This could be a list of who's naughty and nice, a list of grocery items to get, or an inventory list. Lists are denoted as comma separated items between brackets, like:
```py
[0, 1, 2, 3, 4, 5]
```
Each item in the list get's an index. That index is simply a number that increments by 1 for each position, so in the example above, the index of 3, is 3.

But wait, what? Shouldn't 3's index be 4, because it's the fourth thing in the list?

In computer science, counting always begins with 0, instead of 1. Because of this, the interpretter will start with the index 0, and then add 1 to the index each time it goes to a new thing in the list.

```py
In [1]: numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

In [2]: numbers[3]
Out[2]: 3

In [3]: numbers[9]
Out[3]: 9

In [4]: numbers[1:3]
Out[4]: [1, 2]

In [5]: numbers[9:]
Out[5]: [9]

In [6]: numbers[8:]
Out[6]: [8, 9]

In [7]: len(numbers)
Out[7]: 10
```

Notice that we can ask for a range of numbers in a few different ways. First, we can set a start and and end point, separated by a `:` in order to ask for a specific range:

```py
In [4]: numbers[1:3]
Out[4]: [1, 2]
```

You can omit one side of the range to start from the beginning, or specific until the end:
```py
In [5]: first_number = numbers[:1]

In [6]: print(first_number)
[0]

In [7]: last_number = numbers[9:]

In [8]: print(last_number)
[9]
```

You may have noticed that this returns a list, which we know because the output is enclosed in []: `[0]` and `[9]`.

If we wanted the number only, we'd have to ask for the index of the item in the list. Since there is only one, we can ask for the `0th` index of the range like so:

```py
In [5]: first_number = numbers[:1]

In [6]: print(first_number[0])
0
```

Now that you know a bit about lists, let's return to our example.

The previous example only capitalized hank's first name, which isn't quite right. To capitalize Hank's full name, we need to split his name into two strings, which can be kept together in a `list` of strings. To do that, we use `string`'s `split()` method. Split takes a character you want to split a `string` up on, and returns a `list` of strings to you. By default, if no character is given, it will split up a string based on spaces. Here's an example:

```
In [5]: king_of_the_hill.split()
Out[5]: ['hank', 'hill']

In [6]: names = king_of_the_hill.split()

In [7]: print(names[0], names[1])
hank hill

In [8]: print(names[0].capitalize(), names[1].capitalize())
Hank Hill
```

Let's say we needed to get Hank's initials. In real life, we just take the first character of each name. We can do the same thing in python. We already have our names in lists, which means our first name is in `names[0]`. If we want to take the first character of Hank, which is `names[0]`, we need the first character of `names[0]`, which is `names[0][0]`:

```py
In [9]: print(names[0][0])
h
```

Knowing what you do now, can you print out both initials on your own? 


## Booleans

One more thing to touch on are boolean values. Booleans, or `bool` as you may see them in python, are a type of variable that can be `True` or `False`, or an expression that evaluates to `True` or `False`.

Here is an example:
```py
In [17]: power_on = True

In [18]: power_off = False

In [19]: power_on == power_off
Out[19]: False
```

The first two examples are pretty straight forward, but what is `==` you might ask? `==` is an operator that evaluates if both sides of it are equal to each other.

In this case, we wrote an expression that essentially asks, is `power_on` equal to `power_off`. Since they have different values, it is false that `power_on` is equal to `power_off`, so the expression evaluates to `False`.

# Challenge

1.0 - Assign your name in lower case to a variable called my_name, then print out `Hi <name>` where <name> is replaced with your name.

1.1 - Capitalize your name and assign that to a different variable.

1.2 - Instead of getting your initials from the first letter of each of your names, try making a cryptic set of initials using the last letter of each name. *hint* `len` can help you

1.3 - Is your first and last name the same? Create a boolean expression that tells you if you have the same name twice.