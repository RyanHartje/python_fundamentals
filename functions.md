# Functions

If you went through the `fruit_query` example, we shared how to use the same code for multiple purposes. By parameterizing what our `fruit_query` was, we could look through our `fruit_list` the same way for apples, bananas, and coconut the same way. 

However, we had to set the `fruit_query` variable by hand. This wouldn't be very helpful to a customer, so let's create a script that takes `fruit_query` as an input from the user. 

There are two ways of doing this, on a prompt, similar to how ipython or python wait for your commands, or as an argument to your script.

## User Input

First, let's look how we can prompt the user to get their `input`.
```
fruit_query = input("What sort of fruit do you want: ")
```

If we run this, we get a prompt. In this example, I've entered "coconut":
```
What sort of fruit do you want: coconut
```

Asking what the user is looking for is one function of our program. For that reason, we can choose to write a function in python to do this tasks for us:

```py
def get_search_from_user():
    fruit_query = input("What sort of fruit are you looking for: ")
    return fruit_query
```

The 3 lines above have created a function, called `get_search_from_user()`. When any other code calls `get_search_for_user()`, it will take the user's input, and return it to whatever is calling it.

In our program, we can call this function like so:

```py
fruit_list = ["apple", "banana", "coconut", "date", "fig", "grape", "plum"]

def get_search_from_user():
    fruit_query = input("What sort of fruit are you looking for: ")
    return fruit_query

fruit_query = get_search_from_user()
for fruit in fruit_list:
    if fruit == fruit_query:
        print(fruit_query, "is in stock")
```

Putting all of this together, we can now ask the user what they're looking for and let them now if we carry it, but we don't really know what our inventory looks like. Let's try creating an inventory from our `dict` type. A `dict`, or dictionary, is a "key value" store, which is to say indices are `string`s that hold an object. That object for our example should be an `int`, but can be any of the other data types you've learned about.

What does that look like? Here's an example of an inventory:
```py
produce_isle = {
    "apple": 10,
    "banana": 40
}
```

Using a dictionary, we can select how many of a `key` we have in the produce_isle. For instance, if we `print(produce_isle["apple"])`, python will print out `10`.

If a customer comes and buys an apple, we have to update our inventory. The way we could do that is:
```py
produce_isle["apple"] -= 1
```
After subtracting 1 from the inventory, the value of `produce_isle["apple"]` is now 9.