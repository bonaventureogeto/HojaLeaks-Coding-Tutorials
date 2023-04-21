---
title: "Python File Handling 101: A New Guide to Reading and Writing Files"
seoTitle: "Python File Handling 101: A New Guide to Reading and Writing Files"
datePublished: Tue Jan 17 2023 05:53:13 GMT+0000 (Coordinated Universal Time)
cuid: clcztk0su000508mj2lry9d6l
slug: python-file-handling-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1673934519527/16272fd0-fc1a-4fa0-a846-985b0a3f83b8.jpeg
tags: programming-blogs, python, python3, beginners, python-beginner

---

### Introduction

Files are an essential part of any programming language, and Python is no exception. Python provides several built-in functions and modules for working with files, including the `open()` function and the `os` module.

### Opening a File

The first step in working with a file in Python is to open it. The `open()` function is used to open a file, and it takes two arguments: the file name and the mode. The mode can be one of the following:

* `'r'`: opens the file in read mode (default)
    
* `'w'`: opens the file in write mode
    
* `'a'`: opens the file in append mode
    
* `'x'`: opens the file in exclusive creation mode
    
* `'b'`: opens the file in binary mode
    
* `'t'`: opens the file in text mode (default)
    

For example, to open a file named `example.txt` in read mode, you would use the following code:

```python
f = open('example.txt', 'r')
```

### Reading a File

Once a file is opened, you can read its contents using the `read()` method. The `read()` method takes one optional argument, the number of bytes to read. For example, to read the entire contents of a file, you would use the following code:

```python
f = open('example.txt', 'r')
contents = f.read()
print(contents)
```

You can also read a file line by line using the `readline()` method. This method reads the next line of the file, and it can be used in a loop to read the entire file. For example:

```python
f = open('example.txt', 'r')
for line in f:
    print(line)
```

### Writing to a File

To write to a file, you must open it in write mode or append mode. The `write()` method is used to write to a file. For example:

```python
f = open('example.txt', 'w')
f.write('Hello, World!')
```

You can also use the `writelines()` method to write multiple lines to a file. This method takes a list of strings as an argument. For example:

```python
lines = ['Hello, World!', 'This is a test.']
f = open('example.txt', 'w')
f.writelines(lines)
```

### Closing a File

After you are done working with a file, it is important to close it. The `close()` method is used to close a file. For example:

```python
f = open('example.txt', 'r')
contents = f.read()
f.close()
```

You can also use the `with` statement to automatically close a file when you are done with it. For example:

```python
with open('example.txt', 'r') as f:
    contents = f.read()
```

### Conclusion

In this tutorial, we have covered the basics of file handling in Python. We have learned how to open, read, write, and close files using the `open()` function, the \`read()`,` write()`, and` close()`methods, as well as the`with\` statement. Remember to always close a file after you are done working with it to ensure that any changes are saved and to prevent data loss. You should also be aware of the different file modes and their uses, such as reading and writing to a file. With these concepts, you will be able to handle files in Python with ease.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!