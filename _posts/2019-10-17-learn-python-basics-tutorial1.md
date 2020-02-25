---
layout: post
title: "Learn Python Basics: Tutorial 1"
date: 2019-10-17
categories: ['Programming', 'Python', 'Tutorial']
tags: ['basics','ide','practice','programming language']
comments: true
author: Benjamin Carlson
description: Welcome back to the second post. Because this is the first tutorial, there is a lot of set up that we need to do before we can even start programming in Python
meta-description: In this second beginner python tutorial, we will learn python environments, basic syntax, VSCode and much more.
keywords: 'learn python, python tutorial, beginner python'
img: /assets/img/posts/2-python-tutorial-1/learn-python-basics-tutorial1.png
alt: Python Programming Logo
---

## Introduction

Welcome back to the second post. Because this is the first tutorial, there is a lot of set up that we need to do before we can even start programming in Python. Without wasting any time, let's dive in! Keep in mind, all of the code in this tutorial can be found on my GitHub, specifically this repository.

{% include under-p1-ad.html %}

Quick note: If you already have Python installed on your machine and would like to skip the basic terminology and the setup, feel free to skip to the basics section. If you are familiar with the basics of Python, you might want to [skip to the second tutorial](https://benjamincarlson.net/python/programming/tutorial/2019/11/20/learn-python-variables-comments-and-data-types-tutorial-2.html). Let's get learning!

## Terminology

Before we do any programming at all, it is important that we go over some basic terminology. As we get further along I will introduce more terminology but for now, here are the basics to get you started and comfortable.

### IDE

An **IDE** >or Integrated Development Environment, is where we will be writing all our code. Although it is technically possible to write code in a basic text editor, like notepad, IDE’s give you a better environment with more tools, plugins, and other helpful tools that allow you to code faster and more efficiently. In this tutorial, we will be using visual studio code, also known as VSCode. I will go into more detail on how to download VS Code and the advantages of using it later in this tutorial. 

The standard Python IDE is called IDLE. IDLE is not the best IDE and we will not be using it in this tutorial series because VS Code is 100 times better. If you would like to learn more about IDLE you can do so [here](https://docs.python.org/3/library/idle.html).

### Programming Language

A **Programming** **Language** is what programmers use to give directions to a computer. Python is an example of a programming language. There are different types of programming languages like [high level and low level languages](https://www.geeksforgeeks.org/difference-between-high-level-and-low-level-languages/). Python is a high level language.

### What is Python

The Programming language **Python** is the language we will be using. This language was created all the way back in the ‘80s but didn't become prominent until the past decade or so. If you want to learn more about Python you can do so [here](https://www.w3schools.com/python/python_intro.asp), otherwise, that is all the terminology we need to get started coding.

## Downloading Python

The first thing we need to do is download and install Python itself. To do this we need to go to [Python.org](https://www.python.org/downloads/).
<span class="blog-post-imbedded-img">
![Python.org]({{ site.url }}/assets/img/posts/2-python-tutorial-1/1.png) 
</span>
Click the yellow button that says 'Download Python [version number]'. For me the version number is 3.7.4.<span style="font-weight: 400;"> I am using a mac so it says mac os x but if you are using windows it will be the windows download. </span> <span style="font-weight: 400;">After that simply follow the directions to install Python on your machine. </span> <span style="font-weight: 400;">Now you have Python installed on your machine but you need somewhere to write Python code. This is where Visual Studio Code comes in. Go to</span> [<span style="font-weight: 400;">https://code.visualstudio.com/download</span>](https://code.visualstudio.com/download)<span style="font-weight: 400;">. </span> <span style="font-weight: 400;">![VS Code](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/2-1-300x205.png)</span> <span style="font-weight: 400;">Pick your operating system and click</span> _<span style="font-weight: 400;">download</span>_<span style="font-weight: 400;">. Your download will start and you can now open the application.

## Python Basics

<span style="font-weight: 400;">At this point you should have the following completed. A basic understanding of Python, IDE, and programming language. Python installed on your machine and Visual Studio Code installed on your machine. If you had any problems with any of these tasks, feel free to</span> [<span style="font-weight: 400;">contact me</span>](https://computersciencecentral.dev/contact/) <span style="font-weight: 400;">and I will get back to you and try to help as soon as possible.</span>

### Writing Python Code

<span style="font-weight: 400;">Now we will start actually coding in Python. First open visual studio code. You should see a screen like this. </span> [![VS Code startup](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/3-1-300x188.png)](https://computersciencecentral.dev/wp-content/uploads/2019/10/3.png)

### Making our First Python File

<span style="font-weight: 400;">Now, exit out of the welcome screen. Click file, new file. This will create an untitled file. We need to name the file and tell the compiler that this is a Python file. To do this hit control s, or file, save as, and rename the file program.py. You can save the program anywhere on your machine. I am saving mine on my desktop in a folder called ‘blog’. Normally I would not recommend saving items on your desktop because they can be accidentally deleted but it is fine for now.</span> ![Making program.py](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/4-1-300x169.png) <span style="font-weight: 400;">You might get some messages saying something along the lines of you don’t have the necessary components to run Python code. Simply hit install and let the IDE do its job and install the necessary Python components.</span>  

### Writing our First Line

<span style="font-weight: 400;">At this point you should have a blank Python file. We will start by writing the following line of code:</span>

<pre class="theme:github toolbar:2 lang:default highlight:0 decode:true" title="First line of python code">print(‘Hello World!’)
</pre>

<span style="font-weight: 400;">You will notice a few things as you type this. One, the VS code highlights words in different colors. Also, VS Code auto completes and suggests words for you. These are 2 powerful things that good IDEs have. It makes it easier to write and read code.</span>

### Running the Python Code

<span style="font-weight: 400;">This code is pretty self explanatory. It prints the phrase ‘Hello World!’. This is a pretty standard starter project. You may be wondering, “Okay, how do we run this?” For that we need the terminal. Luckily for us, VS Code has its own integrated terminal. Because we already installed Python components in VS Code earlier in the tutorial, the terminal should be there already. If it is not, don't worry. Simply press, control, shift, p, and a search bar will come up.Type “terminal” and you will see, “Terminal: create a new integrated terminal”. Hit enter. </span> ![Integrated Terminal in VS Code](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/6-1-300x94.png)

### Terminal Commands

<span style="font-weight: 400;">Next, we need to navigate to where the file is stored on our computer. This is where terminal commands come into play. If you are on mac, type ls + enter. This will display a list of the folders and files in the current directory.</span> <span style="font-weight: 400;">![](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/7-1-300x48.png)</span> <span style="font-weight: 400;">Since the program is in my desktop folder, I will type “cd Desktop”. This will </span><span style="font-weight: 400;"></span> <span style="font-weight: 400;">“change directory” (cd) me into the Desktop folder. If I type ls again, I see the program.py file.</span> ![Change Directory](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/8-1-300x51.png) <span style="font-weight: 400;">From here, to run the program, we type “Python [program name]. In this case, Python program.py. This will run the program.</span> ![Running Program](https://www.benjamincarlson.net/blog/wp-content/uploads/2019/10/9-1-300x45.png)

### Understanding the Output

<span style="font-weight: 400;">As you can see, we get the output, “Hello World!” </span> With that, this first <span style="font-weight: 400;">Python</span> tutorial is completed. Be sure to check out the recommended problems below and stay tuned for my next post!

## Practice Problems and Programs

<span style="font-weight: 400;">To really test what you learned in this tutorial, I will be giving you practice problems that you can do to test your knowledge and get better with what we learned in that specific tutorial. Completing these exercises will allow you to really understand the material and will enforce the concepts that were just presented. </span>

1.  <span style="font-weight: 400;">Research basic mac terminal and windows command prompt commands. This will help you navigate the terminal and make you more comfortable running code from the command line. </span>
2.  <span style="font-weight: 400;">Practice printing other phrases in Python! Maybe print, “My name is [your name]”</span>
3.  <span style="font-weight: 400;">Familiarize yourself with VS Code and all it has to offer. Knowing the IDE well will help you program better.  </span>
