---
title: "Python Package Management with Pipenv"
pubDatetime: 2020-09-29T18:21:00+07:00
tags:
  - python
  - programming
description: Pipenv is a modern package manager that brings the best package managing practices found in other languages to Python. To understand the benefits of Pipenv, let's start with the reason why we should use a package manager.
---

# Python Package Management with Pipenv

[Pipenv](https://pipenv.pypa.io/) is a modern package manager that brings the best package managing practices found in other languages to Python. To understand the benefits of Pipenv, let's start with the reason why we should use a package manager.

## Why do package management?

It is trivial to work with Python in a few small projects that consist of just one or two programmers. However, as the size of the team and project grows, problems start to arise.

Imagine a group of people working in a single Python project. Alan started the project successfully then transferred it to Bob. Bob checked out the project on his machine and found out it couldn't run on his because Alan used the newer versions of some packages.
Bob tried to update those packages to the same versions used by Alan, but then he found out that the updates broke another part of the project he worked with Carthy.
At this point, Bob's choices were either to fix the dependency issues in Alan's code or Carthy's, neither was easy and without risk of breaking another thing down the line.

Solving this sort of problem is the task of a package manager.

Modern package management consists of 2 main concepts:

1. dependency management

2. environment isolation

Dependency management declares what packages are used by the project, what other packages those packages depend on, and what versions exactly are they using.
It allows everyone working on the same project to use the same version of everything, eliminating the compatibility and functional issues within the code.

Environment isolation is a mechanism that keeps the dependencies for each project completely isolated. It lets one project to use one set of dependencies while another project uses another set of dependencies which could be different versions.

## Python's way of doing package management

One of the main shortcomings of Python is the lack of a built-in package management system.
Unlike other modern languages such as _NodeJS_ or _Go_, Python was not designed with a package management mechanism.
By default, every package is installed manually by a user into what referred to as "Base Environment", where the installed package is seen and used across the whole system.
This behaviour is precisely the reason for the problems mentioned previously.
The use of Base Environment, also known as Global Environment, makes it impossible for projects to independently manage their dependencies.

Python programmers work around this limitation by creating a practice that acts as a "make-shift" package management using `virtualenv` package together with `pip`, Python's default package installer.

The `virtualenv` package allows a project to achieve environment isolation by creating a virtual environment that shadows the Base Environment. In the virtual environment, all code behaves as if packages are installed in the Base Environment, even though they are installed in the project itself.

To achieve dependency management, Python programmers use the so-called `requirements.txt` file as a dependency declaration. This file is created using `pip`, and consumed by `pip` when recreating the project.

### Standard package management practice

The first programmer creates a new project by:

1. create a new virtual environment for the project using `virtualenv`

2. install all dependencies using `pip install`

3. create the requirements file using `pip freeze > requirements.txt` command.

Another programmer can recreate the environment by

1. create a new virtual environment for the project using `virtualenv`

2. install all dependencies using `pip install -r requirements.txt`

## Problems with the current solution

Whilst the standard practice allows Python programmers to achieve the same capabilities given by the package managers in other languages, it contains two major flaws:

1. Virtual environment and dependency management are separated

2. Requirements file is not a real dependency management

### 1. Virtual environment and dependency management are separated

It's all too easy for a Python programmer to be in a wrong environment.
When a programmer created the requirements file, they could mistakenly be in the Base Environment instead of the virtual environment. The requirement file they created thus listed the packages in their Base environments instead which could be very different from the ones used in the project.
Worse still, when a programmer installed the dependencies from the requirements file, they too could be in Base Environment instead of the intended one. The packages listed got installed system-wide and the impacts were left to the worst of their imagination.

The fact that Python virtual environment is not easy to activate does not help the case.
One could easily forget to `source venv/bin/activate` before the `pip install -r requirements.txt` and see their work machine got corrupt in front of their eyes.

### 2. Requirements file is not a real dependency management

What exactly does the `pip freeze > requirements.txt` do? The job of `pip freeze` command is to print the list of all installed packages, along with their version numbers, to the screen.
The `> requirements.txt` is a little command line trick called _redirection_.
It means to write those printed texts into the `requirements.txt` file instead.
Thus, the content of the requirements file is the list of all installed packages in the environment along with their version numbers.

Compared it to the dependency management files of other package managers such as _npm_ or _cargo_ and the differences are clear.

**1. What project does this requirements.txt belong to?**

Dependency file should contain the name of the project, with a version number, so that it is impossible to mix up the dependencies between projects/versions.

**2. No dependency hierarchy**

A programmer installed one package they need. They then created a `requirements.txt` file and found out there were a dozen of packages listed.
Most of the packages listed in the `requirements.txt` are dependencies of other packages in the list.
There is no distinction between the packages depended by the project, installed by the programmer, and the packages depended by those _top-level_ packages.

This is the main point why using `requirements.txt` as a dependency file is a bad idea. When there are conflicting package problems, most of the time the conflicting packages are those dependent packages and not the top-level ones. Because the programmers themselves usually have no idea what packages the one they install depend on, it is not possible to avoid the conflict manually.

Modern package managers usually split the dependencies into these two groups.
The "real" dependencies, manually installed by the programmer, are stored in the main dependency file.
The dependencies of dependencies are resolved during the installation and stored in a separate file, commonly referred to as a _lock file_.

**3. Package versions as a requirement.**

Version numbers in `requirements.txt` are exact. When it says `numpy==1.19.1`, only version 1.19.1 can be installed.
Version numbers in the dependency file should be conditional. For example, it should say whether the project requires exactly version 1.19.1, or include any newer version (>=1.19.1), or any version at all (\*).
This allows the resolver to find a version that fits the project best. The actual version used will be recorded in the lock file.

Most package managers also separate the main dependencies—packages needed by the program logic—and the development dependencies which are used for the development purposes such as testing and debugging.
With this setup, only the relevant packages will be packaged and distributed to the end-users.

## Introducing Pipenv

[Pipenv](https://pipenv.pypa.io/) is a Python package manager which aims to bring into Python a good modern package manager. From the official Pipenv documentation:

> Pipenv is a production-ready tool that aims to bring the best of all packaging worlds to the Python world.

Pipenv is a wrapper on the `virtualenv` and `pip`.
It enables the dependency management and the environment isolation in Python that conforms to the practices followed by package managers of other languages.
Using pipenv solves all the aforementioned issues without the need for any manual process.

## How to use pipenv

### Installation

To install pipenv, follow the instruction on [https://pypi.org/project/pipenv](https://pypi.org/project/pipenv/)

### Create new project and install new package

To create a new project, simply install a package by

```
pipenv install <package name>
```

Pipenv will create the new Pipfile—which is the dependency file—if one does not yet exist.
Otherwise, it will update the Pipfile to add the new package.

Pipenv will then resolve for the dependency list and create the lock file (Pipfile.lock).

### Activate the virtual environment

To activate and use the virtual environment, simply run

```
pipenv shell
```

to enter a new shell which runs inside the virtual environment.
All the installed packages are visible to any programs running within this shell.

Another option is to start the program in the virtual environment directly without entering the shell. Run

```
pipenv run <program name>
```

This command is convenient in many common Python use cases, such as when using Jupyter Notebook. One can simply

```
pipenv run jupyter notebook
```

to start a new notebook inside the virtual environment.

### Deactivate the virtual environment

To deactivate the virtual environment, simply type `exit` in the shell.

## Conclusions

Even though Python traditionally lacks a good package manager, Pipenv finally brings the best features of modern package management to the language such that it is now possible for Python programmers to work efficiently and safely across multiple projects.
