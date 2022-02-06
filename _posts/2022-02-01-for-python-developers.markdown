---
layout: "post"
title: "Things you should know about Python as a Developer"
date: 2022-02-01 17:50:59 +5:45
tags: [python, thread, gil]
# categories: basic
---

Hey readers, today I am going to write something interesting about Python that every developer should learn about.

This is about the Python Programming Language, it's speciality and some pitfalls. So let's begin start exploring and learning about this beautiful high-level programming language.

**Python** is an interpreter based language. To elaborate, when we write the code in python, every section of the program gets compiled not like that of Java, C++ and C where the entire program is compiled first and we run the compiled file to get the output. Here in Python, it is different so the variable(let's suppose x) is an integer at line number 4, the same variable can be the list at line number 5. So, it is called dynamic language.

Another important thing about Python is it has a Global Interpreter Lock (GIL) which prevent two thread to run parallelly simultaneously. That means when there are multiple threads in Python they use the 'coordinated multi tasking' feature to run the thread at the kernel level.

I have a very good example to describe this feature.

When you run two threads with help of the python programming language in an octa-core computer. Those multiple threads can only take 100% of one single core of that computer, whereas in other languages like C++ you could take 100% of eight different cores to run the threads. So here in this example, two threads in python language could only share 100% with each other (for eg: 50% each) while the other core is not used although they may be free.

We can use threading in python by importing Thread from threading and use threading by using the following commands :

```
from threading import Thread

def myfunc():
    #do something

#creating thread
thrd = Thread
```

So to achieve multiple running of two tasks we can use multiprocessing only. The procedure is similar to the threading approach.

```
from multiprocessing import Process

def myfunc():
    #do something

#creating process
proc = Process(target=myfunc)
```

More about threading :
Python threading was different before the 3.2 version the sharing of the control between threads was by using the Ticks method where the thread checks if there is any other thread asking for thread control after 100 ticks. This method was tedious. There were issues like :

1. Starvation
2. Signaling overhead to tell thread has finished task.
3. Battle for GIL

But with a fixed time approach of 5ms for all the threads, it removes all three issues which used to be in the previous version. But it also has one major disadvantage. It has the property of having priority of CPU bound operation more than I/O bound operation but in fact, we need more priority to I/O operation. So this leads to a problem of Priority Inversion.

This is not to say that Python cannot execute truly multithreaded, parallel code. Python C extensions that use native multithreading (in C or C++) can run code in parallel without being impacted by the GIL, so long as they do not need to regularly interact with Python objects.

This is very necessary to understand the inner level of programming language, how it is built and it's architecture because it makes you understand what are the language speciality and where the language shorts.
