---
layout: post
title: "Understanding The World Wide Web"
date: 2019-11-10
categories: ['Programming','Web Development']
tags: ['domain name servers','html','http','tim berners lee','uri','url','world wide web']
comments: true
author: Benjamin Carlson
description: The World Wide Web, or more commonly known as the internet, is a way for billions of people to connect, share, and interact online. Most people think they understand how the internet works but it’s more complex than you may think
img: /assets/img/posts/4-understanding-the-world-wide-web/understanding-the-world-wide-web.jpg
alt: World Wide Web
meta-description: 'The internet and the World Wide Web were invented a while ago by Sir Tim Berners-Lee and are one of the most important inventions of all time.'
keywords: 'World Wide Web, internet, what is the internet, Sir Tim Berners-Lee'

---

## Introduction
The World Wide Web, or more commonly known as the internet, is a way for billions of people to connect, share, and interact online. Most people think they understand how the internet works but it’s more complex than you may think. How and why did the world wide web start? What’s an IP address or a DNS? What’s a hyperlink or HTTP? These are all things that will be covered in this in this post. 

{% include under-p1-ad.html %}

## The Very Beginning
Sir Tim Berners-Lee is credited with inventing the world wide web in 1989. A British born computer scientist, Lee was interested in computers from an early age. His curiosity in electronics carried him throughout his days. He eventually attended and graduated from Oxford University. After graduation Berners-Lee became a software engineer at CERN.

> The Web as I envisaged it, we have not seen it yet. The future is still so much bigger than the past. – Tim Berners-Lee

While working there, he noticed that information stored on computers was very difficult to share, especially because at that time, information was different across different computers. By combining the power of the internet, Sir Tim Berners-Lee realized that computers could share information by exploiting an emerging technology called hypertext. He proposed this idea in an academic paper titled “Information Management: A Proposal. From here, Sir Tim Berners-Lee went on to create the three main technologies that to this day allow us to use the world wide web. 

There are three important technical things that make up the web. They are as follows:
1. HTML
2. URI
3. HTTP

HTML is a markup language which means that special codes are used to define elements. It is not a programming language. You may hear HTML being referred to as “source code”. You can code html in a plain text editor or any other code editor or IDE. HTML is fairly simple to write from a developer standpoint. It simply consists of tags that ground common things or content. Each tag starts with a “<” and ends with a “/>”. See the picture below for an example of HTML code.

<span class="blog-post-imbedded-img">
![]({{ site.url }}/assets/img/posts/4-understanding-the-world-wide-web/html-min.jpg) 
</span>

### Inspect Element
A fun trick you can do when you are using Google Chrome is to right click and hit inspect. This will show you the source code for the website you are viewing. You can see all of the html as well as other cool things. You can even edit the html but it will not save the changes for everyone, only on your local machine. When you refresh the changes will be gone. 

Every web page has these tags:

- **HTML**: HTML lets the browser know that an html page must be rendered. This tag encompasses all the content on the page.
- **Head**:The head tag is very important as it includes the title of the website, links to external files including CSS (the styling), and a bunch of metadata including the description and search terms. This is very important for search engine optimization (SEO) and will be talked about in a later post. 
- **Body**: This encompasses all the main html markup on the page. Paragraphs, images, headings, and much more can go in here.

 
A URI or Uniform Resource Identifier (commonly known as URL or Uniform Resource Locator) is the method for locating a document on the web. Typically the URL points to the home page or default page for a website. This page is often located in the root folder of a website and is usually called index.html.

Lastly is HTTP. The web is essentially a network of computers all over the world. The way these devices communicate to one another is a communication standard known as HTTP (hypertext transfer protocol).

## Different Parts of the World Wide Web
### Domain Name Server
When a user logs onto their computer and searches for a website, you are requesting a web document through your web browser. There are many browsers available but some of the most popular ones are Google Chrome, Apple Safari, and Mozilla Firefox. 

This request is handed to a DNS (domain name server)  which checks the domain name and finds the address of the web server. This web host or web server sends the requested document to your browser where you can then view it. All this is happening in a matter of seconds. 

### Role of the Web Browser
The web browser does many things for the user. First off, it interprets the html code. It also fetches a web page from a server by a request. A standard http request includes a page address.

### Basic Web Pages
Web pages are what the user views on their device. These are documents that can display text, graphics, audio, video, and other elements through a web browser. Web pages are stored on web servers and contain instructions on how to display content. The most common way to give these instructions in in html (hypertext markup language).

For an example of a basic web page, you can check out my personal website. Here you will find a static web page. You can also view the source code to my personal website on my Github to see the structure of web pages and how they are grouped together.

### Hyperlinks
Hyperlinks are what tie web pages together. They are what make navigation bars work and can be internal or external. If you log into a site by hitting “login”, that’s a hyperlink. Have you ever [clicked a Twitter](https://twitter.com/bencarlsonblog){:target="_blank"} button on a website and were brought to that companies or individuals Twitter account? That’s a hyperlink.

## What Came out of the World Wide Web
Lots of new ideas and ways of thinking emerged from the internet. The first is the idea of decentralization. Basically this means that there are no rules to publishing anything on the web. You have full control over what you post. This can of course lead to some obvious problems. 

Secondly, is the idea of non-discrimilization. This has to do with users paying to access the internet at different speeds. You might know of the phrase net neutrality. This is basically what this is and recently was an issue. In very simplistic terms, each user is able to communicate at the same level.

Third is the idea of universality. This allows anyone around the globe to publish a web page regardless of their hardware, operating system, or even cultural views. 

## Wrapping Up
As you can now tell, the world wide web is more complicated than you would imagine and this is only a brief description of it. If you found this article helpful or interesting, please share it using the share button to the bottom right. If you would like to see another more in-depth article about the world wide web, let me know in the comment section below! Happy coding!
