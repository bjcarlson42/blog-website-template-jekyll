---
layout: post
title: "Client Side Form Validation In JavaScript"
date: 2019-12-10
categories: ['Javascript','Programming','Web Development','Technology']
tags: ['First Post','Internships','Python','Programming']
comments: true
author: Benjamin Carlson
description: Whenever you are browsing the web, you are bound to come across some sort of form you need to input information into. You may be inputting credit card information to buy an item off Amazon, or inputting...
img: /assets/img/posts/7-client-side-form-validation/client-side-form-validation.jpeg
alt: Javascript book
---

## Introduction
Whenever you are browsing the web, you are bound to come across some sort of form you need to input information into. You may be inputting credit card information to buy an item off Amazon, or inputting your username and password to log into Instagram. You may even be inputting your email to subscribe to my newsletter. Regardless of what or where you are inputting this information, it needs to be verified in some way.

{% include under-p1-ad.html %}

There are two ways to do this. It can be verified by the server (server side verification) or it can be verified right as the user enters the information in the form (client side validation). In this post, I will go over how to use JavaScript to perform client side verification to verify information entered into a HTML form. As always, the code can be found on my [GitHub](https://github.com/bjcarlson42/blog-website-code/tree/master/JavaScript%20Form%20Validation).

## Setting Up

The first step is to write some HTML code. We need to use the form tag along with some input tags to gather all of the information. Take a look at the code below where I am creating an index.html file with a basic [HTML form](https://www.w3schools.com/html/html_forms.asp).

<pre class="theme:github lang:xhtml mark:6 decode:true"><html>
<head>
    <title>JavaScript Form Validation</title>
</head>
<body>
    <form action="response.html" medhod="post" onsubmit="return validateForm()">

        <table width="450px" style="background-color: lightgray">

            <tr>
                <td valign="top">
                    <label for="first_name" id="lblFirstName">First Name *</label>
                </td>
                <td valign="top">
                    <input type="text" name="first_name" id="firstName" maxlength="50" size="30">
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <label for="last_name" id="lblLastName">Last Name *</label>
                </td>
                <td valign="top">
                    <input type="text" name="last_name" id="lastName" maxlength="50" size="30">
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <label for="email" id="lblEmail">Email Address *</label>
                </td>
                <td valign="top">
                    <input type="text" name="email" id="emailAddress" maxlength="80" size="30">
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <label for="telephone" id="lblTelephone">Telephone Number *</label>
                </td>
                <td valign="top">
                    <input type="text" name="telephone" id="telephoneNumber" maxlength="30" size="30">
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <br>
                    <label>Jersey Style</label>
                </td>
                <td valign="top">
                    <br>
                    <select name="style">
                        <option value="Collar">Collar</option>
                        <option value="Mock Neck" selected>Mock Neck</option>
                        <option value="T-Shirt">T-Shirt</option>
                    </select>
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <br>
                    <label>Size</label>
                </td>
            </tr>
            <tr>
                <td valign="top">
                    <input type="radio" name="size" value="Small"> Small<br>
                    <input type="radio" name="size" value="Medium"> Medium<br>
                    <input type="radio" name="size" value="Large" checked> Large<br>
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <br>
                    <label>Color</label>
                </td>
            </tr>
            <tr>
                <td valign="top">
                    <input type="radio" name="color" value="Red" checked> Red<br>
                    <input type="radio" name="color" value="white"> White <br>
                    <input type="radio" name="color" value="Blue"> Blue<br>
                </td>
            </tr>

            <tr>
                <td valign="top">
                    <br>
                    <label for="comments" id="lblComments">Comments *</label>
                </td>
                <td valign="top">
                    <br>
                    <textarea name="comments" id="comments" maxlength="1000" cols="25" rows="6"></textarea>
                </td>
            </tr>

            <tr>
                <td colspan="2" style="text-align:center">
                    <input type="submit" value="Submit">
                </td>
            </tr>

            <tr>
                <td colspan="2" style="text-align:center">
                    <p id="msg" style="font-weight: bold; color: red;"></p>
                </td>
            </tr>

        </table>
    </form>
</body>
</html></pre>

This is a lot of HTML code but it is fairly simple. It consists of the following elements:

1.  A standard html, head, and body tag.
2.  Inside the body tag there is a form tag which holds all of the input fields.
3.  Inside the form there is a table tag. This is used for the layout. If you don't know much about html tables you can read up on it [here](https://www.geeksforgeeks.org/html-tables/).

Inside the table, there are a few different tags, but the important one is the input tag. This is where we are getting the actual user input from. Additionally, on line 6, we see 3 important parameters.

### Parameters

They are as follows:

1.  action = "response.html"
2.  method = "post"
3.  onsubmit = "return validateForm()"

**action = "response.html"** means that when the form is submitted successfully, it will redirect to a page named action.html. The next is **action = "post"**.There are two commonly used action parameters for forms - get and post. This is referring the the url string. If the parameter is get, all of the information entered into the form will be visible in the url. If the parameter is post, it will not be visible. For security reasons, the post method is usually used.

### Adding JavaScript Validation

Next, we need to validate the form. If you try to hit submit now, it will "work" (you will get an error saying cannot get response.html but the form went through. For completeness, you can create a file names response.html and simply write "It worked!"). I am writing "worked" in parentheses because we were able to get past the form successfully. It did not, however, validate the input in any way. To do that, we need to use JavaScript. To do this, insert the following tag underneath the first body tag:

<pre class="theme:github lang:js decode:true ">//code above

<body>
    <script>
    //JavaScript Validation will go here.
    </script>

//code below</pre>

Now, we must add the JavaScript. The first step is to declare a function. We will name this function "validateForm".

<pre class="theme:github lang:js mark:2-4 decode:true "><script>
        function validateForm() {

        }
    </script></pre>

Next, we need to make a variable for each of the users input. In this case, we have 5 places where the user can enter text data, so we need 5 variables.

<pre class="theme:github lang:js mark:3-7 decode:true"><script>
        function validateForm() {
            inFirstName = document.getElementById("firstName").value
            inLastName = document.getElementById("lastName").value
            inEmailAddress = document.getElementById("emailAddress").value
            inTelephoneNumber = document.getElementById("telephoneNumber").value
            inComments = document.getElementById("comments").value
            result = true
        }
    </script></pre>

Now we will add some logic. If the user enters nothing, we want to give them an error. We show this in JavaScript by writing the following line:

<pre class="theme:github lang:js decode:true ">if (inFirstName == "") {
                document.getElementById("lblFirstName").style.backgroundColor = "red"
                result = false
            } else { 
                document.getElementById("lblFirstName").style.backgroundColor = "lightgrey"
                result = true
            }</pre>

This says, if the variable called "inFirstName" is empty (the user entered nothing), then turn the background color red and set the result to false. If that is true, the else statement is executed. This turns the background color back to its original color and sets the result to true (important if the result was originally false). The result is the result of the function. If the overall function executes as true, it will allow the user to submit the form. Look back at the 4th code block. Here, we set the function to true so we assume that the user has entered all of the correct information. If the user enters nothing, the result will be set to false. We can now repeat this for the remaining input fields.

<pre class="theme:github lang:js decode:true ">if(inLastName == "") {
        document.getElementById("lblLastName").style.backgroundColor="red"
        result = false
      }else {
        document.getElementById("lblLastName").style.backgroundColor = "lightgrey"
        result = true
      }

      if (inEmailAddress == "") {
        document.getElementById("lblEmail").style.backgroundColor = "red"
        result = false
      }else {
        document.getElementById("lblEmail").style.backgroundColor = "lightgrey"
        result = true
      }  

      if (inTelephoneNumber == "") {
        document.getElementById("lblTelephone").style.backgroundColor = "red"
        result = false
      }else {
        document.getElementById("lblTelephone").style.backgroundColor = "lightgrey"
        result = true
      }

      if(inComments == "") {
        document.getElementById("lblComments").style.backgroundColor = "red"
        result = false
      }else {
        document.getElementById("lblComments").style.backgroundColor = "lightgrey"
        result = true
      }</pre>

Lastly, we will return the result.

<pre class="theme:github lang:js decode:true "> return result</pre>

Note: Remember that the entire code can be found on my [GitHub](https://github.com/bjcarlson42/blog-website-code/tree/master/JavaScript%20Form%20Validation).

### Adding a Helpful Message

We are done, but there is one more touch we can add. If you look back to the first code snippet, you will notice a paragraph tag at the bottom with the id "msg". This can be used to display a message if the function returns false. We can add the code:

<pre class="theme:github lang:js decode:true">if (!result) {
                document.getElementById("msg").innerHTML = "Please enter valid data in highlighted fields."
                result = false
             }</pre>

This will give the user a message when the fields are not entered.

## Conclusion

And with that, we are done. Please visit my [GitHub repo](https://github.com/bjcarlson42/blog-website-code/tree/master/JavaScript%20Form%20Validation) for the completed code for this post and other posts. There is still more that we can do, like adding regular expressions or HTML validation to make sure the input entered is correct. For example, if we want a phone number entered, we don't want text to be allowed through. If you would like to see a tutorial like this in the future, leave a comment on this post and I'll make a separate post on it! Good luck and happy coding!
