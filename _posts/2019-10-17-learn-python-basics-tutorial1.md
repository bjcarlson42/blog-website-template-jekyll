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

Welcome back to the second post. Because this is the first tutorial, there is a lot of set up that we need to do before we can even start programming in Python. Without wasting any time, let's dive in! Keep in mind, all of the code in this tutorial can be found on my [GitHub](https://github.com/bjcarlson42){:target="_blank"}, specifically [this](https://github.com/bjcarlson42/blog-website-code){:target="_blank"} repository.

{% include under-p1-ad.html %}

Quick note: If you already have Python installed on your machine and would like to skip the basic terminology and the setup, feel free to skip to the basics section. If you are familiar with the basics of Python, you might want to [skip to the second tutorial](https://benjamincarlson.net/python/programming/tutorial/2019/11/20/learn-python-variables-comments-and-data-types-tutorial-2.html){:target="_blank"}. Let's get learning!

## Terminology

Before we do any programming at all, it is important that we go over some basic terminology. As we get further along I will introduce more terminology but for now, here are the basics to get you started and comfortable.

### IDE

An **IDE** or Integrated Development Environment, is where we will be writing all our code. Although it is technically possible to write code in a basic text editor, like notepad, IDE’s give you a better environment with more tools, plugins, and other helpful tools that allow you to code faster and more efficiently. In this tutorial, we will be using visual studio code, also known as VSCode. I will go into more detail on how to download VS Code and the advantages of using it later in this tutorial. 

The standard Python IDE is called IDLE. We will not be using IDLE in this tutorial series because it
is not programmer friendly. If you would like to learn more about IDLE you can do so [here](https://docs.python.org/3/library/idle.html){:target="_blank"}.

### Programming Language

A **Programming** **Language** is what programmers use to give directions to a computer. Python is an example of a programming language. There are different types of programming languages like [high level and low level languages](https://www.geeksforgeeks.org/difference-between-high-level-and-low-level-languages/){:target="_blank"}. Python is a high level language.

### What is Python

The Programming language **Python** is the language we will be using. This language was created all the way back in the ‘80s but didn't become prominent until the past decade or so. If you want to learn more about Python you can do so [here](https://www.w3schools.com/python/python_intro.asp){:target="_blank"}, otherwise, that is all the terminology we need to get started coding.

## Downloading Python

The first thing we need to do is download and install Python itself. To do this we need to go to 
[Python's official website](https://www.python.org/downloads/){:target="_blank"}.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/1-min.jpg) 
</span>

Click the yellow button that says 'Download Python (version number). For me the version number is 3.7.4. I am using a mac so it says 'mac os x' but if you are using windows it will be the windows download. After that, simply follow the directions to install Python onto your machine.

Now you have Python installed on your machine. Next, we need an IDE to write Python code. This is where Visual Studio Code comes in. Go to [this link](https://code.visualstudio.com/download){:target="_blank"}. 

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/2-min.jpg) 
</span>

Pick your operating system and click download. Your download will start and you can now open the application.

## Python Basics

At this point you should have:

1. A basic understanding of Python, IDE's, and programming languages 
2. Python installed on your machine
3. Visual Studio Code installed on your machine. 

If you had any problems with any of these tasks, feel free to [send me a message](mailto:bjcarlson42@gmail.com){:target="_blank"} and I will get back to you and try to help as soon as possible.

### Writing Python Code

Now we will start actually coding in Python. First open visual studio code. You should see a screen like this.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/3-min.jpg) 
</span>

### Making our First Python File

Now, exit out of the welcome screen. Click file, new file. This will create an untitled file. We need to name the file and tell the compiler that this is a Python file. To do this hit control s, or file, save as, and rename the file program.py. You can save the program anywhere on your machine. I am saving mine on my desktop in a folder called ‘blog’. Normally I would not recommend saving items on your desktop because they can be accidentally deleted but it is fine for our purposes.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/4-min.jpg) 
</span>

You might get some messages saying something along the lines of you don’t have the necessary components to run Python code. Simply hit install and let the IDE do its job and install the necessary Python components.  

### Writing our First Line

At this point you should have a blank Python file. We will start by writing the following line of code:

<div class="shadow">
{% highlight python %}
print(‘Hello World!)
{% endhighlight %}
</div>

You will notice a few things as you type this. One, the VS code highlights words in different colors. Also, VS Code auto completes and suggests words for you. These are 2 powerful things that good IDEs have. It makes it easier to write and read code.

### Running the Python Code

This code is pretty self explanatory. It prints the phrase ‘Hello World!’. This is a pretty standard starter project. You may be wondering, “Okay, how do we run this?” For that we need the terminal. Luckily for us, VS Code has its own integrated terminal. 

Because we already installed Python components in VS Code earlier in the tutorial, the terminal should be there already. If it is not, don't worry. Simply press, control, shift, p, and a search bar will come up.Type “terminal” and you will see, “Terminal: create a new integrated terminal”. Hit enter. 

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/5-min.jpg) 
</span>

### Terminal Commands

Next, we need to navigate to where the file is stored on our computer. This is where terminal commands come into play. If you are on mac, type ls + enter. This will display a list of the folders and files in the current directory.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/6-min.jpg) 
</span>

Since the program is in my desktop folder, I will type “cd Desktop”. This will “change directory” (cd) me into the Desktop folder. If I type 'ls' again, I see the program.py file.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/7-min.jpg) 
</span>

From here, to run the program, we type “Python [program name]. In this case, Python program.py. This will run the program.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/2-python-tutorial-1/8-min.jpg) 
</span>

### Understanding the Output

As you can see, we get the output, “Hello World!”. With that, this first Python tutorial is completed. Be sure to check out the recommended problems below and stay tuned for my next post!

## Practice Problems and Programs

To really test what you learned in this tutorial, I will be giving you practice problems that you can do to test your knowledge and get better with what we learned in that specific tutorial. Completing these exercises will allow you to really understand the material and will enforce the concepts that were just presented.

1. Research basic mac terminal and windows command prompt commands. This will help you navigate the terminal and make you more comfortable running code from the command line.
2. Practice printing other phrases in Python! Maybe print, “My name is [your name]”
3. Familiarize yourself with VS Code and all it has to offer. Knowing the IDE well will help you program better.