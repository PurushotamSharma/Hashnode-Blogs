---
title: "Day 14 Task: Python Data Types and Data Structures for DevOps"
datePublished: Sat Jan 14 2023 15:59:20 GMT+0000 (Coordinated Universal Time)
cuid: clsbgsn5m000209kz6n6vg3xb
slug: day-14-task-python-data-types-and-data-structures-for-devops-dc2e49a4e10d
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290687821/71e24a3a-5aa2-4407-ab41-8b526cad5753.png

---

In this we will discuss about what is Data Types and Data Structures for DevOps.

When we listen about Data Types, then first question in our mind is…

> **What is Data Type?**

Data types are the classification or categorization of data items. It represents the kind of value that tells what operations can be performed on a particular data.

Since everything is an object in Python programming, data types are actually classes and variables are instance (object) of these classes.

There are different types of data types in Python. Some built-in Python data types are:

**Numeric data types**: int,float,complex

**String data type**: str

**Sequence types:** list,tuple,range

**Binary types:** bytes,*bytearray,memoryview*

**Mapping data type**: dict

**Boolean type:** bool

**Set data type:** set,*frozenset*

To check what is the data type of the variable used, we can simply write: `your_variable=100` `type(your_variable)`

1.  **Python Numeric Data Type:**

Python numeric data type is used to hold numeric values like;

a. int — holds signed integers of non-limited length.

b. long- holds long integers(exists in Python 2.x, deprecated in Python 3.x).

c.float- holds floating precision numbers and it’s accurate up to 15 decimal places.

d.complex- holds complex numbers.

**2.Python String Data Type:**

The string is a sequence of characters. Python supports Unicode characters. Generally, strings are represented by either single or double-quotes.

**3\. Python List Data Type:**

The list is a versatile data type exclusive in Python. In a sense, it is the same as the array in C/C++. But the interesting thing about the list in Python is it can simultaneously hold different types of data. Formally list is an ordered sequence of some data written using square brackets(\[\]) and commas(,).

**4\. Python Tuple:**

The tuple is another data type which is a sequence of data similar to a list. But it is immutable. That means data in a tuple is write-protected. Data in a tuple is written using parenthesis and commas.

**5\. Python Dictionary:**

Python Dictionary is an unordered sequence of data of key-value pair form. It is similar to the hash table type. Dictionaries are written within curly braces in the form `key:value`. It is very useful to retrieve data in an optimized way among a large amount of data.

> **What is Data Structures?**

Data Structures are a way of organizing data so that it can be accessed more efficiently depending upon the situation. Data Structures are fundamentals of any programming language around which a program is built. Python helps to learn the fundamental of these data structures in a simpler way as compared to other programming languages.

Lists Python Lists are just like the arrays, declared in other languages which is an ordered collection of data. It is very flexible as the items in a list do not need to be of the same type

Tuple Python Tuple is a collection of Python objects much like a list but Tuples are immutable in nature i.e. the elements in the tuple cannot be added or removed once created. Just like a List, a Tuple can also contain elements of various types.

Dictionary Python dictionary is like hash tables in any other language with the time complexity of O(1). It is an unordered collection of data values, used to store data values like a map, which, unlike other Data Types that hold only a single value as an element, Dictionary holds the key:value pair. Key-value is provided in the dictionary to make it more optimized

### Tasks:-

> **Give the Difference between List, Tuple and set. Do Handson and put screenshots as per your understanding.**

List:

Lists are just like dynamic sized arrays, declared in other languages . Lists need not be homogeneous always which makes it the most powerful tool in [Python](https://www.geeksforgeeks.org/python-programming-language/). The main characteristics of lists are –

The list is a datatype available in Python which can be written as a list of comma-separated values (items) between square brackets.

List are mutable .i.e it can be converted into another data type and can store any data element in it.

List can store any type of element.

In this we first create a blank list and after that we write an script of List in number and after that we also discuss how to write string in list …you may follow the given example…

**Input:**

Input

**Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290674341/4564906f-a8ff-482c-8693-d3f8098764c8.png)

Tuple:

Tuple is a collection of Python objects much like a list. The sequence of values stored in a tuple can be of any type, and they are indexed by integers. Values of a tuple are syntactically separated by ‘commas’. Although it is not necessary, it is more common to define a tuple by closing the sequence of values in parentheses. The main characteristics of tuples are –

*   Tuple is an immutable sequence in python.
*   It cannot be changed or replaced since it is immutable.
*   It is defined under parenthesis().
*   Tuples can store any type of element.

You may explain from given example

**Input**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290675776/67103357-e3cf-4412-9f25-eae881947378.png)

**Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290677146/f0245877-4806-4d7c-983e-83865cf50bcf.png)

Set:

In Python, Set is an unordered collection of data type that is iterable, mutable, and has no duplicate elements. The major advantage of using a set, as opposed to a list, is that it has a highly optimized method for checking whether a specific element is contained in the set. The main characteristics of set are –

*   Sets are an unordered collection of elements or unintended collection of items In python.
*   Here the order in which the elements are added into the set is not fixed, it can change frequently.
*   It is defined under curly braces{}
*   Sets are mutable, however, only immutable objects can be stored in it.

You may understand from given example..

**Input:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290678796/6e41da7c-7d87-412e-bb19-29e9e964f31d.png)

**Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290680138/b202029d-38ff-4554-a6e9-f9afa6382b4b.png)

> **Create below Dictionary and use Dictionary methods to print your favorite tool just by using the keys of the Dictionary.**

fav\_tools =   
{   
  1:"Linux",   
  2:"Git",   
  3:"Docker",   
  4:"Kubernetes",   
  5:"Terraform",   
  6:"Ansible",   
  7:"Chef"  
}

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290681708/215c78c7-7511-4e6d-979d-515ee65f4187.png)

**Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290683238/3ac02106-0a57-408e-8773-c553a55b6c52.png)

> **Create a List of cloud service providers ?eg.**

cloud\_providers = \["AWS","GCP","Azure"\]

Write a program to add `Digital Ocean` to the list of cloud\_providers and sort the list in alphabetical order.

for adding we use append command and for sorting we use sort command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290684793/bcfa583c-937e-4f74-af53-b240668005c7.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290686360/ab5a78f8-1704-4642-bfa3-2e76287c9fa2.png)

Here we use sorted command also for sorting….

Thanks for Reading..

Happy Learning)..