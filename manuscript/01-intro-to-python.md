# Introduction

[Watch on YouTube](https://www.youtube.com/watch?v=7wuKDDMb3R4)

Python is an open source, cross platform, interpreted language. Since it is open source, you can distribute the language in any commercial software, since it is cross platform, you can write programs on Mac and they'll run exactly the same way on any other platform which Python supports. 

Python has been around and open source pretty much since 1990s, that is the reason there are many third party packages available, it is advisable to check out http://pypi.python.org before you start writing your package, because the chances are that someone already has written a package for that. There are millions of Python programmers out there, and python can be used for doing virtually anything, YouTube, Quora, Hulu are just a few platforms written in Python. We can write command line applications, Linux's bootloader is written in Python, we can write webapps, front end apps and just about everything that you want to build.

Because of its English like syntax, Python makes for an excellent prototyping language. Any program implemented in Python has significantly less number of lines as compared to Java. But because it is a dynamically typed language, it is somewhat difficult to debug the programs written in Python. Thus, we need to be extra careful while writing them.

The reason for that is if you have a 100 line program and you define `i=1` at the first line and by mistake you do `i = '1'` somewhere in between the lines, then it won't complain that `i is an integer you can't assign string to it`, it'll just run the rest of the code assuming the new value of i.

Along with this, what makes Python powerful is the presence of high level data structures like hashmaps, sets, lists.

## Python 2 vs Python3

Python3 is the successor of Python2. In 2020 Python2 will be history. This tutorial is based on Python3 as it is the present and future of the language. Python3 is a backwards incompatible with Python2, but we _can_ write code which can run in both Python2 and Python3.


## Installation

If you are on Windows, please go to https://python.org and download the latest .exe file of Python3. For Android, please download Termux (https://termux.com/help.html). If you are on Mac (brew install python3), if you are on Linux, depending on your distro (apt-get install python3 or yum install python3)

Enough theory.

Let's write programs now. Make sure you have Python installed.

## Example: List all `*.txt` files
We are going to print the list of all files which end with '.txt'.

#### Note:

Python doesn't use semi colons or braces for control flow of the programs, it uses **indentation**. It is mandatory to use indentation if you are using a `for`, `while`, `if` loop.

```python
import os
files = os.listdir()
for file in files:
    if file.endswith(".txt"):
        print(file)
```

Save this in `file.py`. Create 2-3 .txt files. `touch file{1,2,3,4,5}.txt` will create file1.txt, file2.txt till file5.txt, but it works only on Linux or Mac.

After saving `file.py`, execute the program by typing `python3 file.py`

###### Note:
If you get an error saying that python3 wasn't found, then type `python --version`, if it is 3 or above then just type `python file.py`. Because in that case, you have Python3 installed and calling python will call python3.

If everything went well, you should see this as the output:

```
file1.txt
file2.txt
file3.txt
file4.txt
file5.txt
```

This is the beauty of the language, its syntax is very easy to understand and that's the reason the language is very powerful.

If you want to list all the .txt files, you can use the unix utility `ls`, `ls *.txt`. We saw here, how to implement one feature of the `ls` utility in less than 5 lines. This is the power of Python.

## Using glob
There is a stdlib module which allows you to have advanced features which don't so that you don't have to check the extension of the file yourself.

#### Note:

If the third line, `files` doesn't work, then please use `print(files)`. When we use the interpreter, typing in a variable name should typically print the value of the variable, but in some cases it might not, hence we use the print statement, for brevity, we are not going to add a print statement to each line, but you should, if you want to see the output and it isn't working in your case!

```python
>>> import glob
>>> files = glob.glob('*.txt')
>>> files
['file1.txt', 'file2.txt', 'file3.txt', 'file4.txt', 'file5.txt']
 ```

The `glob` method does a regular expression match on the current directory.

As you advance your knowledge in Python, you'll feel the need to use as many stdlib functions as you can so as to reduce code duplication.

Exercise:

1. Write a program to print all `*.csv` files, create multiple `.csv` files first, without using glob.
1. Install ipython using easy_install or pip. Be careful about the version of pip you use.

##### Links

|[Next](02-more-about-language.md) | [Previous](README.md) |  [Index](SUMMARY.md)
| ---- | ---- | ---- |