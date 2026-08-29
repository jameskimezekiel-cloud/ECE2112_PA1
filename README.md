# ECE2112_PA1
# PA1_ECE2112_JAMES, KE

**Submitted by:** James, Kim Ezekiel G. | 2ECE-A | 8/29/2026

---

## Experiment 1: Introduction to Python Programming

This experiment introduces the fundamentals of Python programming, including string manipulation, indexing, slicing, string methods, and sequence unpacking. The notebook contains three programming tasks — **Word Rotation, Username Builder, and Bookend Swap** — which demonstrate how basic Python operations can be used to solve simple problems efficiently.

---

## Intended Learning Outcomes

At the end of this laboratory activity, the student should be able to:

1. Use basic Python functions, operators, and string operations.
2. Manipulate strings using indexing, slicing, and built-in string methods.
3. Apply sequence unpacking to manipulate the elements of a list.
4. Construct simple Python functions that return a specified result.

---

## A. Word Rotation Problem

Create a function named `rotate_word()` that accepts a non-empty string. Move the first character of the string to the end while keeping all remaining characters in their original order. Preserve the capitalization of every character.

**Function format:** `rotate_word(text)`

### Solution
```python
def rotate_word(text):
    s = text[1:len(text):1] + text[0]
    print(s)

text = str(input("Enter a word: "))
rotate_word(text)
```

### Examples
```python
rotate_word("python") --> "ythonp"
rotate_word("logic")  --> "ogicl"
rotate_word("Code")   --> "odeC"
rotate_word("A")      --> "A"
```

---

## B. Username Builder Problem

Create a function named `make_username()` that accepts two strings: first name and last name. The function must:

1. Convert all letters to lowercase.
2. Remove all spaces from the first name.
3. Remove all spaces from the last name.
4. Join the processed first and last names using one period (`.`).

**Function format:** `make_username(first_name, last_name)`

### Solution
```python
def make_username(first_name, last_name):
    f_n = first_name.lower().replace(" ", "")
    l_n = last_name.lower().replace(" ", "")
    return f_n + "." + l_n

first_name = str(input("Enter your First Name: "))
last_name = str(input("Enter your Last Name: "))
print(make_username(first_name, last_name))
```

### Examples
```python
make_username("Ada", "Lovelace")        --> "ada.lovelace"
make_username("Alan", "Turing")         --> "alan.turing"
make_username("Ana Maria", "De Leon")   --> "anamaria.deleon"
```

---

## C. Bookend Swap Problem

Create a function named `swap_bookends()` that accepts a list containing at least two elements. Unpack the list into three variables:

- `first` – the first element;
- `middle` – a list containing everything between the first and last elements; and
- `last` – the last element.

Using these variables, return a new list in which the first and last elements have exchanged positions. The elements in `middle` must remain in their original order. Do not modify the input list.

**Function format:** `swap_bookends(items)`

### Solution A — Direct list swap
```python
def swap_bookends(items):
    first, *middle, last = items
    return [last] + middle + [first]

print(swap_bookends([1, 2, 3, 4, 5, 6]))
print(swap_bookends(["red", "green", "blue"]))
print(swap_bookends([8, 3]))
```

### Examples
```python
swap_bookends([1, 2, 3, 4, 5, 6])       --> [6, 2, 3, 4, 5, 1]
swap_bookends(["red", "green", "blue"]) --> ["blue", "green", "red"]
swap_bookends([8, 3])                   --> [3, 8]
```

### Solution B — Interactive user input version
```python
def swap_bookends(items):
    first, *middle, last = items
    return [last] + middle + [first]

num = int(input("Enter number of item: "))
k = 0
j = []
while k < num:
    i = input("Enter an item: ")
    j.append(i)
    k += 1

print(swap_bookends(j))
```

### Example Run
```
Enter number of item: 4
Enter an item: Banana
Enter an item: Apple
Enter an item: Mango
Enter an item: Grapes
['Grapes', 'Mango', 'Apple', 'Banana']
```

---

## Requirements

- Python 3 (ipykernel)
- Jupyter Notebook / JupyterLab

## How to Run

1. Open `PA1_JAMES.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the cells in order from top to bottom.
3. Follow the input prompts for each problem where applicable.

---

**Course:** ECE2112
**Section:** 2ECE-A
**Date:** 8/29/202
