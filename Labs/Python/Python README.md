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

---

Lab 5

# Working with Mixed-Type Lists in Python

## Lab Overview
Python offers unique flexibility by allowing multiple data types to coexist within a single collection. In this lab, I developed a script to create, traverse, and analyze a mixed-type list within the **AWS Cloud9** environment.

## Objectives
* **Numeric Data Types:** Integrated both Integers (`int`) and Floating-point numbers (`float`).
* **String Data Types:** Handled text data and numeric strings.
* **List Data Type:** Built and managed a collection containing diverse data objects.
* **Control Flow:** Utilized a `for` loop to automate the traversal of the collection.
* **Output & Introspection:** Used the `print()` and `type()` functions to audit data at runtime.

## Technical Execution
* **Multi-Type Integration:** Created a list containing `int`, `float`, `bool`, and `str`. 
* **Dynamic Analysis:** Implemented a loop that programmatically identified the data type of each element. This mimics real-world scenarios where an application must validate incoming data from different sources (like a CRM or HCM database).
* **String Formatting:** Used the `.format()` method to create clean, readable logs of the data processing.

## Results
The script successfully identified and printed the type for every item, proving that Python can handle complex, non-uniform datasets efficiently. This is a foundational skill for building robust automation scripts in cloud environments.

## Environment
* **Platform:** AWS Cloud9 (Linux-based IDE)
* **Language:** Python 3

<img width="1841" height="774" alt="image" src="https://github.com/user-attachments/assets/488ace99-d340-400c-b9de-b2c9ecde0ee8" />

---

Lab 6

# Processing Composite Data Types from CSV

## Lab Overview
In modern data engineering, information is rarely simple. This lab focused on managing **composite data types**—complex structures where strings are nested in dictionaries, which are then nested within lists. Using **AWS Cloud9**, I developed a Python script to import an external CSV inventory file and transform it into a highly structured, in-memory data collection.

## Objectives
* **File I/O:** Used the `import csv` module to read and parse external tabular data.
* **Complex Data Nesting:** Implemented a "list of dictionaries" structure to manage a vehicle inventory.
* **Memory Management:** Utilized `copy.deepcopy` to ensure data integrity when creating new object instances in RAM.
* **Control Flow:** Applied `if/else` statements and nested `for` loops to handle headers and item properties.
* **Modern String Formatting:** Leveraged **f-strings** for cleaner, more efficient console output.

## Technical Execution
* **Schema Definition:** Created a `myVehicle` dictionary to act as a blueprint for car data (VIN, make, model, etc.).
* **Data Transformation:** * Opened `car_fleet.csv` using the `with open` context manager (best practice for resource management).
    * Iterated through the file rows, skipping the header and mapping each column to the blueprint.
    * Dynamically appended each vehicle "object" to a master `myInventoryList`.
* **Deep Copy Logic:** Addressed a critical programming concept by using `copy.deepcopy()`. This ensured that each vehicle in the list occupied its own unique memory space rather than just pointing to a shared reference.

## Key Learning Outcomes
* **Data Pipelines:** Successfully built a mini-pipeline that moves data from a "Storage" state (CSV) to an "Active" state (Python Objects).
* **Code Reusability:** Designed a process that can handle any number of rows from a source file, a core requirement for automation in CRM and HCM systems.

## Environment & Tools
* **AWS Cloud9:** Cloud-based IDE and Linux terminal.
* **Python 3:** Using `csv` and `copy` standard libraries.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42626dc7-5f39-49b8-856f-e47094742773" />

---

Lab 7

# Implementing Logic with Python Conditionals

## Lab Overview
This lab focused on creating dynamic "decision-making" paths within a program using conditional statements. By using comparative operators and proper Python indentation, I developed a script that simulates a customer service interaction for a shipping center.

## Objectives
* **`if` Statement:** Executed code blocks based on specific user input (e.g., shipping a package).
* **`else` Statement:** Provided fallback responses when the primary condition was not met, ensuring a complete user experience.
* **`elif` (Else-If) Statement:** Handled multiple branching paths to offer additional services like stamps, envelopes, or copies.
* **`input()` Function:** Captured real-time user data to drive program logic.
* **Comparative Operators:** Utilized `==` to evaluate equality between user responses and defined triggers.

## Technical Execution
* **Logic Branching:** Developed a multi-layered conditional structure where the program evaluates conditions sequentially until a match is found.
* **Input Handling:** Integrated nested inputs within specific branches (e.g., asking for the number of copies only if the "copy" path is selected).
* **Indentation Mastery:** Applied Python’s strict spacing rules to define logic blocks, replacing the brackets used in other programming languages.

## Key Learning Outcomes
* **Mutually Exclusive Paths:** Understood that once a condition is met (`True`), the program skips the remaining `elif` and `else` blocks, optimizing execution speed.
* **Predictable UX:** Learned how to account for "negative" or unexpected inputs using the `else` statement to prevent the program from exiting silently.
* **Project Relevance:** This logic is the foundation for building automated workflows in **Salesforce** or **Workday**, such as triggering specific email alerts only when certain criteria (like a high-priority case or a specific region) are met.

## Environment & Tools
* **Platform:** AWS Cloud9
* **Language:** Python 3

<img width="1852" height="944" alt="image" src="https://github.com/user-attachments/assets/e5e48190-d3f6-4c6f-87ae-a6f75fd1cd13" />

<img width="1760" height="645" alt="image" src="https://github.com/user-attachments/assets/aa91e1b8-cc1e-4d47-850b-438a748150e1" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/588f70d1-fd51-454c-b7c1-92abeb1b263f" />

---

Lab 8

# Automating Tasks with Python Loops

## Lab Overview
This lab introduced the core concepts of iteration in Python, specifically focusing on how to repeat segments of code to automate tasks. By developing a "Guess the Number" game and a counting script, I mastered the practical application of both condition-based and sequence-based loops.

## Objectives
* **`while` Loop:** Implemented a loop that continues executing as long as a specific condition remains true (ideal for unpredictable user interactions).
* **`for` Loop:** Utilized a loop to iterate over a fixed range of numbers (ideal for processing known sequences).
* **`import` Statement:** Integrated the `random` module to add dynamic, non-deterministic behavior to a program.
* **Range Function:** Mastered the `range()` function, including its non-inclusive nature at the stop parameter.
* **Pseudocoding:** Applied the technique of writing program logic in plain language to plan code structure before implementation.

## Technical Execution
* **Game Logic:** Developed a loop driven by a boolean flag (`isGuessRight`), which handles user input, type conversion (`int()`), and comparative logic to determine the win state.
* **Iteration Control:** Configured a `for` loop to automate counting from 0 to 10 by defining a specific numerical range.
* **In-Memory Logic:** Practiced "indented logic blocks," ensuring Python understands which commands belong inside the loop's execution path.



## Key Learning Outcomes
* **Condition vs. Sequence:** Learned when to use a `while` loop for tasks with unknown duration (like waiting for a correct guess) versus a `for` loop for predictable sequences.
* **External Modules:** Gained experience using the `random.randint()` function, a skill directly transferable to generating unique IDs or tokens in CRM systems.
* **Documentation Habits:** Implemented code comments using `#` to ensure maintainability and team collaboration—a critical skill for professional project management in IT.

## Environment & Tools
* **Platform:** AWS Cloud9
* **Language:** Python 3
* **Libraries:** `random`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb1446ac-618e-4606-aada-96f57fe4d22d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9a2d272a-3f83-4478-8c51-bb2e59642eed" />


---

Lab 9

# AWS Lab: Version Control and Project Management with GitHub

## Lab Overview
In modern software development and cloud operations, version control is the backbone of collaboration. This lab focused on initializing a professional development workflow by migrating local AWS Cloud9 projects to a remote repository on **GitHub**. This process ensures code durability, version tracking, and accessibility for global teams.

## Objectives
* **Version Control Integration:** Transitioned local Python development projects to a centralized Git-based platform.
* **Repository Architecture:** Created and configured a remote repository, including the initialization of a `README.md` for project documentation.
* **Asset Migration:** Managed the extraction and bulk upload of Python scripts, ensuring directory integrity was maintained during the move.
* **Cloning & Distribution:** Mastered the process of "cloning" and downloading repositories to synchronize work between cloud IDEs and local machines.

## Technical Skills Demonstrated
* **Git Workflow:** Familiarity with the lifecycle of a code project, from local creation in **AWS Cloud9** to remote hosting on **GitHub**.
* **Documentation (IaC Mindset):** Utilized Markdown to provide context for technical assets, mirroring the "Infrastructure as Code" approach where documentation lives alongside the code.
* **File Management:** Efficiently handled compressed project files and directory structures to avoid data loss during migration.

## Key Learning Outcomes
* **Collaborative Readiness:** Gained the ability to work within a modern DevOps environment where GitHub acts as the "Single Source of Truth."
* **Project Portability:** Developed a workflow that allows for seamless switching between different development environments without losing progress.
* **Professional Portfolio:** Successfully established a public presence to showcase technical growth in **Python** and **Cloud Infrastructure**, a critical step for consultancy roles in **Salesforce** and **Workday**.

## Environment & Tools
* **AWS Cloud9:** Primary development environment.
* **GitHub:** Cloud-based Git hosting service.
* **Git:** Version control software for tracking changes in source code.







