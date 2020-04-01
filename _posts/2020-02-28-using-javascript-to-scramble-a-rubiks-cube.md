---
layout: post
title: Using JavaScript To Scramble A Rubik's Cube
date: 2020-02-28
categories: ['JavaScript','Tutorial','Rubiks Cube']
author: Benjamin Carlson
comments: true
description: The Rubiks cube is a popular puzzle in which the goal is to solve a 3x3 cube by matching the colors on each side. In order to solve the cube, you first need to scramble it. There are rules for how to do this but in general
meta-description: In this tutorial, we will use JavaScript arrays and the push opperation to generate a Rubik's cube scramble.
keywords: 'rubiks cube, rubiks cube scramble, beginner javascript, how to solve a rubiks cube'
img: /assets/img/posts/10-rubiks-cube/rubiks-cube.jpg
alt: Rubik's cube
---

## Introduction

The Rubiks cube is a popular puzzle in which the goal is to solve a 3x3 cube by matching the colors on each side. In order to solve the cube, you first need to scramble it. There are rules for how to do this but in general a scramble consists of 20 random moves performend in sequence. In this post I will show you how to implement a scramble in JavaScript.

As always, the complete code for this tutorial can be found on my [GitHub](https://github.com/bjcarlson42/blog-website-code/blob/master/Rubik's%20Cube%20JavaScript%20Scrambler/main.js){:target="_blank"}.

{% include under-p1-ad.html %}

## Rubiks Cube Termonology
Before we start coding, we first need to go over some Rubik's cube termonology.

### Scramble
A **scramble** is a sequence of 20 moves that are performed on a solved cube. These 20 moves are picked randomly from the following set of moves:

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    F, R, U, B, L, D, F2, R2, U2, B2, L2, D2, F', R', U', B', L', D'
    </span>
</pre>

Each of the above letters are rotations of the cube. They stand for:

<span class="ccc">
- F - Front
- R - Right
- U - Upper
- B - Back
- D - Bottom (Down)

A single letter means you rotate that face of the cube clockwise. If there is a " **'** " (single quote) after the letter, you move that face counterclockwise. Likewise, if there is a 2 after the letter, you move that face on the cube twice.

For example, **F2** means you turn the front of the cube clockwise 2 times. **B'** means you rotate the back of the cube counterclockwise one time.

Here is a great visual I found on [ruwix.com](https://ruwix.com/the-rubiks-cube/notation/){:target="_blank"} to help you understand this better.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/10-rubiks-cube/cube-rotations.png) 
</span>

### Example Scrambles

Here are some example scrambles of the cube. This is what we will be writing JavaScript to do for us.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    B2 R F' L2 R B L2 F' D' L2 F L2 R' U B D' F D' U2 R' F2 L U2 F B2
    B' D U2 F' L U' R2 L' D B D' R2 B' F' R2 B2 D2 R B D2 B2 L' U' R L2
    L' R2 U2 F U' B' D2 B D B' F2 U R2 F2 U' L2 B2 R2 L U' B' F' L D R'
    </span>
</pre>

## JavaScript Scrambler

Now let's start writing JavaScript code to scramble the cube for us. 

First, I will declare a function named makeScramble().

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    function makeScramble() {
        // function code here
    }
    </span>
</pre>

Next, we need to declare 2 arrays. The first array will have all of the options I listed above in it. This array will be where we pick the moves from. The second array will be empty. This is where the scramble will go.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    var options = ["F", "R", "U", "B", "L", "D", "F2", "R2", "U2", "B2", "L2", "D2", "F'", "R'", "U'", "B'","L'", "D'"]
    var scramble = []
    </span>
</pre>

Let's step back and think about how we want to approach this next part. We need to randomly select one element in the first array and put it into the second array. We then need to repeat this 19 more times so we have a scramble with 20 elements.

Let's tackle the first part. To randomly select an element in the firrst array, we need can generate a random number from 1 to 18 and then put whatever move at that index into the new scramble. Luckily for us, there is a JavaScript Math library that can help us do this.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max))
    </span>
</pre>


The above code is doing a few things. First, it is declaring a function called getRandomInt. This functions accepts a value max. In our case this value will be 18 because we want to generate a random number from 1 to 18. The inner line of the function is returning that random number for us.

## Push And Pop

Now that we have a way to randomly get an element in the first array, we need to put it into the second array. JavaScript, like other languages, has built in methods for doing commmon tasks. One of these methods is called push. This method works on arrays and allows us to push one item onto the array. In our case we will be pushing one string move onto the arrray. 

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    scramble.push(options[getRandomInt(18)])
    </span>
</pre>

The above code gets a random int from 1 to 18 using the getRandomInt method, gets the corresponding cube rotation at that index in array options, and pushes it onto the new array, scramble. 

If you run this code, only one move will be in the new array. To push 20 moves into the array, we can use a for loop.

<pre class="ir is it iu iv lh li fg">
    <span class="lj jl ap bh lk b by ll lm r ln">
    for (var i = 0; i < 20; i++) {
        scramble.push(options[getRandomInt(18)])
    }
    </span>
</pre>


If you run this code, you will see that the array named scramble now has 20 random moves in it. 

Pop is simmilar to push except instead of adding an element to the array, it removes the last element. We do not use that here but I brought it up because it is the opposite of push and is very useful.

## Conclusion

I hope you enjoyed and learned something from this post! To recap, we went over Basic Rubik's cube notation and termonology, talked about two JavaScript concepts: functions and arrays, and finally looked at one of arrays built in methods, push and pop, and implemented push with a for loop. If you enjoyed please give this post a share and be sure to follow me on social media to be notified of new posts!
