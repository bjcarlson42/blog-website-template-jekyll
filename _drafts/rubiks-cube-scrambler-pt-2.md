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

This may seem like a sijmple fix but it is not quite that easy.  









## Conclusion

After seeing how I solved this problem, can youy solve it better? I am by no means a JavaScript expert so if there is a better solution please let me know in the comments. You can get the code for this tutorial on my [GitHub](){!target="_blank"}
