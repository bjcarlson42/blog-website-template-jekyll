---
layout: post
title: "HTML and CSS Dropdown Menu (Better than Bootstrap)"
date: 2019-11-27
categories: ['Tutorial','Programming','Web Development']
comments: true
author: Benjamin Carlson
description: A navigation bar is used in every website. They may look different across each site due to branding, but the underlying code is very similar. In this tutorial I will go over how to make a drop-down navigation
img: /assets/img/posts/6-html-css-dropdown-menu/html-and-css-nav-bar.jpg
alt: Javascript book
meta-description: 'In this tutorial we will go over how to make a dropdown menu with html, css, and javascript that 
will work better than bootstrap.'
keywords: 'bootstrap navigation, javascript nav, bootstrap cdn, website navigation'
---

## Introduction
A navigation bar is used in every website. They may look different across each site due to branding, but the underlying code is very similar. In this tutorial I will go over how to make a drop-down navigation bar in pure HTML and CSS. I will assume that you know basic HTML and CSS syntax and structure. As always, the code for this tutorial can be found on my [GitHub](https://github.com/bjcarlson42){:target="_blank"}.

{% include under-p1-ad.html %}

## Step 1: Adding HTML

The first thing you need to do is open up your favorite IDE. I will be using visual studio code. Next, create a file named 'index.html'. Inside this file we will write the following code:

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    {% highlight html %}
        <html>
            <head>
                <title>Navigation Bar</title>
            </head>
        <body>
            <nav>
            <ul>
                <li><a href="#">Logo</a></li>
                <li><a href="#">Item 1</a></li>
                <li><a href="#">Item 2</a></li>
                <li><a href="#">Item 3</a></li>
            </ul>
            </nav>
        </body>
        </html>
{% endhighlight %}
    </span>
</pre>

The html, head, and body tags are all standard HTML tags that are used in every HTML document. The important stuff is inside the 'nav' tag. As you can see, we have created an unordered list inside the 'nav' tag. If we run this on our local server we see what we would expect; a clickable list of 4 items. Since I am using visual studio code, to run this I will right click on the file and click 'open with live server'.

## Step 2: Adding CSS

This is all the HTML we need until we add drop-downs later in the tutorial. Now we move on to CSS. We must first remove all the margin and padding from the page. Add the following CSS inside a style tag.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    * {
        padding: 0;
        margin: 0;
    }
    </span>
</pre>

The style tag can be placed anywhere inside the body tag on the index.html page or you can link to an external html page if you would rather do that. Next, we will start to style the actual navigation bar. We will add the following line of code declaring that we want the height of the navigation bar to be 100px and that the background should be light-gray.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav {
        height: 100px;
        background-color: lightgray;
    }
    </span>
</pre>

Next, we need to style the list items. To do this, we can use hierarchy to reach the li tags.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li {
       list-style: none;
       display: inline-block;
       float: left;
       line-height: 100px;
       position: relative;
    }
    </span>
</pre>

Now with the li tags styled, we can move on to the next item in the hierarchy, the a tag. This is the actual text.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li a {
        display: block;
        text-decoration: none;
        font-family: arial;
        color: #fff;
        padding: 0 20px;
    }
    </span>
</pre>

One important thing to notice is the 'display: block;'. This will come in handy when the user wants to click on one of the items. The block element allows the user to  just have to click on the area around and including the word rather than the word itself. 

Now the navigation bar is starting to look like one you would see on an actual website. Lets make it even better by making it change color when the user hovers over a particular item.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li a:hover {
        color: white;
        background-color: gray;
    }
    </span>
</pre>

The nav bar is now finished. You can play around with it by switching the colors around, changing the font size, or even by making it do something other than a color change on hover.

## Step 3: Adding Drop-down Navigation

The above navigation bar works but what if you wanted a dropdown? You can do that by adding nested unordered lists and styling those lists by using the same css hierarchy structure as before. Add the marked lines of code below.
c
<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    {% highlight html %}
    <nav>
    <ul>
        <li><a href="#">Logo</a></li>
        <li><a href="#">Item 1</a></li>
        <li><a href="#">Item 2</a>
            <ul>
                <li><a href="#">Item 2 dropdown 1</a></li>
                <li><a href="#">Item 2 dropdown 2</a></li>
                <li><a href="#">Item 2 dropdown 3</a></li>
            </ul>
        </li>
        <li><a href="#">Item 3</a>
            <ul>
                <li><a href="#">Item 3 dropdown 1</a></li>
            </ul>
        </li>
        <li><a href="#">Item 4</a></li>
    </ul>
    </nav>
{% endhighlight %}
    </span>
</pre>

The nav bar will look a little weird because it is using styling from css that was meant for a non dropdown menu. Let's fix this by adding the following CSS.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li ul {
        display: block;
        position: absolute;
        background-color: lightgray;
        padding: 0;
        border-bottom-left-radius: 4px;
        border-bottom-right-radius: 4px;
        display: none;
    }

    nav ul li:hover ul {
        display: block;
    }

    nav ul li a:hover {
        color: white;
        background-color: gray;
    }
    </span>
</pre>


This fixes it but the dropdown links are cut off. We need to make the width bigger.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li ul li {
        width: 180px;
    }
    </span>
</pre>

The nav bar dropdown looks a bit rigid. Lets make it look a little nicer by adding a subtle touch.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    nav ul li ul {
            display: block;
            position: absolute;
            background-color: lightgray;
            padding: 0;
            border-bottom-left-radius: 4px;
            border-bottom-right-radius: 4px;
            display: none;
    }
    </span>
</pre>

These two lines of code add a little curve to the bottom left and right corners. And with that we have the final product.

## Wrapping Up

If you followed this tutorial successfully, you should have a completed drop-down navigation bar! Remember, you can find the completed source code on my [GitHub](https://github.com/bjcarlson42/blog-website-code/blob/master/Drop%20Down%20Navigation%20Bar/index.html){:target="_blank"}. Happy coding!