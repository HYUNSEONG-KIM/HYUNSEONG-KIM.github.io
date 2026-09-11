---
layout: post
title: Python Notes
permalink: /docs/Miscellaneous/python-cheat
parent: Resources
nav_order: 4
description: "Practical notes on packaging Python applications, Python–C interfaces, and Tkinter."
last_modified_date: 2026-09-10
---

# Python Notes

These notes collect practical considerations from Python application development: distributing standalone applications, using C extensions, and configuring Tkinter window icons.

## Packaging standalone applications

Sharing Python source code is straightforward when other developers already have a suitable environment. Distributing an application to a broader audience takes more work: users may not have Python installed or be familiar with managing dependencies.

[PyInstaller](https://pyinstaller.org/en/stable/operating-mode.html) bundles an application with a Python interpreter and its dependencies. Users can run the resulting application without installing Python separately. Build and test the bundle on the operating system you intend to support; a bundle built on Windows is not a Linux executable.

### Scientific libraries and bundle size

Libraries such as [NumPy](https://numpy.org/) provide efficient numerical routines, but their compiled components and dependencies can increase the size of a standalone application. The final size depends on the platform, package versions, and files included in the bundle.

For a small utility that uses only a few simple operations, consider whether a large dependency is necessary. For substantial numerical work, a well-tested library is usually worth the additional size. Measure the actual bundle before deciding: package size alone is not a good reason to replace reliable numerical code.

## Python–C interfaces

Implementing computationally intensive code in C can improve performance, but crossing the Python–C boundary has a cost. Repeated calls that perform very little work, or repeatedly convert and copy data, can offset the benefit of a faster implementation.

Profile the application before moving code to C. When a bottleneck warrants a native implementation, consider:

- processing an array or batch of inputs in one call;
- keeping the inner loop in native code;
- avoiding unnecessary conversions and copies;
- choosing data representations that both sides can access efficiently.

The [Python C-extension documentation](https://docs.python.org/3/extending/extending.html) explains how extension functions receive Python objects and return results to the interpreter.

The same caution applies to bit-level optimizations. A low-level technique that is effective in C does not automatically improve Python code. Benchmark the complete operation, including conversion overhead, rather than assuming that a bitwise implementation will be faster than a built-in operation.

## Tkinter window icons on Linux

Tkinter exposes two window-icon methods, `iconbitmap` and `iconphoto`. They are not separate controls for the title bar and taskbar: how an icon is displayed depends on the platform and window manager.

On Windows, `iconbitmap` can accept an ICO file. On X11, bitmap icons use Tk-supported bitmap formats such as XBM; renaming an ICO file does not convert it to XBM.

For a photo-based icon, use `iconphoto` with a Tk photo image. Window-manager support still affects where the icon appears. See the [Tk window-manager documentation](https://www.tcl-lang.org/man/tcl8.6/TkCmd/wm.htm) for platform-specific behavior.

