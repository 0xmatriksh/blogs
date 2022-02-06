---
layout: post
title: "Prerequisite for Data Science Developers in Python"
date: 2022-02-01 19:54:42 +0545
tags: [data science, python]
excerpt: "This blog discuss about different neccessary tools and library for every Data Science developer in Python"
# categories: jekyll update
---

![alt text]({{ '/assets/img/posts/ds_pfp.jpg' | relative_url}}){: .center-image }

Data Science is a very important job in today's age of data being the aspect that plays a vital role in most of the field whether it may be the medical field, business, agriculture, engineering, sports and the list go on and on.

Python is one of the programming language, which is used for data science and machine learning. It consists of many libraries and a very good community built within the past couple of decades. And it also has the upper hand among other languages as this same language can be used to build the system.

While I talk about libraries in Python for Data Science(DS), the first library that come into thought is `NumPy`, NumPy (abbreviation for Numerical Python) is the library built with the purpose of scientific calculation in numerical data. It is best for storing the numerical values in an array as a NumPy array that may be single or multi-dimensional (also called Tensors).

"Okay, then why not List?"

This is because a List in Python is dynamic in nature, with that I mean the list can store data of different types like integer, string, dictionary or in fact the list itself so the list takes a large amount of storage and in data science, for the storing and calculating process we have a large number of data to get the more accurate outcome from it so if we had used list it would have created a lot of issues.

Now, let's talk about another library that is `Pandas`. Pandas is the library built for storing tabular forms of relational data like that of excel (in fact we can read data of excel with the pandas function pandas.read_excel() and also CSV, similarly). We can play with data and make some changes we require, to refine and make some corrections in data like removing the NaN elements. To sum up, making the bulky data to one with only necessary attributes and elements.

There are other libraries also like `matplotlib` for plotting and visualization data on how the attribute affects each other or to the result, basically to understand more about data.
And, `sklearn` is another library used for different machine learning algorithms like linear regression, KNN classification and more.

To import these libraries we have the following method and alias as a convention in the Python programming world.

```
import numpy as np
import pandas as pd
import matplotlib as plt
```

We have talked about the libraries, now let's focus on where to write the code.

For that, we have `Jupyter Notebook`, a web-based interactive computing platform. Jupyter Notebook is the advanced version of IPython which is another important topic to understand, let's dig about them.

![alt text]({{ '/assets/img/posts/ipython.PNG' | relative_url}}){: .center-image}

When we want to write the python code what are our options. It is either to use shell or write the script as filename.py and run it. But they both have sharing merits and demerits sharing in a criss-cross manner. So we have IPython which is the solution to the above methods. With IPython we can easily understand the code as it runs for each segment(according to our will, how much we want) and also can edit the code in past run segments(or cells to be precise).

Great, but what is Jupyter Notebook then?
Jupyter Notebook is the more advanced form of IPython where we can also include texts, Markdown and include the output on the same page, which makes them easy to understand the flow of code. Jupyter Notebook runs on the browser as the client and interacts with Python kernel like the client-server model.

It establishes the connection with the Python kernel and when we run the code in the Notebook it passes the code to the kernel. The kernel is the server that enables Python programmers to run cells within Notebook, basically gets the code, process the code, give the result back to the client (the notebook running browser) and displays the result there. While the markup language is easily processed in the browser itself).

![alt text]({{ '/assets/img/posts/kernel.PNG' | relative_url}}){: .center-image}

Kernel displays the commands in a separate window. If you have ever used then you must have seen a command prompt like a window opens when we run Jupyter notebook and run some code in the browser that window also runs in the background doing some logic. Well, if you haven't tried Jupyter notebook yet then, time to give it a try and run some python code in it.

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
