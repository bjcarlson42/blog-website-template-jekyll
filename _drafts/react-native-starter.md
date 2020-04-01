---
layout: post
title: "Quickstart for your first React Native App"
date: 2020-3-9
categories: ['React Native','App Development']
tags: ['react','app development','ios','android','expo']
comments: true
author: Benjamin Carlson
description: 
meta-description: In this beginner react native tutorial we will learn how to get your first app up and running quickly.
keywords: 'react native, beginner react native'
img: /assets/img/posts/11-react-native-quickstart/react-native.png
alt: React Native
---

## Introduction

React Native is a JavaScript framework for building cross platform mobile apps. In this tutorial I'll show you how to quickly set up a React Native project and run your app on a real phone and an android and ios simulator.

## Expo
In this tutorial, we will be using expo with React Native. Expo acts as a container around the React Native framework that allows us to develop applications quicker and easier. The first thing we need to do is install the Expo CLI command line utility. Open your terminal and run the following command:

<div class="shadow">
{% highlight javascript %}
npm install -g expo-cli
{% endhighlight %}
</div>

Now we can create a new React Native project. I will call my project ExampleProject but you can call it whatever you like.

<div class="shadow">
{% highlight cmd %}
expo init ExampleProject
{% endhighlight %}
</div>

Expo will prompt you with the following message:

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/11-react-native-quickstart/1.png)
</span>

For this tutorial, I will select blank but I encourage you to do some research and select the best option for your propject.

## Running Our App

To start our app we must move into the folder which contains our app and the run the start command. 
<div class="shadow">
{% highlight javascript %}
cd AwesomeProject
npm start
{% endhighlight %}
</div>

### Actual Device

This will open a browser window at your local host. You will notice a barcode in the lower left hand corner. We can scan this in the expo app to access our app on a device. Go to either the Apple App Store or the Google Play Store and search for the expo client. See the image below. 

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/11-react-native-quickstart/2.png)
</span>

Once you download and open the app, you will see an open to "Scan QR Code". Tap this and scan your code. After the JavaScript loads, you should be able to see the app on your device. If you see "Open up App.js to start working on your app!" you have done it correctly.

### XCode and IOS Emulator

Many times, you want to run your app on a simulator for testing and debugging purposes. Lets take a look how to do that. 

Download XCode from the Apple App Store. Note that this is **only availible for Mac users**. Open XCode and navigate to

### Android Studio and Android Emulator

## Conclusion

Now you out and start building the app of your dreams! If you want the exact code I used in this tutorial, it can be found on my [GitHub](https://github.com/bjcarlson42/blog-website-code/tree/master/Quickstart%20React%20Native/ExampleProject){:target="_blank"}.