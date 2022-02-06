---
layout: post
title: "Understanding Web In General"
date: 2022-02-05 21:54:42 +0545
tags: [http, www, web]
excerpt: "This is about the how the web works or to be precise what happens unders the hood when we visit a website"
---

![alt text]({{ '/assets/img/posts/webindepth.jpg' | relative_url}}){: .center-image }

When we open a browser and type "www.example.com" it establishes the connection as you being in the browser as client and example.com's computer stored somewhere on the internet.
When we say the internet connects everything, this is one example.

Here, you as a client want to take service from the server example.com.

How is the connection established?

The connection is established with the help of HTTP protocol. Now let's dig inside HTTP.

HTTP is a protocol for transferring Hypertext data from one computer to another on the World Wide Web basically the internet. Let's understand it more with the above example. When you go to example.com. First, the connection is established between a server and you as a client to communicate a socket is established for request and response. Your request to view the homepage is then taken as a request after connection establishment. And the server is designed in such a way that, what should we do when a particular request comes. Here also, the server has a response ready. That response travels via the socket to the Client. This is the task of HTTP.

And more on HTTP, HTTP request and response connection it can be persistent or non-persistent. Non-persistent basically destroy connection after every data transfer. Whereas in persistent, multiple request-response transfers can occur after a connection.

But, what is that connection establishment in beginning?

Basically, there are two types of connection TCP and UDP. In bird eye view, TCP is reliable and UDP is not reliable but fast. And here in this case we use TCP because we want every response and request between client and server to reach each other without any loss of data.

HTTP is stateless. We have learnt that HTTP establishes the TCP connection before request-response. And also got the idea that HTTP destroys connection after transmission, this feature of HTTP is called stateless.

So with this, we came to the conclusion that HTTP is Gajani. It does not recognize you are the same user. No matter how many times you go to example.com it assumes you are a new user. Then how come an 'XYZ' e-commerce website recognize me, if it is stateless?

Then here comes an idea of Cookies. Cookies which is stored in your browser makes it recognize as you are the one who is making the request. So it is your browser that is recognized, not you a person. To recognize you as a person you need to have a user account for example.com.

But even if you had created an account and logged in as a user in example.com, it forgets every time you make a new request that essentially means logging in every time for viewing content for your account. Because HTTP is stateless.

There are three ways to recognize a user:

1. Cookies
2. Sessions
3. Token Based

Cookies :
So when you go to example.com it assigns you an identification number and saves other information(like name, age) together as a cookie in your browser. But this method is less secure. So, we have sessions.

Sessions:
Sessions basically are the secured form of the Cookie system above explained. In spite of saving all the information on the user's browser, it only saves the identification number as session-id in the user's browser and has a database in the server from where that session id is mapped to get the other information. Also, the server terminates the session after a certain time. Remember that time when you have been logged out of the website automatically after some time? The session time limit was the reason. And if the expiration is not declared it expires on tab close by default.

The problem with this method is that we have to store the extra database for the session, so comes the token method.

Token-Based:
In this case, the server assigns a token to the user in place of the session. The user information is also embedded inside the token. And when the server sends the token to the user the browser stores it in the storage mechanisms like local Storage and Session Storage. And that token is sent to the server every time the request is made. Here the private key is used in the server which can only decrypt the token.
And with this method, there is no need for the extra database problem. One of the implementations is JSON Web Token(JWT).

So much about authentication and sessions and all.

Now let's dig inside the frontend, the thing that we see in our browser as a response from a server on a web page.

How does this work?

There are basically two ways of rendering the content in the browser, Client-side rendering and Server-side rendering.

Client-side rendering for example React first gets all the javascript content from the server and renders the HTML from the javascript received. The javascript contains HTML for all the pages of the website and it does not have to request for another page once the JS is loaded in the browser. This method has pros and cons. The benefit is there is no need to request more than once for the server and it is highly interactive. While there is the demerit of Low SEO because the website is not loaded until rendered on the browser. And loading javascript is slow so it requires more time to load the site for the first time.

While on the other hand, we have Server Side rendering. In this approach, the HTML content is preloaded in the server and sent to the browser as a response to the request of the page. This has the advantage of better SEO as the search engine can crawl the website. And loading HTML is faster. But has the disadvantage of requesting for every page and more on that pre-loading the page on the server becomes a slow task.

We have a better implementation of this method today with Next.js, it uses CDN, a dumb server to load the HTML in the server in spite of the actual server and makes the work lot faster.
