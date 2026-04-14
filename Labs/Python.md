Labs shown from the intro level to the most advanced

## Environment & Tools
* **AWS Cloud9 IDE:** Used as the primary cloud-based code editor.
* **AWS Terminal:** Used for executing Python scripts and debugging output.
* **Python 3:** The core language used for all exercises.

## Conclusion
Successful completion of this lab confirms a solid understanding of how Python organizes data. These skills are directly applicable to handling JSON payloads, managing user records, and scripting automation tasks in enterprise

---

Lab 1

## AWS Cloud9 (Hello World)

Completed an introductory Python lab using **AWS Cloud9**, focusing on environment setup and basic program execution.

---

### Tasks Completed

<ul>
<li>Launched and accessed the <b>AWS Cloud9 IDE</b></li>
<li>Verified the working directory using <code>pwd</code></li>
<li>Checked installed Python versions (<code>python</code>, <code>python2</code>, <code>python3</code>)</li>
<li>Created and saved a Python file (<code>hello-world.py</code>)</li>
<li>Executed a basic Python program</li>
</ul>

---

### Sample Code

```python
print("Hello, World")

```

<img width="1737" height="700" alt="image" src="https://github.com/user-attachments/assets/77dda40c-ccb5-4de8-b563-11ca63b27e5b" />

---

Lab 2

## Working with Numeric Data Types

Explored Python numeric data types and basic operations using **AWS Cloud9**.

---

## What I Did

<ul>
<li>Used the <b>Python shell</b> to perform basic arithmetic:
  <ul>
    <li>Addition, subtraction, multiplication, division</li>
  </ul>
</li>
<li>Created and ran a Python file (<code>numeric-data.py</code>)</li>
<li>Worked with variables and printed outputs using <code>print()</code></li>
<li>Used built-in functions:
  <ul>
    <li><code>type()</code> to identify data types</li>
    <li><code>str()</code> to convert values to strings</li>
  </ul>
</li>
</ul>

---

## Data Types Practiced

- <b>int</b> → whole numbers (e.g. 1)  
- <b>float</b> → decimal numbers (e.g. 3.14)  
- <b>complex</b> → imaginary numbers (e.g. 5j)  
- <b>bool</b> → True / False values  

---

## Example Code

```python
myValue = 3.14
print(myValue)
print(type(myValue))
```

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/d5b933a4-6c49-4fc7-a847-aba3d9ed2247" />

<img width="1850" height="737" alt="image" src="https://github.com/user-attachments/assets/3999667f-d37d-4d48-a0a7-b674d3d8b0e9" />

<img width="1689" height="721" alt="image" src="https://github.com/user-attachments/assets/982e3c67-4b67-435a-a846-31bd0657f6d8" />

<img width="1865" height="953" alt="image" src="https://github.com/user-attachments/assets/2b4411b9-258e-4bd3-a90c-53ad79527b24" />

<img width="1799" height="881" alt="image" src="https://github.com/user-attachments/assets/f3d2dce1-5112-4782-9d2e-77d34074c1cf" />

---

Lab 3

# Working with the String Data Type

## Summary
Completed a hands-on Python lab in AWS Cloud9 focused on **string data handling**, **user interaction**, and **output formatting**. Built and executed a Python script demonstrating core text-processing capabilities relevant to real-world applications.

---

## Work Completed

- Set up and used a **cloud-based development environment (AWS Cloud9)**
- Created and managed a Python script (`.py` file) in a Linux environment
- Implemented and tested multiple string operations within a single program

---

## Key Implementations

### String Handling
- Defined and printed string variables  
- Verified data types using `type()`  
- Converted data types using `str()` for safe string operations

<img width="925" height="368" alt="image" src="https://github.com/user-attachments/assets/9a5f9631-b29a-4bd4-a733-d963742f0f12" />


### String Concatenation
- Combined multiple string variables using the `+` operator  
- Demonstrated practical differences between numeric and string operations  

<img width="1856" height="579" alt="image" src="https://github.com/user-attachments/assets/4b108d96-8109-445d-a6dd-c49878f39855" />


### User Input Processing
- Captured dynamic user input using `input()`  
- Stored and reused user-provided values within the program

<img width="1794" height="627" alt="image" src="https://github.com/user-attachments/assets/18897cb2-5325-4e7b-a250-694eb5b3c53f" />


### Output Formatting
- Built structured output using `print()`  
- Applied `format()` with placeholders `{}` for clean, readable messages  

---

## Example Functionality
The final script:
- Prompts the user for their name, favorite color, and favorite animal  
- Processes the input  
- Outputs a formatted, human-readable sentence  

**Example Output:**

<img width="1919" height="1008" alt="image" src="https://github.com/user-attachments/assets/2588128c-7710-40ed-a6c5-ac3c9c29bd99" />

---

## Skills Demonstrated

- Python fundamentals (strings, variables, functions)  
- Command-line interaction (CLI input/output)  
- Clean and dynamic output formatting  
- Basic scripting in a cloud environment  

---

## Tools & Environment

- AWS Cloud9 IDE  
- Python 3  
- Linux-based file system and terminal  

---

## Relevance

This work demonstrates practical ability to:
- Build simple interactive applications  
- Handle user input and text data efficiently  
- Create readable outputs for end users  

Applicable to:
- Automation scripts  
- Backend logic development  
- CRM/HCM customization scenarios

---

Lab 4

# Python Data Collections (Lists, Tuples, Dictionaries)

## Overview
This lab involved configuring a development environment within **AWS Cloud9** to practice the foundational "building blocks" of Python programming. Mastering these collections is essential for managing data structures in cloud-based applications and automated workflows.

## Objectives
* Use the **List** data type for mutable collections.
* Use the **Tuple** data type for immutable (unchangeable) data.
* Use the **Dictionary** data type for organized key-value mapping.

## Technical Tasks
### 1. Working with Lists (Mutable)
* Created a fruit list and practiced accessing items via **index positions** (starting at 0).
* Demonstrated the **mutability** of lists by updating specific entries (e.g., changing "cherry" to "orange").

### 2. Working with Tuples (Immutable)
* Defined a tuple using parentheses `()` to store data that must remain constant throughout a program's lifecycle.
* Verified that while data can be accessed by position, it cannot be modified, ensuring **data integrity**.

### 3. Working with Dictionaries (Key-Value Pairs)
* Built a dictionary to map specific names to values.
* Practiced accessing data by **name (key)** rather than number, which mimics how modern APIs and databases (like CRM/HCM systems) retrieve information.

<img width="917" height="234" alt="image" src="https://github.com/user-attachments/assets/2b9e6e34-73c0-49f8-9b49-d042a401b07d" />

<img width="1745" height="528" alt="image" src="https://github.com/user-attachments/assets/be898ba4-857f-4b38-88b4-793a3fa03656" />

<img width="1837" height="865" alt="image" src="https://github.com/user-attachments/assets/f139c83e-6240-4a3a-82e5-122d5152acfb" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8862e36f-c68e-4379-8af8-9dfbc2098cd7" />


