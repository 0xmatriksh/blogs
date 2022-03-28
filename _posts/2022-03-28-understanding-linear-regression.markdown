---
layout: post
title: "Understanding Linear Regression"
date: 2022-03-28 21:44:42 +0545
tags: [data science, python]
excerpt: "This blog discuss about linear regression used as algorithm in machine learning implemented in Python"
# categories: jekyll update
---

When we start learning about the algorithms in Machine Learning, the first algorithm we encounter with or books introduce to us is Linear Regression algorithm. It is one of the most used atleast at begineer phase of any Data Science wannabes. Most of us have heard about this algo before, not? atleast you heard it when I mentioned above.

Linear Regression is the algorithm used for Regression based Supervised learning. In regression we predict the actual value of the output, unlike Classification based which predict the category the output lies on (for eg: True or False, Dog or Cat). As we need a actual value as output for Regression the linear regression algorithm gives us the linear line which tells the property of the data. For example y = 5x + 2. For input value of x as 4, the output value of y will be 22.

Linear Regression(LR) are has different types, mainly Simple LR and Multiple LR. Simple LR is just the example we mentioned above. It has sinlge independent varialbe(input) x for single dependent varialbe(output) y which is actually dependent on x, is in the form of y = mx + b, where m is slope and b is y-intercept, which is defined for a particular line and shows two typical property of the line. So when we are doing machine learning with LR, our actual task is to find this line.

#### What exactly is m and b?

Basically m also called slope is the weightage of x. That means by what parameter the value of x has weight on the value of y, by what amount he value of y depends on value of x.

Whereas the b is the outlier. If the value of x = 0, what will be the value of y.
(Figure to show slope and y-intercept)

Now, we understood what is Simple LR, how to implement in coding. For this, we have a well known machine learning library scikit-learn which has all the necessary machine learning algorithm and also other facility.

One of the facilites is to split our input(x) and output(y) as train and test data.

```
from sklearn.model_selection import train_test_split
X_train,X_test,y_train,y_test = train_test_split(X,y,test-size=0.2)
```

After done spliting we can import linear regression to train the algorithm for creating the line to represent our data in the form of `y = mx + b`.

```
from sklearn.linear_model import LinearRegression
lr = LinearRegression()
lr.fit(X_train,y_train)
```

We can also print the value of m and b for our line by following line of code

```
m = lr.coef_
b = lr.intercept_
```

#### What exactly is done by scikit-learn under the hood?

Basically to produce the a line of equation y = mx + b, the scikit-learn runs some logic, which is just the mathematics behind the Linear Regression. If we learn this logic, we can create our own <YourNameLinearRegression>.

To find the value of m and b:
Let's assume the value of Y at Xi is Yi as per the linear regression's line but actually it was Y(cap) as per the the data. So here the error is Yi-Y(cap), which is squared to remove the negative element(because it could be up or down, which Yi-Y(cap) could be positive or negative).

Y(cap) is the actual location of point so it can be written as:
Y(cap) = mXi+b

So E(m,b) = (summation from i to n) (Yi-mXi-b)^2
Now our goal is to minimize this error(E).

(3D figure)

We know that slope is 0 at the minimum point and the slope is given by the first order differentiation of the E.
First, we differentiate E with respect to 'm' and differentiate it with respect to 'b'.

<differentiation of E = Yi - mXi - b w.r to b>

So the value of b = Y(bar) - mX(bar)
And, now using b in E to differentiate w.r to m:

<differentiation of E = Yi - mXi - b w.r to m>

So, the value of m becomes = (X-Xi)(Y-Yi)/(X-Xi)^2
Now, when we know the logic behind calculation of m and b.
We can implement this in code:

```
class MyLR:
	def __init__(self):
		self.m
		self.b
	def fit(self,X_train,y_train):
		num = 0
		den = 0
		X_mean = X_train.mean()
		y_mean = y_train.mean()
		for i in range(X_train.shape[0]):
			num = num +  (X_train[i] - X_mean)(y_train[i]-y_mean)
			den = den +  (X_train[i]-X_mean)^2
		self.m = num/den
		self.b = y_mean - m*(X_mean)
	def predict(self,X_test): #takes single value
		return (self.m*X_test)-self.b
```

Similarly we have multiple linear regression where the equation is in form of

`Y = b0 + b1X1 + b2X2 + ..... bmXm`

where m in the number of features in input.
And a plane is used instead of line in the (m+1)D space.

So similarly, the error in each point is given by Yi-Y(cap). And the total error is given by E = e^T.e

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
