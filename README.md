{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "ff92625c-ae1f-4737-80df-f4d0dbd8c546",
   "metadata": {},
   "source": [
    "# PA1_ECE2112_JAMES, KE\n",
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bd965fd0-dfa2-4fd8-9952-778e227b0b50",
   "metadata": {},
   "source": [
    "### EXPERIMENT 1: INTRODUCTION TO PYTHON PROGRAMMING <br> Submitted By: James, Kim Ezekiel G. | 2ECE-A | 8/29/2026\n",
    "---\n",
    "The content of this repository contains the Programming Assignment 1 for our course \"Advance Computer Programming\" this S.Y. 2025-2026. This project covers three python problems pertaining to Module 1 - Base Computing with Python."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cc3e8c98-f05e-412b-8a5d-fdf5223e73e0",
   "metadata": {},
   "source": [
    "### Objectives\n",
    "---\n",
    "##### At the end of this laboratory activity, the student should be able to:\n",
    "1.  use basic Python functions, operators, and string operations;\n",
    "2.  manipulate strings using indexing, slicing, and built-in string methods;\n",
    "3.  apply sequence unpacking to manipulate the elements of a list; and\n",
    "4.  construct simple Python functions that return a specified result."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ebe6c018-8b23-4617-b029-a88cf12f64bc",
   "metadata": {},
   "source": [
    "### A. WORD ROTATION PROBLEM\n",
    "---\n",
    "Create a function named rotate word() that accepts a non-empty string. Move the first character\n",
    "of the string to the end while keeping all remaining characters in their original order. Preserve the\n",
    "capitalization of every character.\n",
    "\n",
    "**Function format:** rotate word(text)\n",
    "\n",
    "The following function and methods were used in this problem:\n",
    "- `len()` - a string method used to count the total amount of characters\n",
    "\n",
    "  Example:\n",
    "  <br> `w = \"Advanced Programming\"`\n",
    "  <br> `len(w)` --> 20\n",
    "   \n",
    "- `text[index of first element : number of characters : increment]` - a string method to slice given string into parts\n",
    "  - index of first element - the index where the slicing begins\n",
    "  - number of characters - the index where the slicing stops\n",
    "  - increment - the number of index to move between characters\n",
    "\n",
    "  Example:\n",
    "  <br> `w[0:20:3]` --> \"AaePgmn\"\n",
    "\n",
    "- `text[index]` - a string method used to get the value of a specific index\n",
    "\n",
    "  Example:\n",
    "  <br> `w[0]` --> \"A\"\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b2e04193-4f9a-4b12-b78b-6c355353109f",
   "metadata": {},
   "source": [
    "These method is used to create a single function that rotates the word while keeping the remaining characters in order:\n",
    "```python\n",
    "def rotate_word(text):\n",
    "    s = text[1:len(text):1] + text[0]\n",
    "    print(s)\n",
    "\n",
    "text = str(input(\"Enter a word: \"))\n",
    "rotate_word(text)\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "53ce4929-f6e3-4712-8277-134029b61874",
   "metadata": {},
   "source": [
    "### Examples:\n",
    "```python\n",
    "rotate_word(\"python\") --> \"ythonp\"\n",
    "rotate_word(\"logic\") --> \"ogicl\"\n",
    "rotate_word(\"Code\") --> \"odeC\"\n",
    "rotate_word(\"A\") --> \"A\"\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4ffd93be-a7c2-413c-9385-38a2a19fb954",
   "metadata": {},
   "source": [
    "### B. USERNAME BUILDER PROBLEM\n",
    "---\n",
    "Create a function named make username() that accepts two strings: first name and last name. The\n",
    "function must:\n",
    "1. convert all letters to lowercase;\n",
    "2. remove all spaces from the first name;\n",
    "3. remove all spaces from the last name; and\n",
    "4. join the processed first and last names using one period (.).\n",
    "\n",
    "**Function format:** make_username(first_name, last_name)\n",
    "\n",
    "The following function and methods were used in this problem:\n",
    "- `.lower()` - a string method used to change all characters into lowercase\n",
    "\n",
    "  Example:\n",
    "  <br> `w.lower()` --> \"advanced programming\"\n",
    "  \n",
    "- `.replace(\"\",\"\")` - a string method used to change selected character to another character\n",
    "\n",
    "  Example:\n",
    "  <br> `w.replace(\"m\", \"*\")` --> \"Advanced progra**ing\""
   ]
  },
  {
   "cell_type": "markdown",
   "id": "1f75fde6-258a-498f-baad-80f76c99bb0a",
   "metadata": {},
   "source": [
    "These method is used to create a single function that generates a username by combining the first and last name, seperated by a period, in all lowercase characters:\n",
    "```python\n",
    "def make_username(first_name, last_name):\n",
    "    f_n = first_name.lower().replace(\" \" , \"\")\n",
    "    l_n = last_name.lower().replace(\" \" , \"\")\n",
    "    return f_n + \".\" + l_n\n",
    "\n",
    "first_name = str(input(\"Enter your First Name: \"))\n",
    "last_name = str(input(\"Enter your Last Name: \"))\n",
    "print(make_username(first_name,last_name))\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bb365a27-9ea8-4cc0-973b-12f536ff7264",
   "metadata": {
    "jp-MarkdownHeadingCollapsed": true
   },
   "source": [
    "### Examples:\n",
    "```python\n",
    "make_username(\"Ada\", \"Lovelace\") --> \"ada.lovelace\"\n",
    "make_username(\"Alan\", \"Turing\") --> \"alan.turing\"\n",
    "make_username(\"Ana Maria\", \"De Leon\") --> \"anamaria.deleon\"\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "6807ca85-7563-4e41-bf6a-97422c059add",
   "metadata": {},
   "source": [
    "### C. BOOKEND SWAP PROBLEM\n",
    "---\n",
    "Create a function named swap bookends() that accepts a list containing at least two elements. Unpack\n",
    "the list into three variables:\n",
    "- first – the first element;\n",
    "- middle – a list containing everything between the first and last elements; and\n",
    "- last – the last element.\n",
    "\n",
    "Using these variables, return a new list in which the first and last elements have exchanged positions.\n",
    "The elements in middle must remain in their original order. Do not modify the input list.\n",
    "\n",
    "**Function format:** swap bookends(items)\n",
    "\n",
    "The following function and methods were used in this problem:\n",
    "- Extended Sequence Unpacking `first, *middle, last = items`\n",
    "  - first - gets index zero (0)\n",
    "  - *middle - combines all intermediate values\n",
    "  - last - gets the last index (-1)\n",
    "\n",
    "  Example:\n",
    "   <br> `z = [\"1\", \"2\", \"3\", \"4\"]`\n",
    "   <br> `first, *middle, last = z`\n",
    "   <br> first --> \"1\"\n",
    "   <br> *middle --> [\"2\", \"3\"]\n",
    "   <br> last --> \"4\"\n",
    "\n",
    "For manually inputting list items:\n",
    " - `.append()` used to add elements into the list\n",
    "\n",
    "   Example:\n",
    "   <br> `x = [\"apple\", \"banana\"]`\n",
    "   <br> `x.append(\"cherry\")`\n",
    "   <br> `x` --> [\"apple\", \"banana\", \"cherry\"]"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "c9364df4-68e6-4177-a885-d27fa035d364",
   "metadata": {},
   "source": [
    "A.) These method is used to create a single function that interchanges the position of the first and last index while the remaining characters stay the same:\n",
    "```python\n",
    "def swap_bookends(items):\n",
    "    first, *middle, last = items\n",
    "    return [last] + middle + [first]\n",
    "\n",
    "print(swap_bookends([1, 2, 3, 4, 5, 6]))\n",
    "print(swap_bookends([\"red\", \"green\", \"blue\"]))\n",
    "print(swap_bookends([8, 3]))\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "81e08038-e2b5-4ed9-a84c-7670113202ee",
   "metadata": {},
   "source": [
    "### Examples:\n",
    "```python\n",
    "swap_bookends([1, 2, 3, 4, 5, 6]) --> [6, 2, 3, 4, 5, 1]\n",
    "swap_bookends([\"red\", \"green\", \"blue\"]) --> [\"blue\", \"green\", \"red\"]\n",
    "swap_bookends([8, 3]) --> [3, 8]\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "969b5cba-963c-4cf8-bac6-50888a454749",
   "metadata": {},
   "source": [
    "B.) Code that accepts string values and prints as a bookend swap:\n",
    "```python\n",
    "def swap_bookends(items):\n",
    "    first, *middle, last = items\n",
    "    return [last] + middle + [first]\n",
    "\n",
    "num = int(input(\"Enter number of item: \"))\n",
    "k = 0\n",
    "j = []\n",
    "while k < num:\n",
    "    i = input(\"Enter an item: \")\n",
    "    j.append(i)\n",
    "    k += 1\n",
    "\n",
    "print(swap_bookends(j))\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "fd927270-e1aa-4ad5-bbd9-4d8beccac0f4",
   "metadata": {},
   "source": [
    "### Examples:\n",
    "```python\n",
    "Enter number of item: 4\n",
    "Enter an item: Banana\n",
    "Enter an item: Apple\n",
    "Enter an item: Mango\n",
    "Enter an item: Grapes\n",
    "['Grapes', 'Mango', 'Apple', 'Banana']\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "be3a4f2c-02dd-4d4f-aac1-ed48b1201c37",
   "metadata": {},
   "source": [
    "---\n",
    "To view the program for PA1: download [ECE2112_PA1](https://github.com/kathleenhazelhulipas-cloud/ECE2112_Hulipas_PA1/blob/main/PA1.ipynb), open on Jupyter Notebook, and run all cells.\n",
    "\n",
    "## **README file Version History:**\n",
    "- August 28, 2026 - Initial README Content uploaded\n",
    "- August 29, 2026 - Included PA1 Program to the README file"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.14.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
