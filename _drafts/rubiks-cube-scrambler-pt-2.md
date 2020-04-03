---
layout: post
title: " "
date: 
categories: ['']
comments: true
author: Benjamin Carlson
description: 
keywords: ''
img: 
alt:
---

## Introduction

This is a follow up post to the post I wrote just the other day on scrambling a rubiks cube with JavaScript. If you haven't read that post yet be sure to check it out [here]("TODO"){!target="_blank"} and then come back to this post. In this post, I will improve the scrambler. To do that, we will unfortuantl have to rewrite most of the code, but the fundemental design and thinking stays the same. Let's get too it!

## What's a Scramble

You should already know what a Rubik's cube scramble is (assuming you read the first post), however, here is a quick refesher just in case. A scramble is a sequence of 20 moves that are performed on a solved cube. These 20 moves are picked randomly from the following set of moves:

TODO insert moves image here

Here are some sample scrambles:

TODO insert sample scrambles.

## The Problem

The problem with the last post was that our scrambling algorithm doesn't account for the possibility of 2 of the same move being next to each other. For example, we might get a scrambles that look like these:

TODO insert scrambles with issues

At first these scrambles might not look like an issue, escpecially to non cubers, however having two d moves next to each other or having a b2 and a b' next to each other doesnt make sense. Take the first example with two d moves next to each other. That is the same as saying d2. So essentially that scramble is now 19 moves, not 20. This is a problem, ecspecially when we get 3 or 4 moves like this in our scrambles. Now our scrambles could be 15 moves instead of 20!

## The Fix

This may seem like a simple fix but it is not quite that easy. We need to think about solving this in a different way than we did last time. Let's take a look at the options again. 

TODO insert options img

We can see that there are 6 different moves by letter. There is F, R, U, B, L, and D. Furthermore, there are 3 differnt moves for each of these. single clockwise move (F), double move (F2), and single counter clockwise move (F'). These make up our 18 possible moves (6 x 3 = 18). 

## Coding the Solution in JavaScript

We can now approach this problem using this knowledge. Let's start off by giving each of the 6 possibilities a number 0 through 6 and store them in an arrray. We will call this array numOptions.

```javascript
var numOptions = [0,1,2,3,4,5]
```

Now, we can randomly add these numbers to another array nammed scramble untill we have 20 random letters in the array. Remember, a Rubik's cube scramble is 20 moves. 

```javascript
var scramble = [] // initialize to empty

for (var i = 0; i < 20; i++ ) {
  scramble.push(numOptions[getRandomint(6)])
}

// random int code from last tutorial
function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max)) // returns up to max - 1
}
```

Now, we have an array of 20 randomo numbers from 0 to 5! Now, some of you are thinking, we still have the same problem as last time. If that's you, you're absolutely right. We still have the possibility for a two 3's to be next to each other. However, since we are using numbers, it is super easy to loop through the array and check this. We can now write code to generate an array of 20 numbers, loop though and check to see if any of the same number are next to each other, and if they are, generate the array again. 

```javascript
var bad = true

while (bad) {
        scramble = []
        for (var i = 0; i < length; i++) {
            scramble.push(numOptions[getRandomInt(6)])
        }
        // check if moves directly next to each other involve the same letter
        for (var i = 0; i < length - 1; i++) {
            if (scramble[i] == scramble[i + 1]) {
                bad = true
                break
            } else {
                bad = false
            }
        }
    }
```

To briefly explain the code above: we declare a boolean bad and set it to true. The next block of code we already saw. Next, we check the scramble by looping through the array. It compares the value at index 0 to the value at index 1. If they are not equal it moves on. If they are equal it quits and regenerates. 

You can run this code in your browser and see for yourself! 

1. Right click and click inspect element.
2. Copy the follwoing code:

```javascript
function makeScramble() {
    var numOptions = [0, 1, 2, 3, 4, 5] // 0 = F, 1 = R, 2 = U, 3 = B, 4 = L, 5 = D
    var scramble = []
    var bad = true

    while (bad) {
        scramble = []
        for (var i = 0; i < 20; i++) {
            scramble.push(numOptions[getRandomInt(6)])
        }
        // check if moves directly next to each other involve the same letter
        for (var i = 0; i < length - 1; i++) {
            if (scramble[i] == scramble[i + 1]) {
                bad = true
                break
            } else {
                bad = false
            }
        }
    }
```

3. Paste it into the console

TODO insert image of console

4. Click enter
5. Copy and paste the following line: 

```javascript
makeScramble()
```

You should see something similar to this: 

TODO add image of scramble output

Your scramble will be different than mine becasue it's random!

## Adding the Letters

The final step is to substitute letters for the numbers. We will do this by declaring an array of all possible options and then writing a switch statement to inside a for loop to substitute the right letters for each number.

Ex. If the number is 3, we will place either a B, B2, or B' (randomly of course)

```javascript
var options = ["F", "F2", "F'", "R", "R2", "R'", "U", "U2", "U'", "B", "B2", "B'", "L", "L2", "L'", "D", "D2", "D'"]
var move

for (var i = 0; i < 20; i++) {
        switch (scramble[i]) {
            case 0:
                move = options[getRandomInt(3)] // 0,1,2
                scrambleMoves.push(move)
                break
            case 1:
                move = options[getRandomIntBetween(3, 6)] // 3,4,5
                scrambleMoves.push(move)
                break
            case 2:
                move = options[getRandomIntBetween(6, 9)] // 6,7,8
                scrambleMoves.push(move)
                break
            case 3:
                move = options[getRandomIntBetween(9, 12)] // 9,10,11
                scrambleMoves.push(move)
                break
            case 4:
                move = options[getRandomIntBetween(12, 15)] // 12,13,14
                scrambleMoves.push(move)
                break
            case 5:
                move = options[getRandomIntBetween(15, 18)] // 15,16,17
                scrambleMoves.push(move)
                break
        }
    }
    
function getRandomIntBetween(min, max) { // return a number from min to max - 1. Ex. 3, 9 returns 3 - 8
    return Math.floor(Math.random() * (max - min) + min)
}
```

You will notice we have another function that gets a random number between 2 numbers. 

Here is the final code:

```javascript
// Make scramble function
function makeScramble() {
    var options = ["F", "F2", "F'", "R", "R2", "R'", "U", "U2", "U'", "B", "B2", "B'", "L", "L2", "L'", "D", "D2", "D'"]
    var numOptions = [0, 1, 2, 3, 4, 5] // 0 = F, 1 = R, 2 = U, 3 = B, 4 = L, 5 = D
    var scramble = []
    var scrambleMoves = []
    var bad = true

    while (bad) {
        scramble = []
        for (var i = 0; i < 20; i++) {
            scramble.push(numOptions[getRandomInt(6)])
        }
        // check if moves directly next to each other involve the same letter
        for (var i = 0; i < length - 1; i++) {
            if (scramble[i] == scramble[i + 1]) {
                bad = true
                break
            } else {
                bad = false
            }
        }
    }
    console.log(scramble)
    // switch numbers to letters
    var move
    for (var i = 0; i < 20; i++) {
        switch (scramble[i]) {
            case 0:
                move = options[getRandomInt(3)] // 0,1,2
                scrambleMoves.push(move)
                break
            case 1:
                move = options[getRandomIntBetween(3, 6)] // 3,4,5
                scrambleMoves.push(move)
                break
            case 2:
                move = options[getRandomIntBetween(6, 9)] // 6,7,8
                scrambleMoves.push(move)
                break
            case 3:
                move = options[getRandomIntBetween(9, 12)] // 9,10,11
                scrambleMoves.push(move)
                break
            case 4:
                move = options[getRandomIntBetween(12, 15)] // 12,13,14
                scrambleMoves.push(move)
                break
            case 5:
                move = options[getRandomIntBetween(15, 18)] // 15,16,17
                scrambleMoves.push(move)
                break
        }
    }
    scrambleMoves = scrambleMoves.join(" ") // final scramble ready to be displayed
    console.log(scrambleMoves)
    scrambleElement.innerHTML = scrambleMoves
}

function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max)) // returns up to max - 1
}

function getRandomIntBetween(min, max) { // return a number from min to max - 1. Ex. 3, 9 returns 3 - 8
    return Math.floor(Math.random() * (max - min) + min)
}
```

## Conclusion

After seeing how I solved this problem, can youy solve it better? I am by no means a JavaScript expert so if there is a better solution please let me know in the comments. You can get the code for this tutorial on my [GitHub](){!target="_blank"}
