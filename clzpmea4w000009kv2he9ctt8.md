---
title: "5 Simple Python Coding Challenges For Beginners"
seoTitle: "5 Simple Python Coding Challenges For Beginners"
datePublished: Sun Aug 11 2024 13:48:20 GMT+0000 (Coordinated Universal Time)
cuid: clzpmea4w000009kv2he9ctt8
slug: 5-simple-python-coding-challenges-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/npxXWgQ33ZQ/upload/b9f5d5e0e0a46bcc21cd42695094c8db.jpeg
tags: software-development, python, data-science, web-development, projects, beginners, software-engineering, coding-challenge, python-beginner, python-projects

---

### 1\. Regular Expressions in Python

Objective: To understand and implement regular expressions in Python to match and extract specific patterns from a given string.

Instructions:

* Use the `re` module in Python to implement regular expressions
    
* Write a function called `extract_phone_numbers(string)` that takes in a string and returns a list of all the phone numbers present in the string in the format (XXX) XXX-XXXX
    
* Write a function called `extract_email_addresses(string)` that takes in a string and returns a list of all the email addresses present in the string.
    
* Write a function called `replace_email_addresses(string, replacement)` that takes in a string and a replacement string and replaces all email addresses in the given string with the replacement string.
    
* Use the provided test cases to test your functions
    

Example:

```javascript
string = "Please contact info@example.com for assistance. Phone: (123) 456-7890 or (111) 222-3333"

print(extract_phone_numbers(string))
# Output: ['(123) 456-7890', '(111) 222-3333']

print(extract_email_addresses(string))
# Output: ['info@example.com']

print(replace_email_addresses(string, "REPLACED"))
# Output: "Please contact REPLACED for assistance. Phone: (123) 456-7890 or (111) 222-3333"
```

Note:

* Phone numbers and email addresses can appear in any order and more than once in the provided string.
    
* Phone numbers may or may not have spaces or dashes in between digits.
    
* Email addresses may or may not have .com, .edu, .gov, etc.
    
* Be mindful of edge cases
    

Hint:

* Phone number regex pattern: "(?\\d{3})?\[-.\\s\]?\\d{3}\[-.\\s\]?\\d{4}"
    
* Email address regex pattern: "\[a-zA-Z0-9.\_%+-\]+@\[a-zA-Z0-9.-\]+.\[a-zA-Z\]{2,}"
    

Submission:

* Create a python file named `coding_challenge.py` and paste your functions and test cases inside.
    
* Zip the python file and submit.
    

### **2\. File Handling - Books Manager**

Create a program that reads in a CSV file containing information about books (title, author, ISBN, and price), and then allows the user to search for books by author, ISBN, or price range.

* Step 1: Create a function that takes a file name as an argument and reads in the contents of the file as a list of dictionaries, with each dictionary representing a book and containing keys for title, author, ISBN, and price.
    
* Step 2: Create a function that takes an author's name as an argument and returns a list of all books written by that author.
    
* Step 3: Create a function that takes an ISBN as an argument and returns the title and price of the book with that ISBN.
    
* Step 4: Create a function that takes a minimum and maximum price as arguments and returns a list of all books within that price range.
    
* Step 5: Use the functions from steps 2-4 in a user interface that allows the user to search for books by author, ISBN, or price range.
    
* Bonus: Add the ability for the user to add new books to the CSV file.
    

### **3\. File Handling and Dictionaries**

Create a program that reads a text file containing a list of names and addresses, and then organizes the information into a dictionary.

1. Begin by creating a function called "parse\_file" that takes in a file path as an argument.
    
2. Use the open() function to open the file and read its contents into a variable called "file\_contents".
    
3. Split the contents of the file by newline characters to create a list of strings, where each string represents a line from the file.
    
4. Iterate through the list of strings and split each line by commas to create a list of lists, where each sublist represents the name and address of a person.
    
5. Create an empty dictionary called "address\_book".
    
6. Iterate through the list of lists and use the first element of each sublist as the key, and the second element as the value, and add them to the "address\_book" dictionary.
    
7. Return the "address\_book" dictionary.
    
8. Test the function by calling it with the file path of a sample file and print the returned dictionary to the console.
    

**Example file contents(you can add more on your own):**  
John Smith, 123 Main Street, Anytown USA  
Jane Doe, 456 Park Avenue, Anytown USA  
Bob Johnson, 789 Elm Street, Anytown USA  
**Example output:**  
{'John Smith': '123 Main Street, Anytown USA', 'Jane Doe': '456 Park Avenue, Anytown USA', 'Bob Johnson': '789 Elm Street, Anytown USA'}

### **4\. Coding Challenge**: Python Lists and Tuples

**Objective:** To test the candidate's knowledge of Python Lists and Tuples, and their ability to manipulate and extract information from them.  
Instructions:

* Create a Python script that performs the following tasks:
    

1. Create a list of integers called `numbers` with the following values: \[1, 2, 3, 4, 5, 6, 7, 8, 9, 10\]
    
2. Create a tuple of strings called `words` with the following values: ("hello", "world", "python", "coding", "bootcamp")
    
3. Use the `numbers` list and the `words` tuple to create a new list called `result` which contains the following values: \[1, "hello", 2, "world", 3, "python", 4, "coding", 5, "bootcamp", 6, 7, 8, 9, 10\]
    
4. Use the `result` list to extract the following sublists:
    

* The sublist containing the values from index 2 to index 5
    
* The sublist containing the last 5 elements of the `result` list
    

1. Use the `result` list to extract the following elements:
    

* The element at index 4
    
* The element at the last index of the `result` list
    

1. Use the `result` list to count the number of occurrences of the string "python"
    
2. Use the `result` list to determine if the integer 3 is present in the list
    
3. Use the `result` list to remove the element at index 4
    
4. Use the `result` list to insert the string "programming" at index 6
    
5. Use the `result` list to sort the list in ascending order
    
6. Use the `result` list to reverse the order of the elements in the list
    
7. Use the `result` list to convert it to a tuple called `final_tuple`
    

* The script should be well-organized and commented on and should include appropriate error handling.
    
* The script should be submitted as a single .py file.
    

Evaluation Criteria:

* The script successfully performs all the tasks outlined in the instructions
    
* The script is well-organized, commented, and includes appropriate error handling
    
* The script demonstrates a clear understanding of Python Lists and Tuples and their manipulation
    

## 5\. "Smart Budget Tracker"

Objective: Create a Python program that tracks a user's expenses and generates reports on their spending habits.

Requirements:

* User should be able to input different expenses with categories (e.g. food, transportation, entertainment, etc.)
    
* User should be able to view their expenses and the total amount spent in each category
    
* User should be able to view their overall spending and the total amount saved
    
* The program should provide a monthly spending report and an annual report
    
* The program should be able to suggest a budget for each category based on the user's expenses
    

Skills required:

* Basic knowledge of Python programming
    
* Understanding of data structures (lists, dictionaries)
    
* Ability to use classes and objects in Python
    
* Understanding of file operations (read and write to a file)
    
* Ability to use built-in Python libraries such as csv and date time.
    

This project will challenge students to apply their knowledge of Python to real-world problems and help them learn how to structure a complex program while implementing various data structures and algorithms.

Good luck!