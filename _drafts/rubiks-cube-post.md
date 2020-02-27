---
layout: post
title: Using JavaScript's Push opperation to code a Rubik's Cube Scrambler
categories: ['JavaScript','Tutorial','Rubiks Cube']
tags: ['rubiks cube','gods number','push','pop']
author: Benjamin Carlson
comments: true
description:
meta-description: In this tutorial, we will use JavaScript arrays and the push opperation to generate a Rubik's cube scramble.
keywords: 'rubiks cube, rubiks cube scramble, beginner javascript, how to solve a rubiks cube'
img: /assets/img/posts/10-rubiks-cube/rubiks-cube.jpg
---

## Introduction

The Rubiks cube is a popular puzzle in which the goal is the solve a 3x3 cube by matching the colors. I have been solving a cube for a few years now and have a 
record of 11 seconds. Recently, I have started making a social media website for cubers. One of the parts of the webiste is a timing page. In order to solve the cube, you need to scramble it. To do this, I used JavaScript to generate 20 move scrambles. In this post I'll go over how I did it.

## Rubiks Cube Termonology
Before we talk about the JavaScript code I need to go over some termonology. The first is a **scramble**. A scramble is a sequence of 20
moves. These 20 moves are picked randomly from the following set of moves:

<div class="shadow">
{% highlight javascript %}
"F", "R", "U", "B", "L", "D", "F2", "R2", "U2", "B2", "L2", "D2", "F'", "R'", "U'", "B'", "L'", "D'"
{% endhighlight %}
</div>

To above moves are rotations of the cube. The letters stand for:

1. F - Front
2. R - Right
3. U - Upper
4. B - Back
5. D - Bottom (Down)

A single letter means you rotate that face of the cube clockwise. If there is a **'** after the letter, you move that face counterclockwise. Likewise, if there is a 2 after the letter, you rotate that letter on the cube twice.

Here is a great visual I found on [ruwix.com](https://ruwix.com/the-rubiks-cube/notation/){:target="_blank"}.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/10-rubiks-cube/cube-rotations.png) 
</span>

## JavaScript Scrambler

Now let's get into the JavaScript. 


First, I will declare a function named makeScramble().

<div class="shadow">
{% highlight javascript %}
function makeScramble() {

}
{% endhighlight %}
</div>

Next, we need to make 2 arrays. The first array will have alll of the options I listed above in it and the next array will be empty. This is where the scramble will go.

<div class="shadow">
{% highlight javascript %}
var options = ["F", "R", "U", "B", "L", "D", "F2", "R2", "U2", "B2", "L2", "D2", "F'", "R'", "U'", "B'", "L'", "D'"]
    var scramble = []
{% endhighlight %}
</div>

Now we have a function that has 2 arrays. One with the options and one empty. Now we need a method for generating the scramble. To do this, I will randomly select 20 elements in the first array and put them into the second array. 

Recall that the scramble needs to be 20 moves and that we have 18 possible choices. 

First, we need a way to randomly get a move from the array options. We can use the Math library to do this.

First, we need a way to randomly get a move from the array options. We can use the Math library to do this:

<div class="shadow">
{% highlight javascript %}
function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max));
}
{% endhighlight %}
</div>

The above code is making a fuction named getRandomInt, which passes a parameter of max. Max is the higherst random number. We will pass this parameter in later. See if you can guess what max is for us. 



## Push And Pop

Above when I said we can use a for loop to "push" 20 random elements onto the arrray, I intentially used the word push. This is because javaScript, like other languages, has built in methods for doin commmon tasks. One of these methods is called push. This method works on arrays and allows us to push one item onto the array. In our case we will be pushing once string move onto the arrray. 

After this we can use a for loop to "push" 20 random elements onto the arrray.

<div class="shadow">
{% highlight javascript %}
for (var i = 0; i < 20; i++) {
        scramble.push(options[getRandomInt(18)])
}
{% endhighlight %}
</div>

## Conclusion

I hope you enjoyed and learned something from this post! To recap, we went over Basic Rubik's cube notation, talked about two JavaScript concepts: functions and arrays, and finally looked at one of arrays built in methods, push and pop, and implemented push with a for loop. If you enjoyed please give this post a share and be sure to follow me on social media to be notified of new posts!