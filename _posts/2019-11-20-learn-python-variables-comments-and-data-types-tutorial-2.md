---
layout: post
title: "Learn Python Variables, Comments, and Data Types: Tutorial 2"
date: 2019-11-20
categories: ['Python', 'Programming','Tutorial']
tags: ['commenting','variables','data types','escape sequences']
comments: true
author: Benjamin Carlson
description: Welcome back to the second post in the learn Python series! If you haven't read the first post where we go over setting up a Python coding environment on your local machine and write a simple "hello world program"
img: /assets/img/posts/5-python-tutorial-2/python-tutorial-2.jpg
alt: Python Programming
meta-description: 
keywords: 
---

## Introduction

Welcome back to the second post in the learn Python series! If you haven't read the first post where we go over setting up a Python coding environment on your local machine and write a simple "hello world program", you can do so here. Also, remember that you can find all the code for this tutorial at my GitHub. Otherwise, let's jump right into this tutorial.

{% include under-p1-ad.html %}

## Variables

<span style="font-weight: 400;">Variables are elements that store a value. In programming this value may be user input that may change or a non changing value such as pi (3.14). In order to declare a variable in Python we type:</span>

<pre class="theme:github toolbar:2 show-lang:1 lang:python decode:true">x = 10
</pre>

<span style="font-weight: 400;">This stores the value 10 in the variable "x". Now, whenever we write x, the compiler will know see x as 10\. For example let’s add the line print(x).</span>

<pre class="theme:github toolbar:2 show-lang:1 lang:python mark:2 decode:true">x = 10
print(x)</pre>

<span style="font-weight: 400;">When you run this program (remember to run we use the command ‘Python [program name]’ we see the number 10, not x. If we did... </span>

<pre class="theme:github toolbar:2 show-lang:1 lang:python decode:true">print("x")</pre>

... This would print the letter "x". This is because int he second case, we use quotations (" ") to Python that this is a string literal. In the first instance, we neglected the quotations. Lucky for us, Python is smart enough to recognize that x must be a variable and it prints that. <span style="font-weight: 400;">You can even add variables directly in the print statement. For example if we type...</span>

<pre class="theme:github toolbar:2 lang:python decode:true">print(x + 5)</pre>

<span style="font-weight: 400;">...We will see the output "15".</span> <span style="font-weight: 400;">Try it out for yourself!</span>

## Commenting

<span style="font-weight: 400;">If you want to, you can comment out the first print statement. You can do so by putting a "#" in front of the line. This will comment that line of the code out and the compiler will pass over that code when run.</span> <span style="font-weight: 400;">Commenting is helpful in programming for many reasons.</span> <span style="font-weight: 400;">First, it helps with debugging and finding errors in your program. It also allows you to put information at the top of your program such as your name, the date, and a description of the program. This allows anyone looking at your program to understand what the program does, who wrote it, any anything else you might add.</span> <span style="font-weight: 400;">It is a good practice to comment lines of code that are complex to say what they do. Imagine you write 10 lines of code that is complex. If you come back 2 months from now or another developer looks at it, there is a good chance they won't know what that code does. Even if they have a decent understanding of what the code does, it still makes life easier.</span> <span style="font-weight: 400;">For this reason, it is good practice to write comments often in your code. Take a look at an example with good commenting. </span>

<pre class="theme:github toolbar:2 lang:python decode:true">#@author: Benjamin Carlson
#date: 11/6/19
#description: This program adds the variable x to the number 5 and prints the result

x = 10 #Assigned the value 10 to the variable x

#print(x)
print(x + 5) #adds the variable x and 5 and prints the result
</pre>

As you will notice, adding these comments does not change the output of the code. Normally you would not need to comment a simple print statement or variable declaration but for learning purposes, that is how it's done.

## Data Types

<span style="font-weight: 400;">There are many different data types that Python allows us to use. We will cover a majority of the basic ones now. </span>

### Integers

Integers are self explanatory. Earlier in this article, we saw the code "x = 10". 10 is an integer. In Python, there is no limit to how long an integer can be.

<pre class="theme:github toolbar:2 lang:python decode:true ">print(9999999999999999999999)</pre>

To see that this is an integer, we can type this:

<pre class="theme:github toolbar:2 lang:python decode:true ">print(type(10))</pre>

We get a result of <class 'int'>.

### Floating-Point Numbers

Next up are floating-point numbers. Python calls these values type float and are specified by a decimal point in the number.

<pre class="theme:github toolbar:2 lang:python decode:true ">floating_point_number = 3.14
print(type(floating_point_number))
print(type(2.34))</pre>

We see an output of <type 'float'>.

### Strings

Next up are strings. Also called string literals, strings are either surrounded by single or double quotation marks. There is no difference between the two, just personal preference. Like integers, a string may be however long as you wish, even empty, as long as your machine has enough memory.

<pre class="theme:github toolbar:2 lang:python decode:true">my_string = "hi"
my_string2 = 'hello again'
print(type(my_string))
print(type('i am a string'))</pre>

Strings are arrays. As in many other languages, strings are arrays of bytes representing unicode characters. A single character is simply a string with a length of 1. Square brackets can be used to access elements of the string. This is also known as indexing.

<pre class="theme:github toolbar:2 lang:python decode:true">print(my_string2[0]) 
print(my_string2[1])</pre>

Notice how the first letter (or first element of the array) is zero (0) and not one (1). This is known as zero-based numbering. This will be very important when we start working more with arrays.

#### Escape Sequences

An escape sequence is a sequence of characters that does not represent itself when used inside a character or string literal. Instead, it is translated into something else, such as another character or sequence that otherwise can't be represented. In Python, a backslash character in a string indicates that one or more characters that follow it should be treated specially. For example take a look at the code below.

<pre class="theme:github toolbar:2 lang:python decode:true ">print('I don't want to use double quotations.')
print('I don\'t want to use double quotations.')</pre>

In the above example, we can use a backslash in front of the ' in don't. This tells the compiler that this is not a normal single quotation. If you run the code you will find that the first line doesn't work but the second line, with the escape character does. Here is a list of some escape sequences:

*   \' or \'" or \"""
    *   single, double, or triple quote
*   \newline
    *   newline is ignored
*   \\
    *   backslash

For a list of more escape sequences, see the [official Python documentation](https://docs.python.org/2.0/ref/strings.html).

#### Triple Quoted Strings

You can use triple quotes (""") to declare a string. This allows you to put a single (") and double ("") quotations in your string and have it still work. Check out this example.

<pre class="theme:github toolbar:2 lang:python decode:true">print("""Hello. This is a double " quote and this is a single ' quote.""")
# doesn't work - print(""Hello. This is a double " quote and this is a single ' quote."")</pre>

As you can see, the first line runs fine but the second one doesn't. Important note: You must enclose strings with the same number of quotations. you can have strings like this:

<pre class="theme:github toolbar:2 lang:python decode:true ">print("string')
print("""string"")</pre>

If you try to run this, it will fail.

### Boolean

Last up are booleans. A boolean data type will result to true or false. They are used to express truth and have many applications. See the code snippet below to see booleans in action.

<pre class="theme:github toolbar:2 lang:python decode:true">my_boolean = True
print(type(my_boolean))
print(type(False))</pre>

As you can see from the example, a boolean variable can either be set to "True" or "False". However, non-boolean objects can be evaluated in a boolean context and can also be true or false.

## Practice Problems and Programs

Like the last tutorial, here are some practice problems to help you understand the concepts covered in this tutorial better.

1.  Do more research on escape sequences and write a Python program that prints a sentence and uses some of the escape sequences mentioned above or that you found doing your own research.
2.  Add code to the above program that uses each of the data types discussed above. Declare each data type and try to do something interesting with it. Get creative!
3.  Finally, take this same program and add comments. Make sure to add your name, the date, and a short description at the top!

## Conclusion

In this article we covered a lot. We looked at variables, commenting, and some different data types. We will put everything in this article into action in the next post. As always be sure to follow me on [instagram](https://www.instagram.com/compscicentral/?hl=en) and [twitter](https://twitter.com/compscicentral) and share this post if you found it helpful!
