---
layout: post
title: "Python's lambda function - a beginner's guide"
description: "How to boost your python skills"
category: programming
tags: [programming, python]
---
{% include JB/setup %}

## Functions in python

I learned programming in Matlab and found the syntax easy. However,
writing functions were always a pain. Especially the input/output from
a function. After a year of programming/data reduction I gradually
switched to Python, and found writing functions very easy. Here is a
simple example of adding two numbers.

{% highlight python %}
def add(a, b):
    return a + b
{% endhighlight %}

This of course is a very simple example. The input is `a` and `b`, and the
function `add` gives the user back the sum. A simple call could be like this

{% highlight python %}
c = add(3, 4)
print c  # prints 7 to the terminal
{% endhighlight %}

We are all guilty of writing small functions as the on above. Typically it
takes just 3-5 lines, but it can be condensed down to just a single line of
code with the `lambda` expression.

## The lambda expression
Let me first write the same add function as above but with the `lambda`
expression, and then brake it down.

{% highlight python %}
add = lambda a, b: a + b
{% endhighlight %}

Here the function is also called `add` and works in exactly the same way as
before (therefore I will not show it). After the `lambda` expression is invoked
all inputs are show separated with a comma (as in the "traditional" way). All
after the colon is returned to the user (the sum of the input in this case).

Let's have a look at an example.

## The lambda expression in action
I will show an example where I use the `filter` function. The documentation
reads

> filter(function or None, sequence) -> list, tuple, or string
>
> Return those items of sequence for which function(item) is true.  If
> function is None, return the items that are true.  If sequence is a tuple
> or string, return the same type, else return a list.

So we will try to sort a list of numbers where division by 3 gives 0 remainder.
This task can be done in many ways: 1) a `for`-loop and appending the numbers
to an empty array, 2) with a list comprehension, but in this case we
want to make use of 3) the `lambda` expression. Here is how:

{% highlight python %}
print filter(lambda x: x%3==0, range(10))
[0, 3, 6, 9]
{% endhighlight %}

The first argument in the `filter` function is another function, but
created in-place with the `lambda` expression. This function returns
`True` if the remainder of a number divided by 3 is 0, and `False`
otherwise. The second argument is simple a list of numbers from 0 to 9.
This list is filtered and returns the above result.

### The list comprehension approach
To be complete, let me show you a solution using list comprehension and a for
loop as well. The list comprehension first.

{% highlight python %}
print [x for x in range(10) if x%3==0]
[0, 3, 6, 9]
{% endhighlight %}

This is certainly a very elegant solution as well. But today's topic is on the
`lambda` expression. So let's move on.

### The for loop approach
Here is a solution many of us might have used in the beginning of our Python
career.

{% highlight python %}
arr = []
for i in range(10):
    if i%3==0:
        arr.append(i)
print arr
[0, 3, 6, 9]
{% endhighlight %}

This approach gets the job done, and many coming from other programming
languages might be able to read this more easily than the two above
solutions. But take a look at the two approaches above. It is almost
written in English. This is one of Python's forces!



## A real life example
Finally, let's take a look on a real example. This is from one of the
first times I used the `lambda` expression. I have a plot that needs a
legend, but depending on the slope of a fitted line, it should either
say "Raise the temperature" or "Lower the temperature". Here is how I
went about it.

{% highlight python %}
lbl = lambda slope: '%s temperature\nSlope: %s' % ('Raise' if slope > 0 else 'lower', round(slope, 4))
{% endhighlight %}

And in the plot it is simple called like this

{% highlight python %}
plt.plot(x, y, 'ok', label=lbl(slope))
plt.legend()
plt.show()
{% endhighlight %}

`x`, `y`, and `slope` have been calculated before.

I hope you all learned something. I'm still learning about this little
gem, so let me know in the comment section below if you have other cool
uses of the `lambda` expression.
