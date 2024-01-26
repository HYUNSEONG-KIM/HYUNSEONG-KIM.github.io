---
layout: post
title: python cheat sheet
permalink: /docs/Miscellaneous/python-cheat
parent: Miscellaneous
---

# Python cheat sheet

This document is a memos about programming issue in pythons.


## Standalone packaging
 
There are no more words needed for python's fast reproduction and redistribution of source codes to developers and researchers. However, the *executable* package distribution is not the main scope of python. Unlikely many compile languages(C/C++, Rust, ... ), the execution of python source code requires python environment and dependent packages. Have you ever seen any program requiring a compiler and libraries that the developer pawns off on users? Of course, some scientific programs or mass-size products, like games, demand some prerequisites but the most of dependencies are automatically installed. Moreover, for general users, constructing these environments is usually a merciless demand. 

Pyinstaller is one solution of python distibution. There are other solutions about distibution of executable program.

See details of usage in official [documents](https://pyinstaller.org/en/stable/)

This section describes some essential infos for fast referring.

### Beaware using Libraries( especially scientific library )

Some mathematical routines, like matrix operations, are requiring additional modules or you have to implement yourself for your project.
If the project requires stable, precise, and high speed operations and there are tones of types of operations, it is vital to use addtional libraries, considering fast impelmentation. However, those libraries commonly consist of large number of functionalities. It makes their size huge for including them in executable file with *pyinstaller*. 

One example of those libraries is [numpy](numpy.org/). It is commonly included in many scientific applications and provides us various $n$-dimensional array modulation routines. However, if you only requires little matrix opeation, maybe 2 to 4?, including *numpy* to your project squanders lots of storage resources. At least, it requires 200*MB* in Windows, and a half a *GB* in Linux system.


## C-Python interface

In some case, you would feel desire to write a core algorithm with C to accelerate 
overall speed of the implemeted routines.
However, if the function is frequently called in python evironment to follow or to update 
the internal variables, you **may not** write such function with C.
The transformation cost from python to C and reverse direction requires huge resources
much more than you expected at first. 
To achieve a better performance, the implmented routine must minize data transfer during the execution.
That means, C implemented part of the program could account for almost all parts of the routines.

Good examples are numpy and pandas, they create, manipulate the datatypes(ndarray, dataframe) 
inside C routines and never exchange the internal variables during the process.

Same argument also hold for binary operation.
It is true that binary tricks with IEEE standard number system 
could provide better performance. 
However, Python is not a C and `int(python) != int(C)`. 
Standard string class routines would show much faster performance than
your bitwise implementation in most cases.


## Tkinter

### Icon issue in linux

tkinter provides two icon setting, `iconbitmap` and `iconphoto`. The `iconbitmap` is a icon on program windows where the left top side of windows. The `iconphoto` is a task bar indication icon. 
In Linux operating system, tkinter does not support `.ico` file format for `iconbitmap`. It only supports `.xbm` file format. It is meaningless to change the name of file. They are totally different file format. *Gimp* support `xbm` export of image.
However, practically, `iconbitmap` routines are not work properly in many situation if gui application is on Linux system.

