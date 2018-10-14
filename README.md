Python Fundamentals
===

This guide is meant to be a concise but complete guide to your first python program. If you feel you can improve this guide, pull requests are welcome!

## Getting Started 
---

### Install Python

Before we get started, make sure that you have a working python runtime. 

You should be able to open your terminal, command prompt, or powershell window, and run the python interpretter like so:

```
▶ python
Python 3.7.0 (default, Jul 23 2018, 20:22:55)
[Clang 9.1.0 (clang-902.0.39.2)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

This will allow us to run commands in python on the shell.

#### Windows

Install python (3.7) on your machine to follow along in the examples below. The link to the current stable version is found here:
https://www.python.org/ftp/python/3.7.0/python-3.7.0-webinstall.exe

Once installed, you should be able to run the following from Command Prompt or Powershell (which you can find in the start bar menu):
```
python --version
Python 3.7.0
```

#### Mac

Python 2.7 is installed by default on Mac OS. This guide assumes you are running python 3.7, as python 2 will stop receiving support in 2020. 

There are two ways to install python3 on Mac OS, you can [download the installer](https://www.python.org/ftp/python/3.7.0/python-3.7.0-macosx10.9.pkg), or you can [install homebrew](https://brew.sh/) and run:
```
brew install python3
```

After, you should be able to run `python3` and `pip3` from a terminal window (found in Utilities).

*Note*: The following examples contain references to `python` or `pip`, as is common on systems that only have one version of python installed. As a Mac user, you will need to instead run `python3` or `pip3`.  

#### Linux

Your operating system's package manager should have access to a suitable version of python3, however here are links to 

#### iPython 

I highly recommend installing `ipython` and running these examples one by one, and experimenting with the language. ipython, or interactive python, is a pretty terminal that extends the IDLE interpretter, and allows you to tab complete and other nice features. Since python is scripted, you can write it and run it as you go! To install ipython, you can open a terminal or command prompt and run:
```
pip3 install ipython
```

If you get errors because you do not have pip installed, you might try:
```
easy_install pip
pip install ipython
```

You should now be able to run the ipython interpretter like so:
```
▶ ipython
Python 3.7.0 (default, Jul 23 2018, 20:22:55)
Type 'copyright', 'credits' or 'license' for more information
IPython 7.0.1 -- An enhanced Interactive Python. Type '?' for help.

In [1]:
```
For best results, please try entering and playing with the examples as you read through them. You will see output from my personal ipython shells in the examples to follow.

---


# Contents

The contents are listed in order of relevance to the next lesson. Feel free to jump in where you're comfortable.

- [Variables](variables.md)
  - integers (`int`s)
  - floats (`float`s)
  - strings (`string`s)
  - booleans (`bool`s)
  - objects (`object`s)
- [Logic and Control Flow](logic.md)
  - if statements
  - for loops
- [Functions](functions.md)
  - What is a function
  - Defining your first function
- [Classes](classes.md)
- [Lab](lab.md)


# Continued Learning

This example may have given you some exposure to python, but as next steps, I'd highly recommend the following:
- Sign up for [CodeCademy's course on Python](https://www.codecademy.com/courses/learn-python/lessons/python-syntax/exercises/print-statements?action=resume_content_item), and challenge a friend.
- Sign up for Exercism.io, and start on the python track to solve python programming challenges to help get you comfortable. Form a team, it's more fun with friends.
- Find a python project that interests you, and look at it's code on Github. Also look at open "Pull Requests" to see what patching code looks like in practice.
- Try to find an issue in this project that interests you, and see if you can solve it. It can be helpful to find a similar closed Pull Request where similar work has been done, and borrow from that if you understand it. Be sure to ask questions and get help if needed. 
- If you are feel you are proficient enough to showcase your python skills, try [LeetCode](http://leetcode.com), as a more challenging platform designed for Software Engineers to showcase their talent.