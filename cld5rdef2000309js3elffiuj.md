---
title: "Python 101: Dictionaries in Python Free Tutorial"
seoTitle: "Python 101: Dictionaries in Python Free Tutorial"
datePublished: Sat Jan 21 2023 09:38:42 GMT+0000 (Coordinated Universal Time)
cuid: cld5rdef2000309js3elffiuj
slug: python-101-dictionaries-in-python-free-tutorial
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674105280093/eae25915-415d-4e17-b4e2-82d7e83268f9.png
tags: programming-blogs, python, python3, programming-languages, python-beginner

---

Dictionaries are a powerful data structure in Python that allows you to store and retrieve data in a key-value format.

First, let's create a dictionary. We can do this using curly braces {} and separating each key-value pair with a colon. For example, let's create a dictionary that stores the name of a few cities and their corresponding population.

```python
cities = {
    "New York": 8175133,
    "Los Angeles": 3792621,
    "Chicago": 2695598
}
```

Now that we have our dictionary, let's take a look at how to access the data inside of it. We can access the value of a specific key by using the key in square brackets, like so:

```python
print(cities["New York"])  # Output: 8175133
```

We can also use the `get()` method to access the value of a key. This method is useful because it will return `None` if the key is not found, rather than raising an error:

```python
print(cities.get("Houston"))  # Output: None
```

We can also add new key-value pairs to our dictionary using the assignment operator (=). For example, let's add a new city to our dictionary:

```python
cities["Houston"] = 2296193
print(cities)
# Output: {'New York': 8175133, 'Los Angeles': 3792621, 'Chicago': 2695598, 'Houston': 2296193}
```

We can also remove key-value pairs from our dictionary using the `del` keyword. For example, let's remove the city of Chicago from our dictionary:

```python
del cities["Chicago"]
print(cities)
# Output: {'New York': 8175133, 'Los Angeles': 3792621, 'Houston': 2296193}
```

There are a few methods that are useful when working with dictionaries. For example, we can use the `keys()` method to get a list of all the keys in a dictionary, and the `values()` method to get a list of all the values.

```python
print(cities.keys())  # Output: ['New York', 'Los Angeles', 'Houston']
print(cities.values())  # Output: [8175133, 3792621, 2296193]
```

You can also use the `update()` method to add multiple key-value pairs at once. For example:

```python
states_and_capitals = {}
new_states_and_capitals = {"Hawaii": "Honolulu", "Alaska": "Juneau"}
states_and_capitals.update(new_states_and_capitals)

state_and_capitals = {
    "Hawaii": "Honolulu",
    "Alaska": "Juneau"
}
```

To check if a key exists in a dictionary, you can use the `in` keyword. For example:

```python
if "Texas" in states_and_capitals:
    print("Texas is in the dictionary")
else:
    print("Texas is not in the dictionary")
```

You can also use the `keys()` method to get a list of all the keys in a dictionary, and the `values()` method to get a list of all the values. For example:

```python
print(states_and_capitals.keys()) # Output: ["California", "Texas", "Florida", "New York", "Georgia", "Hawaii", "Alaska"]
print(states_and_capitals.values()) # Output: ["Sacramento", "Austin", "Tallahassee", "Albany", "Atlanta", "Honolulu", "Juneau"]
```

Finally, you can use the `items()` method to get a list of all the key-value pairs in a dictionary. For example:

```python
print(states_and_capitals.items()) # Output: [("California", "Sacramento"), ("Texas", "Austin"), ("Florida", "Tallahassee"), ("New York", "Albany"), ("Georgia", "Atlanta"), ("Hawaii", "Honolulu"), ("Alaska", "Juneau")]
```

In this tutorial, we've covered the basics of dictionaries in Python. You should now have a good understanding of how to create, access, and manipulate dictionaries. They are very useful to store key-value pairs.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!