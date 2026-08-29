# PA1_ECE2112_JAMES, KE
---

### EXPERIMENT 1: INTRODUCTION TO PYTHON PROGRAMMING
**Submitted By:** James, Kim Ezekiel G. | 2ECE-A | 8/29/2026

The content of this repository contains the Programming Assignment 1 for our course "Advance Computer Programming" this S.Y. 2025-2026. This project covers three python problems pertaining to Module 1 - Base Computing with Python.

## Objectives
---
##### At the end of this laboratory activity, the student should be able to:
1. use basic Python functions, operators, and string operations;
2. manipulate strings using indexing, slicing, and built-in string methods;
3. apply sequence unpacking to manipulate the elements of a list; and
4. construct simple Python functions that return a specified result.

---

## A. Word Rotation Problem
---
Create a function named `rotate_word()` that accepts a non-empty string. Move the first character of the string to the end while keeping all remaining characters in their original order. Preserve the capitalization of every character.

**Function format:** `rotate_word(text)`

The following function and methods were used in this problem:

- `len()` — a string method used to count the total amount of characters

  Example:
  ```python
  w = "Advanced Programming"
  len(w)  # --> 20
  ```

- `text[index of first element : number of characters : increment]` — a string method to slice a given string into parts
  - index of first element — the index where the slicing begins
  - number of characters — the index where the slicing stops
  - increment — the number of index to move between characters

  Example:
  ```python
  w[0:20:3]  # --> "AaePgmn"
  ```

- `text[index]` — a string method used to get the value of a specific index

  Example:
  ```python
  w[0]  # --> "A"
  ```

These methods are used to create a single function that rotates the word while keeping the remaining characters in order:

```python
def rotate_word(text):
    s = text[1:len(text):1] + text[0]
    print(s)

text = str(input("Enter a word: "))
rotate_word(text)
```

**Examples:**
```python
rotate_word("python")  # --> "ythonp"
rotate_word("logic")   # --> "ogicl"
rotate_word("Code")    # --> "odeC"
rotate_word("A")       # --> "A"
```

---

## B. Username Builder Problem
---
Create a function named `make_username()` that accepts two strings: first name and last name. The function must:
1. convert all letters to lowercase;
2. remove all spaces from the first name;
3. remove all spaces from the last name; and
4. join the processed first and last names using one period (.).

**Function format:** `make_username(first_name, last_name)`

The following function and methods were used in this problem:

- `.lower()` — a string method used to change all characters into lowercase

  Example:
  ```python
  w.lower()  # --> "advanced programming"
  ```

- `.replace("", "")` — a string method used to change a selected character to another character

  Example:
  ```python
  w.replace("m", "*")  # --> "Advanced progra**ing"
  ```

These methods are used to create a single function that generates a username by combining the first and last name, separated by a period, in all lowercase characters:

```python
def make_username(first_name, last_name):
    f_n = first_name.lower().replace(" ", "")
    l_n = last_name.lower().replace(" ", "")
    return f_n + "." + l_n

first_name = str(input("Enter your First Name: "))
last_name = str(input("Enter your Last Name: "))
print(make_username(first_name, last_name))
```

**Examples:**
```python
make_username("Ada", "Lovelace")        # --> "ada.lovelace"
make_username("Alan", "Turing")         # --> "alan.turing"
make_username("Ana Maria", "De Leon")   # --> "anamaria.deleon"
```

---

## C. Bookend Swap Problem
---
Create a function named `swap_bookends()` that accepts a list containing at least two elements. Unpack the list into three variables:
- **first** – the first element;
- **middle** – a list containing everything between the first and last elements; and
- **last** – the last element.

Using these variables, return a new list in which the first and last elements have exchanged positions. The elements in `middle` must remain in their original order. Do not modify the input list.

**Function format:** `swap_bookends(items)`

The following function and methods were used in this problem:

- Extended Sequence Unpacking: `first, *middle, last = items`
  - `first` — gets index zero (0)
  - `*middle` — combines all intermediate values
  - `last` — gets the last index (-1)

  Example:
  ```python
  z = ["1", "2", "3", "4"]
  first, *middle, last = z
  # first  --> "1"
  # middle --> ["2", "3"]
  # last   --> "4"
  ```

For manually inputting list items:
- `.append()` — used to add elements into the list

  Example:
  ```python
  x = ["apple", "banana"]
  x.append("cherry")
  x  # --> ["apple", "banana", "cherry"]
  ```

**A.)** This method is used to create a single function that interchanges the position of the first and last index while the remaining elements stay the same:

```python
def swap_bookends(items):
    first, *middle, last = items
    return [last] + middle + [first]

print(swap_bookends([1, 2, 3, 4, 5, 6]))
print(swap_bookends(["red", "green", "blue"]))
print(swap_bookends([8, 3]))
```

**Examples:**
```python
swap_bookends([1, 2, 3, 4, 5, 6])       # --> [6, 2, 3, 4, 5, 1]
swap_bookends(["red", "green", "blue"]) # --> ["blue", "green", "red"]
swap_bookends([8, 3])                   # --> [3, 8]
```

**B.)** Code that accepts string values and prints as a bookend swap:

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

**Example:**
```
Enter number of item: 4
Enter an item: Banana
Enter an item: Apple
Enter an item: Mango
Enter an item: Grapes
['Grapes', 'Mango', 'Apple', 'Banana']
```

---

To view the program for PA1: download [ECE2112_PA1]([https://github.com/kathleenhazelhulipas-cloud/ECE2112_Hulipas_PA1/blob/main/PA1.ipynb](https://github.com/jameskimezekiel-cloud/ECE2112_PA1.git)), open on Jupyter Notebook, and run all cells.

## README file Version History
- August 28, 2026 - Initial README Content uploaded
- August 29, 2026 - Included PA1 Program to the README file
